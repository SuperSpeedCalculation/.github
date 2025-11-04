# SuperSpeedCalculation 组织

欢迎来到 SuperSpeedCalculation 组织！

---

## 🔑 SSH 配置（RSA）

### 1. 生成 RSA 密钥

```bash
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
```

按提示操作：
- 保存位置：直接按 Enter 使用默认位置 `~/.ssh/id_rsa`
- 密码：可设置密码保护，或直接按 Enter 跳过

### 2. 启动 SSH 代理并添加密钥

**Windows (Git Bash):**
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

**macOS/Linux:**
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

### 3. 复制公钥

**Windows (PowerShell):**
```powershell
cat ~/.ssh/id_rsa.pub | clip
```

**macOS:**
```bash
pbcopy < ~/.ssh/id_rsa.pub
```

**Linux:**
```bash
cat ~/.ssh/id_rsa.pub
# 然后手动复制输出内容
```

### 4. 添加到 GitHub

1. 登录 GitHub → Settings → SSH and GPG keys
2. 点击 New SSH key
3. 填写 Title，粘贴公钥到 Key 字段
4. 点击 Add SSH key

### 5. 测试连接

```bash
ssh -T git@github.com
```

看到 `Hi username! You've successfully authenticated...` 即配置成功。

---

## 📦 Git 基本操作

### Clone（克隆仓库）

```bash
git clone git@github.com:SuperSpeedCalculation/<repo-name>.git
cd <repo-name>
```

### Pull（拉取最新代码）

```bash
git pull origin main
```

### Push（推送代码）

```bash
# 添加更改
git add .

# 提交更改
git commit -m "feat: 添加新功能"

# 推送代码
git push origin main
```

### 完整流程示例

```bash
# 1. 克隆仓库
git clone git@github.com:SuperSpeedCalculation/repo.git
cd repo

# 2. 拉取最新代码
git pull origin main

# 3. 修改代码后，提交并推送
git add .
git commit -m "feat: 添加新功能"
git push origin main
```

---

## 📝 Commit 规范

提交信息格式：`<type>: <subject>`

| 类型 | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat: 添加用户登录功能` |
| `fix` | Bug 修复 | `fix: 修复登录验证错误` |
| `docs` | 文档更新 | `docs: 更新 README` |
| `style` | 代码格式 | `style: 格式化代码` |
| `refactor` | 重构 | `refactor: 重构用户模块` |
| `perf` | 性能优化 | `perf: 优化查询性能` |
| `test` | 测试 | `test: 添加单元测试` |
| `chore` | 构建/工具 | `chore: 更新依赖` |

---

**最后更新：** 2025年

