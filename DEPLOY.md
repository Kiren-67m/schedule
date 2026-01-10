# 🚀 GitHub Pages 部署指南

## 快速部署步骤

### 1. 创建 GitHub 仓库

1. 登录 [GitHub](https://github.com)
2. 点击右上角的 "+" → "New repository"
3. 填写仓库信息：
   - **Repository name**: 例如 `course-schedule-manager`
   - **Description**: 课程表管理系统
   - **Visibility**: Public（公开，才能使用免费 GitHub Pages）
   - **不要**勾选 "Initialize this repository with a README"（因为我们已经有了文件）

### 2. 上传文件到 GitHub

#### 方式一：使用 GitHub 网页界面

1. 在新建的仓库页面，点击 "uploading an existing file"
2. 将 `package` 文件夹中的所有文件拖拽到上传区域：
   - `index.html`
   - `standalone.html`
   - `README.md`
   - `README_CN.md`
   - `README_EN.md`
   - `LICENSE`
   - `.gitignore`
3. 在底部填写提交信息，例如："Initial commit"
4. 点击 "Commit changes"

#### 方式二：使用 Git 命令行

```bash
cd package
git init
git add .
git commit -m "Initial commit: Course Schedule Manager"
git branch -M main
git remote add origin https://github.com/your-username/your-repo-name.git
git push -u origin main
```

### 3. 启用 GitHub Pages

1. 在仓库页面，点击 **Settings**（设置）
2. 在左侧菜单找到 **Pages**（页面）
3. 在 **Source**（源）部分：
   - 选择 **Deploy from a branch**
   - **Branch**: 选择 `main` 或 `master`
   - **Folder**: 选择 `/ (root)`（根目录）
4. 点击 **Save**（保存）

### 4. 访问您的网站

等待几分钟（通常 1-3 分钟），然后访问：
```
https://your-username.github.io/your-repo-name/
```

例如：`https://username.github.io/course-schedule-manager/`

## 📝 重要提示

- **首次部署可能需要几分钟时间**，请耐心等待
- **更新 README.md**：部署后，记得更新 `README.md` 中的 Live Demo 链接为您的实际 GitHub Pages URL
- **HTTPS**：GitHub Pages 自动提供 HTTPS 加密
- **自定义域名**（可选）：如果您有自己的域名，可以在 Settings → Pages 中设置 Custom domain

## 🔄 更新网站

每次您修改代码并推送到 GitHub 后，GitHub Pages 会自动重新部署（通常需要 1-3 分钟）。

```bash
git add .
git commit -m "Update: description of changes"
git push
```

## ⚠️ 注意事项

- 确保仓库是 **Public**（公开）的，才能使用免费的 GitHub Pages
- `index.html` 是 GitHub Pages 的入口文件，确保它在仓库的根目录
- 所有文件应该直接上传到仓库根目录，不需要嵌套文件夹

## 🐛 故障排除

### 网站显示 404

- 检查仓库是否为 Public
- 确认 `index.html` 在仓库根目录
- 等待几分钟后刷新（首次部署需要时间）

### 样式丢失或功能不工作

- 检查浏览器控制台是否有错误（F12）
- 确保 CDN 链接正常（Tailwind CSS, Alpine.js）
- 检查网络连接（首次加载需要联网）

### 更新后没有变化

- 清除浏览器缓存（Ctrl+Shift+R 或 Cmd+Shift+R）
- 等待 GitHub Pages 重新部署（1-3 分钟）
