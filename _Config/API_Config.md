# API 配置存档

> **安全说明**：本文件不存储任何 API Key 明文。
> Key 请存入操作系统环境变量（Mac：`~/.zshrc`，Windows：系统环境变量），
> 此文件只记录变量名和非敏感参数。
>
> 设置方法见：`_Config/API_Key_Setup_Guide.md`

---

## TTS / 配音

### MiniMax
- **状态**：未配置
- Endpoint：`https://api.minimaxi.com/v1/t2a_v2`
- 认证方式：Bearer Token
- API Key 环境变量名：`MINIMAX_API_KEY`
- 默认音色 (voice_id)：（填入你的 voice_id，可在 MiniMax 控制台查看）
- 默认语速 (speed)：1.0
- 默认音量 (vol)：1.0
- 接口模型：`speech-02-hd`
- 音频格式：mp3，32000Hz，128kbps，单声道
- output_format：url
- 备注：

---

## AI 图片生成

### 服务名（例：即梦 / DALL-E / Replicate）
- **状态**：未配置
- API Key 环境变量名：（例：`JIMENG_API_KEY`）
- Endpoint：
- 默认模型：
- 默认参数（尺寸、风格等）：
- 备注：

---

## AI 视频生成

### 服务名（例：可灵 / Runway / 即梦）
- **状态**：未配置
- API Key 环境变量名：（例：`KLING_API_KEY`）
- Endpoint：
- 默认模型：
- 默认参数：
- 备注：

---

## 配置完成后

1. 将对应服务的 `状态` 改为 `✅ 已配置`
2. 制作决策链将自动识别并显示 **D · 使用已存配置，直接调用**
3. 调用时 AI 从环境变量读取 Key，不会在对话或文件中显示真实值

