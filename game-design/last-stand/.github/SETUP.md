# 🚀 GitHub 仓库设置指南

## 当前状态

✅ 本地 Git 仓库已初始化
✅ SSH 密钥已生成
✅ 远程仓库已配置 (`git@github.com:18710111411/last-stand.git`)
❌ GitHub 仓库未创建 (需要老板手动创建)

---

## 📝 步骤 1: 在 GitHub 创建仓库

### 方式 A: 浏览器创建 (推荐)

1. 打开 https://github.com/new

2. 填写仓库信息：
   ```
   Repository name: last-stand
   Description: 🧟 丧尸末日生存塔防游戏 - 建造防御塔，指挥英雄，在丧尸潮中生存！
   Visibility: Public (公开) 或 Private (私有)
   ❌ 不要勾选 "Initialize with README"
   ```

3. 点击 **"Create repository"**

---

### 方式 B: 使用 GitHub CLI (需要先安装)

```bash
# 安装 GitHub CLI
brew install gh  # macOS
# 或
sudo apt-get install gh  # Linux

# 登录 GitHub
gh auth login

# 创建仓库
gh repo create last-stand --public --description "🧟 丧尸末日生存塔防游戏" --source=. --remote=origin --push
```

---

## 📝 步骤 2: 推送代码到 GitHub

仓库创建后，在本地执行：

```bash
cd /home/admin/.openclaw/workspace/game-design/last-stand

# 确认远程仓库
git remote -v

# 推送代码
git push -u origin main

# 查看状态
git status
```

---

## 📝 步骤 3: 验证推送

1. 打开 https://github.com/18710111411/last-stand

2. 确认文件已上传：
   - ✅ README.md
   - ✅ LICENSE
   - ✅ .github/ 文件夹
   - ✅ 01-world-setting.md 等文档

3. 检查 GitHub Actions：
   - 点击 **"Actions"** 标签
   - 确认 CI/CD 工作流运行

---

## 🔧 常见问题

### 问题 1: 权限错误

```
ERROR: Repository not found.
fatal: Could not read from remote repository.
```

**解决：**
- 确认 GitHub 仓库已创建
- 确认 SSH 密钥已添加到 GitHub (Settings → SSH and GPG keys)
- 测试 SSH 连接：`ssh -T git@github.com`

---

### 问题 2: SSH 密钥未添加

**解决：**
1. 复制公钥内容：
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. 打开 GitHub → Settings → SSH and GPG keys

3. 点击 **"New SSH key"**

4. 粘贴公钥内容，保存

---

### 问题 3: 分支名称冲突

```
error: failed to push some refs to ...
```

**解决：**
```bash
# 强制推送 (谨慎使用)
git push -f -u origin main

# 或者先拉取
git pull origin main --allow-unrelated-histories
git push -u origin main
```

---

## ✅ 完成检查清单

- [ ] GitHub 仓库已创建
- [ ] SSH 密钥已添加
- [ ] 代码已推送
- [ ] README 显示正常
- [ ] GitHub Actions 运行成功
- [ ] Issue 模板可用

---

## 🎯 下一步

仓库设置完成后：

1. **邀请协作者** (可选)
   - Settings → Collaborators → Add people

2. **配置 GitHub Pages** (可选)
   - Settings → Pages → 选择 main 分支
   - 用于展示游戏设定文档

3. **创建 Project** (推荐)
   - Projects → New project
   - 添加开发任务看板

4. **设置 Milestones**
   - Issues → Milestones → New milestone
   - 创建 MVP/Alpha/Beta/Release 里程碑

---

## 📧 需要帮助？

遇到问题请：
1. 检查本指南
2. 查看 GitHub 文档
3. 在 Issues 中提问

---

**🎮 准备好在 GitHub 上展示你的游戏了吗？**
