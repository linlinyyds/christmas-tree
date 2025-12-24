# 圣诞树网页配置指南

## 功能说明

圣诞树页面现在包含两个主要功能：

### 1. 背景音乐
- 页面加载时自动播放圣诞音乐《Christmas Is All Around》（初始静音）
- 左下角音乐控制器可以：
  - 播放/暂停音乐
  - 调节音量
  - 快速静音/取消静音
- 页面会提示用户点击解除静音以享受音乐

### 2. 发送祝福
- 点击右上角的 "Send Blessing" 按钮
- 填写他们的姓名（可选）和祝福内容
- 提交后，祝福将通过邮件发送到您的邮箱

---

## 音乐功能配置

### 准备音乐文件

1. **下载音乐文件**
   - 下载《Christmas Is All Around》的 MP3 文件
   - 推荐来源：
     - YouTube to MP3 转换器
     - 免费音乐库（如 Free Music Archive）
     - 购买正版音乐

2. **重命名文件**
   - 将 MP3 文件重命名为：`christmas-is-all-around.mp3`
   - 或者，如果使用其他名称，需要修改 `index.html` 第 490 行的文件名

3. **放置文件**
   - 将 `christmas-is-all-around.mp3` 文件放在与 `index.html` 相同的目录下

   ```
   christmas-tree/
   ├── index.html
   ├── christmas-is-all-around.mp3  ← 音乐文件放这里
   ├── SETUP.md
   └── ...
   ```

### 使用其他音乐

如果想使用其他圣诞歌曲，修改 `index.html`：

1. 找到第 490 行：
   ```html
   <source src="christmas-is-all-around.mp3" type="audio/mpeg">
   ```
   将文件名改为您的音乐文件名

2. 找到第 502 行：
   ```html
   <span class="music-info">Christmas Is All Around</span>
   ```
   修改显示的歌曲名称

### 音乐功能特点

- ✅ 自动播放（符合浏览器政策，初始静音）
- ✅ 循环播放
- ✅ 音量控制
- ✅ 播放/暂停切换
- ✅ 响应式设计，移动端友好

---

## 祝福功能配置

## 配置步骤

### 1. 注册 Formspree 账号

1. 访问 [Formspree](https://formspree.io/)
2. 点击 "Sign Up" 注册一个免费账号
3. 使用您的邮箱进行注册（这个邮箱将接收所有的祝福）

### 2. 创建表单

1. 登录后，点击 "+ New Form" 创建新表单
2. 输入表单名称，例如：`Christmas Blessings`
3. 创建后，您会得到一个表单端点，格式类似：
   ```
   https://formspree.io/f/xyzabc123
   ```

### 3. 更新 index.html

打开 `index.html` 文件，找到第 275 行左右的表单代码：

```html
<form id="blessingForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

将 `YOUR_FORM_ID` 替换为您在步骤 2 中获得的表单 ID。

例如，如果您的表单端点是 `https://formspree.io/f/xyzabc123`，则修改为：

```html
<form id="blessingForm" action="https://formspree.io/f/xyzabc123" method="POST">
```

### 4. 测试功能

1. 在浏览器中打开 `index.html`
2. 点击右上角的 "Send Blessing" 按钮
3. 填写测试信息并提交
4. 检查您的邮箱，应该会收到来自 Formspree 的邮件

### 5. Formspree 设置（可选）

在 Formspree 控制台中，您可以：

- **自定义邮件主题**: Settings → Email Subject
- **添加自动回复**: Settings → Autoresponder（给发送祝福的人自动回复感谢邮件）
- **添加垃圾邮件过滤**: Settings → Spam Filtering
- **自定义成功页面**: Settings → Redirect URL（可选，当前使用的是弹窗提示）

## 免费套餐限制

Formspree 免费套餐每月可接收 50 条消息，对于个人圣诞祝福页面完全够用。

如果需要更多容量，可以升级到付费套餐。

## 隐私说明

- 所有祝福只会发送到您配置的邮箱
- 祝福不会在网页上公开显示
- Formspree 会安全地处理表单数据

## 故障排除

### 提交后显示错误

1. 检查 `index.html` 中的表单 ID 是否正确
2. 确保您的网络连接正常
3. 检查 Formspree 账号是否已激活

### 没有收到邮件

1. 检查邮箱的垃圾邮件/垃圾箱
2. 确认 Formspree 表单设置中的邮箱地址正确
3. 在 Formspree 控制台的 Submissions 页面查看是否收到提交

## 技术支持

如有问题，请访问：
- Formspree 帮助文档：https://help.formspree.io/
- Formspree 支持：https://formspree.io/support

---

祝您圣诞快乐！🎄✨
