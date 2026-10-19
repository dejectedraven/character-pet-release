# Character Pet

Windows 桌面 AI 角色桌宠。当前角色：散兵 Q 版。

> 这是**分发仓库**，只放安装包、安装说明、版本更新说明与许可声明；不包含源码。
> 解锁码由发布者单独提供，不在本页公开。

## 下载

- 最新安装包：[Releases](../../releases/latest)
- 当前版本：**v0.1.0**
- 文件：`CharacterPet-Setup-0.1.0.exe`（约 270MB）
- SHA256：`c9b802fab05ef033d4f09e24a9ae303a2b4202e8eabce7a79c674c7001e78ecc`
- 系统：Windows 10/11 x64；无需管理员权限；建议 4GB+ 内存、300MB+ 磁盘。

## 安装

1. 下载 `CharacterPet-Setup-0.1.0.exe`。
2. 双击运行。Windows SmartScreen 可能提示未知发布者，选择“更多信息 → 仍要运行”。
3. 安装到 `%LOCALAPPDATA%\Programs\CharacterPet`，自动创建桌面与开始菜单快捷方式并启动。
4. 安装包不安装服务，不写系统目录，不需要管理员权限。

## 第一次启动

### 1. 解锁码

首次启动必须输入解锁码。解锁码只做一次验证，之后记住；每个形象有独立解锁码。

- 输入后只验证本机强哈希，不保存明文。
- 成功后安装对应的基础形象包到 `%APPDATA%\CharacterPet\packs\`。
- 新形象/新皮肤使用新的独立解锁码；从托盘菜单“解锁新形象…”添加。

### 2. 对话后端

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

### 3. 启动后

- 主程序常驻系统托盘；桌宠是独立透明置顶小窗。
- 托盘菜单：对话 / API 设置、解锁新形象、打开数据目录、退出。
- 点桌宠打开右键菜单；可碎碎念、对话、拖动、点击互动。

## 语音

发布包**不内置** F5-TTS/Torch 模型，避免安装包过大。没有语音服务时，文字对话与动作仍可用。

需要角色语音时，在本机运行 F5-TTS 服务（默认 `127.0.0.1:9881`）；发布版默认连接 9881。
F5 语音的停顿已加长：句间 0.34s，逗号/顿号后 0.18s，哼/呵/哈/切/啧等语气词后 0.56s；括号中的内心话不会朗读。碎碎念也会朗读，气泡 9 秒；聊天气泡 18 秒。

## 数据与隐私

所有用户数据在本机：

```text
%APPDATA%\CharacterPet\
  home\dsh-pet\llm.json       对话后端配置
  home\dsh-pet\memory.json    对话记忆
  packs\                     形象包
  unlocked.json              已解锁形象
  server.log                 桌宠服务日志
```

- 不收集遥测；对话内容只发往你配置的 DeepSeek/Ollama。
- 删除 `%APPDATA%\CharacterPet` 会清空记忆、解锁记录和形象包。
- 卸载：退出托盘程序，删除 `%LOCALAPPDATA%\Programs\CharacterPet`；数据目录可保留。

## 更新

- 新版安装包覆盖安装到同一目录，保留 `%APPDATA%\CharacterPet` 数据与解锁记录。
- 新形象/新皮肤会有独立解锁码；旧码不因更新失效。
- 更新前建议退出托盘程序。

## 已知限制

- 0.1.0 只发布基础散兵形象；新形象的自动动画包格式仍在完善。
- sleep 动作暂时从动作池移除（文件保留，后续可恢复）。
- 离线解锁码是软门禁，不能替代服务端授权；请勿公开传播解锁码。
- H3 / Wan2.2 本地视频工作流仍是研究项，未包含在安装包内。
- 角色语音需要单独安装 F5-TTS；安装包不含模型。

## 许可与声明

- 本项目为私有分发；未经许可不得再分发安装包/角色资产。
- 上游 dsh-pet（MIT）、Electron（MIT）等第三方组件遵循各自许可；见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
- 角色相关素材仅用于本项目私人桌面宠物，不代表米哈游官方。
