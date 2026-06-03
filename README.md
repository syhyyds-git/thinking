# HTML Experiments GitHub Pages 发布包

这个目录就是你给的 README 里那套方案：把多个 HTML 结果页放进 `_experiments/`，push 后自动生成首页目录并部署到 GitHub Pages。

## 当前包含

- `_experiments/icml_2026_agent_repo_browser.html`：ICML 2026 LLM Agent 论文仓库浏览器。
- `scripts/gen_index.py`：扫描 `_experiments/*.html`，生成根目录 `index.html`。
- `.github/workflows/deploy.yml`：GitHub Actions 自动部署配置。
- `.nojekyll`：避免 GitHub Pages 用 Jekyll 处理静态文件。

## 怎么用

1. 在 GitHub 新建一个仓库，例如 `paper-html-browser`。
2. 把本目录里的所有文件提交到仓库根目录。
3. 进入仓库 `Settings -> Pages`。
4. `Build and deployment -> Source` 选择 `GitHub Actions`。
5. push 到 `main` 后，Actions 会自动运行并部署。

部署成功后，访问：

```text
https://<你的 GitHub 用户名>.github.io/<仓库名>/
```

首页会列出 `_experiments/` 里的所有 HTML 页面。

## 添加新页面

把新的 HTML 文件放进 `_experiments/`，并在文件开头加：

```html
<!-- index: 页面标题 | 2026-06-03 | 页面描述 -->
```

之后 push，首页会自动出现这个页面。

## 本地测试

```bash
python scripts/gen_index.py
```

然后打开根目录下生成的 `index.html`。
