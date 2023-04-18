# Julia 离线打包方案

## 导师

陈久宁 (johnnychen94@hotmail.com)

## 难度

进阶：要求学生找到一个恰当的扩展 Julia 打包及分发系统的方式

## 说明

目前，Julia 社区提供的唯一一种在其他机器上复现 Julia 项目的方法是：复制 `Manifest.toml` 和 `Project.toml`，然后执行 `pkg> instantiate`。但是，这种方法要求目标机器能够访问与源机器相同的 pkg 服务器，这并不总是可行的。
例如，在超级计算集群中，节点通常彼此隔离，而 pkg 服务器通常只能从登录节点访问。在这种情况下，`instantiate` 命令将失败。

这个项目旨在提供一种将整个 Julia 环境打包到单个文件中的方法，以便可以在没有访问 pkg 服务器的情况下在其他机器上复现环境。

这个项目的想法是提供一个 CLI 命令行工具 `jlpack`，可以用以下方式使用（只是一个粗略的想法，不是最终的 API）：

打包：

```sh
# 打包当前项目
jlpack pack --project=path_to_my_example_project --out=example.jlpkg
```

解包：

```sh
# 将项目解包为新的 Julia depot
example.jlpkg unpack --out=$HOME/.julia
```

关键挑战是：

- 本地 pkg 服务器：仍然保留 `Manifest.toml`，但是构建一个本地的 Julia pkg 服务器，以便它可以提供软件包。这涉及：
  - 如何将软件包和工件打包到单个可移植文件中。人们可能会选择从现有的 pkg 服务器下载，但是构建源代码也是必要的。
  - 如何重写/修剪 pkg 注册表，以便只记录可用的内容。
- 跨平台：打包的文件应该能够跨不同的平台（例如 Linux、macOS、Windows 等）进行移植。
- 延迟：解包过程应该尽可能快。因此，Julia 可能不是实现的最佳选择；现代的静态语言，如 C++、Go、Rust、TypeScript 是很好的候选者。

### 所需知识

- HTTP
- Julia 包系统：Julia depot 路径、Julia 注册表、pkg/storage 服务器等的设计
- 跨平台 CLI 工具开发经验
- 熟悉一门静态语言作为开发方案
