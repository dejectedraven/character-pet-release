# 安装与首次启动

## 1. 下载与安装

- 下载 `CharacterPet-Setup-0.1.0.exe`。
- 双击运行；SmartScreen 提示未知发布者时选“更多信息 → 仍要运行”。
- 安装位置：`%LOCALAPPDATA%\Programs\CharacterPet`；自动创建桌面/开始菜单快捷方式并启动。
- 不需要管理员权限，不写 Program Files / 系统目录。

## 2. 解锁码

- 首次启动输入发布者提供的解锁码。
- 一个码对应一个形象；验证通过后写本机 `%APPDATA%\CharacterPet\unlocked.json`。
- 不会保存明文；卸载/清除数据后需重新输入。
- 新形象从托盘“解锁新形象…”输入新的独立码。

## 3. 对话后端

- 默认 DeepSeek API：填 Key（`sk-...`）、模型 `deepseek-chat`、Base URL `https://api.deepseek.com`。
- 或本机 Ollama：启动 Ollama → 检测 → 选/填模型。
- 或“暂不配置，直接启动”：对话关闭，动作/动画可用；托盘“对话 / API 设置”可恢复。

## 4. 托盘与退出

- 托盘菜单：对话 / API 设置、解锁新形象、打开数据目录、退出。
- 退出托盘程序后桌宠窗口与服务一起退出。
- 数据目录：`%APPDATA%\CharacterPet`。

## 5. 语音（可选）

发布包不含 F5-TTS/Torch。需要角色语音时，按 `VOICE.md`/项目方提供的语音服务说明，
在本机启动 F5-TTS（默认 9881）。没有语音服务时文字对话与动作仍可用。
