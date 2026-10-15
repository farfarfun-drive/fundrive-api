# fundrive-api

占位仓库，规划中的 HTTP API 形态的 fundrive，当前还没有任何功能代码。建库只是先把名字和
位置占下来，等 fundrive 产品线需要常驻服务进程时在这里开工。

## 规划中的职责

把 [fundrive](https://github.com/farfarfun-drive/fundrive) 的统一网盘接口包装成 REST 服务：
以常驻进程形式对外提供 `/api/**` 这类 HTTP 端点，再由
[fundrive-web](https://github.com/farfarfun-drive/fundrive-web) 反向代理后供浏览器调用。
按组织内 `submodule-workspace-governance` 的约定，`-api` 结尾的仓库属于 service 形态，
需要完整的启停与发布动作，而不是纯 package。

## 当前状态

- 仓库里只有这份 README：没有源码目录，也没有 `pyproject.toml`。
- PyPI 上没有 `fundrive-api` 包，无法 `pip install`。
- [fundrive-dev](https://github.com/farfarfun-drive/fundrive-dev) 的 `scripts/setup.sh` 里
  留了注释说明将来要接入这类带进程的 app，但还没有把本仓库纳入子模块。

## 安装与替代方案

本仓库暂无可安装产物。现在要用 fundrive 的网盘能力，直接安装核心包：

```bash
pip install fundrive
```

各网盘驱动按需单独安装，例如阿里云盘：

```bash
pip install fundrive-alipan
```

想一次拉齐整条产品线做跨包联调：

```bash
git clone --recurse-submodules https://github.com/farfarfun-drive/fundrive-dev.git
cd fundrive-dev
```

## 关于组织

[farfarfun-drive](https://github.com/farfarfun-drive) 是 farfarfun 旗下专注网盘 / 云存储
方向的组织，围绕 fundrive 这套统一接口维护主框架、各网盘驱动包、子模块编排仓库和桌面
客户端。本仓库是这条产品线为 HTTP 服务形态预留的位置，尚未进入开发。

- 🏠 组织主页：<https://github.com/farfarfun-drive>
- 🏠 上级组织：<https://github.com/farfarfun>
- 📧 联系：farfarfun@qq.com
