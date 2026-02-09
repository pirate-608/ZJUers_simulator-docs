# 产品文档项目

这是 ZJUers_simulator 用户手册的源代码仓库。文档站点通过 MkDocs 构建，并自动部署到 GitHub Pages。

## 🚀 快速开始

### 前提条件
*   Python 3.8+
*   pip
*   Git

### 本地开发与预览
1.  **克隆仓库**:
    ```bash
    git clone https://github.com/your-org/your-docs-repo.git
    cd your-docs-repo
    ```
2.  **安装依赖**:
    ```bash
    pip install -r requirements.txt
    ```
3.  **启动本地服务器**:
    ```bash
    mkdocs serve
    ```
    浏览器访问 `http://127.0.0.1:8000` 即可实时预览。

## 📁 项目结构
```
your-docs-repo/
├── docs/                    # 所有文档内容（.md文件）
├── .github/workflows/      # CI/CD 自动化部署配置
│   └── deploy.yml
├── mkdocs.yml              # MkDocs 主配置文件
├── requirements.txt        # Python 依赖列表
├── README.md               # （你正在看的文件）
├── LICENSE                 # 项目许可证
└── CNAME                   # （可选）自定义域名配置
```

## ✍️ 写作指南
*   所有文档内容请放在 `docs/` 目录下。
*   使用 MkDocs Material 主题支持的扩展语法，如注释框：
    ````markdown
    !!! note
        这是一个提示信息。
    ````
*   图片等静态资源请放在 `docs/assets/` 目录，并使用相对路径引用：`![描述](assets/image.png)`。

## 🔄 发布流程
文档发布已实现**全自动化**：
1.  将更改推送（`git push`）到 `main` 分支。
2.  GitHub Actions 将自动运行（见 `.github/workflows/deploy.yml`）。
3.  构建产物将自动部署到 `gh-pages` 分支，并更新线上站点。

> **重要**：切勿手动修改 `gh-pages` 分支。

## 🌐 站点信息
*   **线上地址**：[https://docs.yourdomain.com](https://docs.yourdomain.com)
*   **GitHub Pages 设置**：在仓库的 **Settings > Pages** 中查看。
*   **自定义域名**：通过根目录的 `CNAME` 文件管理。

## 🐛 故障排查
| 问题 | 可能原因 | 解决方案 |
| :--- | :--- | :--- |
| `mkdocs serve` 失败 | 依赖未安装或版本不对 | 1. 运行 `pip install -r requirements.txt` <br> 2. 确认 Python 版本为 3.8+ |
| 推送后站点未更新 | GitHub Actions 运行失败 | 1. 在仓库的 **Actions** 标签页查看日志 <br> 2. 检查 `.github/workflows/deploy.yml` 语法 |
| 自定义域名无法访问 | DNS 未生效或 CNAME 未设置 | 1. 确认 `CNAME` 文件已提交且内容正确 <br> 2. 等待 DNS 完全生效（最多24小时） |

## 🤝 如何贡献
欢迎通过 Issue 报告问题或通过 Pull Request 改进文档。
1.  Fork 本仓库。
2.  创建功能分支 (`git checkout -b feat/your-feature`)。
3.  提交更改 (`git commit -m 'Add some feature'`)。
4.  推送分支 (`git push origin feat/your-feature`)。
5.  开启一个 Pull Request。