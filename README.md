# go-musicfox (VincentZyu Fork)

<p align="center">
  <img src="previews/logo.png" alt="go-musicfox VincentZyu fork logo" width="256">
</p>

> [!TIP]
> 这是 VincentZyu 的 fork 版本，并增加 SPlayer-Next 兼容 HTTP/WS API。
> 上游 PR 保持原版视觉与最小改动。

[点击跳转到阅读上游仓库 README →](https://github.com/go-musicfox/go-musicfox#readme)

## 效果预览

![go-musicfox external API 与 OBS Overlay 实机预览](previews/preview.obs.html.overlay.png)

## 构建与全局安装

需要 Git、Go 1.26+ 和 C 编译器，并将示例路径替换为实际目录。

### Windows

```powershell
git clone https://github.com/VincentZyuLive/go-musicfox-vincentzyu-fork.git
cd go-musicfox-vincentzyu-fork
powershell -NoProfile -ExecutionPolicy Bypass -File .\hack\build.ps1 build -BuildTags "enable_global_hotkey,purego"
$InstallDir = "D:\path\to\musicfox-vincentzyu-fork"
New-Item -ItemType Directory -Force $InstallDir | Out-Null
Copy-Item .\bin\musicfox.exe "$InstallDir\musicfox-vincentzyu-fork.exe" -Force
# 将 $InstallDir 加入用户 PATH，并重新打开终端
musicfox-vincentzyu-fork --version
```

### Debian / Ubuntu

```bash
sudo apt update
sudo apt install -y git build-essential libflac-dev libasound2-dev
# 从 https://go.dev/dl/ 安装 Go 1.26+，确保 go 命令在 PATH 中
git clone https://github.com/VincentZyuLive/go-musicfox-vincentzyu-fork.git
cd go-musicfox-vincentzyu-fork
BUILD_TAGS="enable_global_hotkey,purego" ./hack/build.sh build
sudo install -Dm755 bin/musicfox /path/to/musicfox-vincentzyu-fork/musicfox-vincentzyu-fork
# 将 /path/to/musicfox-vincentzyu-fork 加入 PATH，并重新打开终端
musicfox-vincentzyu-fork --version
```
