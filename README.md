# Google DevFest Workshop 网站

这是一个关于 Chrome DevTools MCP Server 的 Google DevFest Workshop 活动官网。

## 部署说明

### GitHub 认证方式

#### 方式 1：使用 Personal Access Token（推荐）

1. **创建 Token：**
   - 访问：https://github.com/settings/tokens
   - 点击 "Generate new token" → "Generate new token (classic)"
   - 设置名称：`luki-dev-deploy`
   - 选择权限：勾选 `repo`（完整仓库访问权限）
   - 点击 "Generate token"
   - **重要：立即复制 token**（只显示一次）

2. **使用 Token 推送代码：**
   ```bash
   git push -u origin main
   ```
   - 用户名：输入您的 GitHub 用户名
   - 密码：输入刚才复制的 token（不是您的 GitHub 密码）

#### 方式 2：使用 SSH 密钥

如果您已配置 SSH 密钥：

```bash
git remote set-url origin git@github.com:lukidesign/luki-dev.git
git push -u origin main
```

#### 方式 3：通过浏览器界面上传

1. 访问：https://github.com/lukidesign/luki-dev
2. 点击 "uploading an existing file"
3. 拖拽所有文件到页面
4. 填写提交信息并提交

### 启用 GitHub Pages

推送代码后，需要启用 GitHub Pages：

1. 访问仓库设置：https://github.com/lukidesign/luki-dev/settings/pages
2. 在 "Source" 部分选择：
   - Source: `GitHub Actions`
3. 保存设置

GitHub Actions 工作流会自动部署网站到 GitHub Pages。

## 文件结构

```
luki-dev/
├── index.html          # 首页
├── gdg-devfest.html    # GDG & DevFest 介绍页
├── devtools-mcp.html   # DevTools MCP 介绍页
├── about.html          # 个人介绍页
├── styles.css          # 样式文件
├── script.js           # JavaScript 文件
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Actions 部署工作流
└── README.md           # 本文件
```

## 本地开发

启动本地服务器：

```bash
python3 -m http.server 8000
```

然后访问：http://localhost:8000

