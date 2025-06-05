---
title: "下一代的 Python 包管理利器 uv 快速指北"
categories: [ "Python" ]
tags: [ "python", "uv" ]
draft: false
slug: "python-uv"
date: "2025-06-06T00:55:00+0800"
---

## 前言与介绍

Python 有一个生态明星公司 Astral Software，在这之前或许很多人已经用过了 ruff 这款 linter，在 GitHub 斩获 15k+ 星的 uv 横空出世三个月，技术圈已涌现上百篇测评。在这之前，我用过诸如 conda 或 poetry 等包管理器，最后还是回归到了 Python 自带的 venv，但在我使用 uv 一个月后，彻底抛弃了 venv。

uv 的官方写到的亮点：

- 10 - 100 倍快于 pip
- 全面的项目管理，带有依赖锁文件
- 支持安装和管理 Python 发行版
- 提供与 pip 兼容接口
- 磁盘利用率高，可复用的全局缓存
- 良好的跨平台支持

uv 整体吸收了 Rust Cargo 的先进包管理经验，使得开发人员可以快速过度到 uv

---

## 重新定义 Python 工作流

### 性能碾压背后的技术革命

- **Cargo式依赖解析**：基于 Rust 实现的 PubGrub 算法，比 pip 快 8-10 倍的依赖解析速度
- **跨平台缓存机制**：首次安装后依赖包全局缓存复用，实测 conda 环境重建速度提升 6 倍
- **统一工具链**：用 `uv pip` 替代pip，`uv venv` 管理虚拟环境，`uv run` 执行脚本

### 多维度工具对比矩阵

| 特性               | pip   | Poetry | Conda | uv      |
|--------------------|-------|--------|-------|---------|
| 依赖解析速度       | 1x    | 0.8x   | 0.5x  | **8x**  |
| 虚拟环境管理       | ❌     | ✅      | ✅     | ✅       |
| 跨平台二进制兼容   | ❌     | ❌      | ✅     | ✅       |
| 项目模板生成       | ❌     | ✅      | ❌     | ✅       |
| 单文件部署         | ❌     | ❌      | ❌     | ✅       |

---

## 安装、卸载与换源

### 一行命令安装

uv 的安装非常简单，一行命令即可完成

```shell
# Linux 和 macOS
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows PowerShell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 卸载

很多文章没有介绍如何卸载，其实非常简单，因为 uv 已经打包成为一个独立的二进制文件，只需移除删除缓存和 uv 本身即可

```shell
# 清除缓存
uv cache clean

# 删除本体
# Linux 和 macOS
rm -r "$(uv python dir)"
rm -r "$(uv tool dir)"

# Windows PowerShell
Remove-Item -Recurse -Force -Path $(uv python dir)
Remove-Item -Recurse -Force -Path $(uv tool dir)
```

### 更换 PyPI 源

如果不做任何配置，uv 默认会使用 PyPI 官方源，如果你需要使用国内源，可以使用下面几种办法来更换源（默认都以清华源为例）。

uv 的配置文件分为项目级、用户级和系统级，如果你只想将某个项目的源配置为国内镜像，那么只需要在创建依赖后把下面的内容添加到项目目录下的 `pyproject.toml`

```toml
[[tool.uv.index]]
url = "https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"
default = true
```

如果想对所有项目都生效，则需要配置全局配置，创建一个全局的配置文件 `~/.config/uv/uv.toml` 并将以下内容写入

```toml
[[index]]
url = "https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"
default = true
```

---

## 项目实战

### Python 版本管理

默认情况下，uv 会使用系统中内置的 Python 版本作为项目的 Python 解释器，如果你需要使用特定的 Python 版本，可以使用 `uv python` 命令来管理 Python 的版本，下面是 uv 提供的一系列命令


| 命令                | 用途（中文）                             |
|---------------------|------------------------------------------|
| `uv python install` | 安装指定版本的 Python                    |
| `uv python list`    | 查看可用的 Python 版本                   |
| `uv python find`    | 查找已安装的 Python 版本                 |
| `uv python pin`     | 将当前项目固定使用特定的 Python 版本     |
| `uv python uninstall` | 卸载某个 Python 版本                   |

### 从零到生产：快速依赖管理

如果你主力管理依赖还是用的 pip，那么只需要在 pip 前面加上 uv 就可以了，`uv pip` 是一个兼容命令

```bash
# 创建项目并初始化虚拟环境
mkdir hello-uv
uv venv .venv
uv pip install -r requirements.txt
```

如果用于开发项目，那么下面是 uv 的最佳实践

创建并初始化项目

```shell
uv init hello-uv && cd hello-world
```

管理依赖是我使用 uv 的主要目的，使用 uv 添加依赖非常简单，和 pnpm 和 cargo 差不多，使用 `add` 来添加依赖

```shell
uv add requests
```

指定依赖的版本

```shell
uv add 'requests==2.32.2'
```

安装依赖的速度非常快，同时项目目录下还自动生成了 `uv.lock` 文件用于锁住依赖

使用 `uv lock` 以及 `--upgrade-package` 标志升级软件包

```shell
uv lock --upgrade-package requests
```

使用 `remove` 命令删除依赖
```shell
uv remove requests
```

如果是使用其他人的项目，将代码克隆下来后，只需要简单的使用 `sync` 来安装所有依赖

```shell  
uv sync
```

依赖树可视化
```shell
# 查看依赖树
uv tree

# 查看最多 2 级的依赖，防止依赖树过大
uv tree --depth 2
```

将会输出

```text
Resolved 6 packages in 0.38ms
hello-uv v0.1.0
└── requests v2.32.3
    ├── certifi v2025.4.26
    ├── charset-normalizer v3.4.2
    ├── idna v3.10
    └── urllib3 v2.4.0
```

在项目根目录创建一个 `main.py`，然后使用 `run` 命令启动项目

```python
# main.py

import httpx

def main():
    response = httpx.get('https://example.com')
    print(response.status_code)

if __name__ == '__main__':
    main()
```

```shell
uv run main.py
```

### 构建发行版及发布

使用以下命令构建您的包

```shell
uv build
```

默认情况下，`uv build` 将在当前目录中构建项目，并将构建的工件放在 `dist/` 子目录中

使用以下命令发布您的软件包

```shell
uv publish
```

使用 `--token` 或 `UV_PUBLISH_TOKEN` 设置 PyPI 令牌，或者使用 `--username` 或 `UV_PUBLISH_USERNAME` 设置用户名，使用 `--password` 或 `UV_PUBLISH_PASSWORD` 设置密码。从 GitHub Actions 发布到 PyPI 时，无需设置任何凭据。只需向 `PyPI` 项目添加受信任的发布者即可。

---

整理了一份 uv 项目依赖管理常用命令表

| 命令         | 作用                                     |
|--------------|------------------------------------------|
| `uv init`    | 创建一个新的 Python 项目                 |
| `uv add`     | 为项目添加依赖项                         |
| `uv remove`  | 从项目中移除依赖项                       |
| `uv sync`    | 同步项目依赖与环境                       |
| `uv lock`    | 为项目依赖创建锁文件（lockfile）         |
| `uv run`     | 在项目环境中运行命令                     |
| `uv tree`    | 查看项目的依赖树                         |
| `uv build`   | 将项目构建为可分发的归档文件             |
| `uv publish` | 将项目发布到包索引（如 PyPI）            |


## 何时该拥抱 uv

✅ **推荐场景**：
- 需要同时维护多个 Python 版本项目
- CI/CD 流水线中依赖安装耗时严重
- 开发跨平台桌面应用或工具包

⚠️ **暂缓使用**：
- 深度依赖 conda 特定科学计算包
- 企业内网无网络缓存环境
- 必须支持 Python 2.7 的遗留系统
