# Julia Offline Packing Solution

## Advisor

Johnny Chen (johnnychen94@hotmail.com)

## Difficulty

Advanced: student will need to find a way to extend Julia's package delivery design

## Description

Currently, there is only one way to reproduce your julia project in other machines: copy the `Manifest.toml` and `Project.toml` and then `pkg> instantiate`. However, this method requires the target machine have the network access to the same pkg server as the source machine, which is not always the case.
For instance, in supercomputing clusters, nodes are usually isolated from each other, and the pkg server is usually only accessible from the login node. In this case, the `instantiate` command will fail.

This project aims to provide a way to pack the whole julia environment into a single file, so that the environment can be reproduced in other machines without the network access to the pkg server.

The idea is to provide a CLI command utility `jlpack` that can be used in the following way (just a rough idea, not the final API):

pack:

```sh
# pack the current project
jlpack pack --project=path_to_my_example_project --out=example.jlpkg
```

unpack:

```sh
# unpack the project as a new Julia depot
example.jlpkg unpack --out=$HOME/.julia
```

The key challenges are:

- local pkg server: still keeps `Manifest.toml` but build a local Julia pkg server that can serve the packages. This involves:
  - how to pack the packages and artifacts into a single, portable file. One might choose to download from existing pkg servers, but it's likely that building from source is also needed.
  - how to rewrite/trim the pkg registry so that only what's available is recorded in the registry.
- cross-platform: the packed file should be portable across different platforms (e.g. Linux, macOS, Windows, etc.). This involves:
- latency: the unpacking process should be as fast as possible. Thus Julia might not be the best choice for the implementation; modern static languages such as C++、Go、Rust、TypeScript are good candidates.

### Required knowledge

- HTTP
- Julia Pkg system: the design of julia depot path, julia registry, pkg/storage server, etc
- cross-platform CLI tool development experience
- familiar with one static language as the implementation language
