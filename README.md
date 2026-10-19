# Character Pet

Windows 桌面 AI 角色桌宠。当前角色：散兵 Q 版。

> 这是**分发仓库**，只放安装包、安装说明、版本更新说明与许可声明；不包含源码，也不包含角色包或解锁码。
> 解锁码由发布者单独提供，每个码绑定一台机器。

## 下载

- 最新安装包：[Releases](../../releases/latest)
- 当前版本：**v0.1.1**
- 文件：`CharacterPet-Setup-0.1.1.exe`（约 229MB）
- SHA256：`f8b202dc2b01c98023584e3d7f22ecf0d516c72dd79c678eda40a8e7b0d7aa9b`
- 系统：Windows 10/11 x64；无需管理员权限；建议 4GB+ 内存、500MB+ 磁盘。

## 安装

1. 下载 `CharacterPet-Setup-0.1.1.exe`。
2. 双击运行。Windows SmartScreen 可能提示未知发布者，选择“更多信息 → 仍要运行”。
3. 安装到 `%LOCALAPPDATA%\Programs\CharacterPet`，自动创建桌面与开始菜单快捷方式并启动。
4. 安装包不安装系统服务，不写系统目录，不需要管理员权限。

## 第一次启动

### 1. 解锁码

安装包**不内置基础角色**。首次启动必须输入发布者提供的解锁码：

- 服务端验证后，只下载该码对应的加密角色包；安装包本身不包含角色。
- 一码绑定一台机器；同一台机器重装可再次激活；换机需由发布者重置。
- 角色包 AES-256-GCM 加密，下载后先校验 SHA256 再安装。
- 新形象使用新的独立解锁码；从托盘菜单“解锁新形象…”添加。

### 2. 网络要求

激活和角色包下载通过 Netlify 中转，国内普通网络可直接使用，不需要自己配置代理。第一次激活请保持网络畅通；角色包约 3MB。

### 3. 对话后端

默认选择 **DeepSeek API**：

- API Key：`sk-...`
- 模型：默认 `deepseek-chat`
- Base URL：默认 `https://api.deepseek.com`

也可以：

- **本机 Ollama**：先启动 Ollama，点“检测本机 Ollama”，选择/填写模型（默认 `qwen3.5:9b`）。
- **暂不配置**：桌宠仍可启动，动作/动画正常；对话关闭。之后从托盘“对话 / API 设置”重新配置即可恢复。

API Key 只保存在本机：

```text
%APPDATA%\CharacterPet\home\dsh-pet\llm.json
```

不会上传到本项目服务器。

### 4. 启动后

- 主程序常驻系统托盘；桌宠是独立透明置顶小窗。
- 托盘菜单：对话 / API 设置、解锁新形象、打开数据目录、退出。
- 点桌宠打开右键菜单；可碎碎念、对话、拖动、点击互动。

## 语音

发布包**不内置** F5-TTS/Torch 模型，但内置一键安装代码（`uv.exe`、`f5_tts_server.py`、`voice-install.ps1`）。

首次安装：

1. 托盘 →“语音（F5）”，或首次设置里的“语音（F5）安装 / 管理”。
2. 点“一键安装 / 修复 F5”，确认下载（约 3–4GB）。
3. 安装器会下载 Python 3.10、CUDA PyTorch、F5-TTS 和模型，完成后自动启动 9881。

没有语音服务时文字对话与动作仍可用。F5 停顿：句间 0.34s，逗号/顿号后 0.18s，哼/呵/哈/嘿/切/啧等语气词后 0.56s；括号中的内心话不读。碎碎念会朗读，气泡 9 秒；聊天气泡 18 秒。

## 数据与隐私

所有用户数据在本机：

```text
%APPDATA%\CharacterPet\
  home\dsh-pet\llm.json       对话后端配置
  home\dsh-pet\memory.json    对话记忆
  home\dsh-pet\main-config.jsonc  角色实例配置（解锁后写入）
  packs\                      角色包
  unlocked.json               已解锁形象
  activation.json             本机激活记录
  server.log                  桌宠服务日志
```

- 不收集遥测；对话内容只发往你配置的 DeepSeek/Ollama。
- 删除 `%APPDATA%\CharacterPet` 会清空记忆、解锁记录和角色包。
- 卸载：退出托盘程序，删除 `%LOCALAPPDATA%\Programs\CharacterPet`；数据目录可保留。

## 更新

- 新版安装包覆盖安装到同一目录，保留 `%APPDATA%\CharacterPet` 数据与解锁记录。
- 新形象/新皮肤会有独立解锁码；旧码不因更新失效。
- 更新前建议退出托盘程序。

## 已知限制

- 安装包不带基础角色；没有解锁码无法启动角色。
- 一码一机；换机需发布者重置，不提供自助换机。
- F5 语音为空机全量下载，首次安装依赖网络，尚未覆盖所有网络环境。
- 角色包加密和机器绑定只能提高门槛，无法绝对防止逆向；请勿公开传播解锁码。
- H3 / Wan2.2 本地视频工作流仍是研究项，未包含在安装包内。

## 许可与声明

- 本项目为私有分发；未经许可不得再分发安装包或角色资产。
- 上游 dsh-pet（MIT）、Electron（MIT）等第三方组件遵循各自许可；见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
- 角色相关素材仅用于本项目私人桌面宠物，不代表米哈游官方。
