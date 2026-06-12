# API Key 安全设置指南

API Key 是你访问各服务的密码，不应明文出现在项目文件中。
请按以下步骤将 Key 存入操作系统，只有你本机可以读取。

---

## Mac 用户

### 第一步：打开终端
Spotlight 搜索"终端"或"Terminal"，打开。

### 第二步：写入环境变量
每个 Key 运行一行命令（把引号内替换成你的真实 Key）：

```bash
# MiniMax
echo 'export MINIMAX_API_KEY="sk-xxxxxxxx"' >> ~/.zshrc
echo 'export MINIMAX_GROUP_ID="123456789"' >> ~/.zshrc

# 图片生成（按你使用的服务填写）
# echo 'export JIMENG_API_KEY="你的key"' >> ~/.zshrc

# 视频生成（按你使用的服务填写）
# echo 'export KLING_API_KEY="你的key"' >> ~/.zshrc
```

### 第三步：使其立即生效
```bash
source ~/.zshrc
```

### 第四步：验证（可选）
```bash
echo $MINIMAX_API_KEY
```
如果输出了你的 Key，说明设置成功。

### 第五步：重启 Claude Code
环境变量设置后，重启 Claude Code 才能读取到新变量。

---

## Windows 用户

### 方法一：图形界面（推荐新手）

1. 按 `Win + S`，搜索"环境变量"
2. 点击"编辑系统环境变量"
3. 在弹出窗口右下角点击"环境变量"按钮
4. 在"用户变量"区域点击"新建"
5. 变量名填写（例）：`MINIMAX_API_KEY`
6. 变量值填写你的真实 Key
7. 点击确定，重复以上步骤添加其他 Key
8. **重启 Claude Code 后生效**

### 方法二：命令行（PowerShell）

```powershell
[System.Environment]::SetEnvironmentVariable("MINIMAX_API_KEY", "你的key", "User")
[System.Environment]::SetEnvironmentVariable("MINIMAX_GROUP_ID", "你的groupid", "User")
```

重启 Claude Code 后生效。

---

## 安全提示

- ✅ 环境变量只存在你本机，不会随项目文件传播
- ✅ `API_Config.md` 只存变量名，不存 Key 本身，可以安全分享
- ❌ 不要把 Key 直接粘贴到 `API_Config.md` 或对话截图里
- ❌ 不要把包含 Key 的 `.zshrc` 截图发给别人

---

## 设置完成后

回到 `_Config/API_Config.md`，将对应服务的状态改为 `✅ 已配置`，
下次制作决策链会出现 **D · 使用已存配置，直接调用** 选项。
