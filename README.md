# 姚辉 · GitHub Pages 个人作品集（部署示例）

基于 [GameReach](https://github.com/usbfl/GameReach) 和 [TracePatch](https://github.com/usbfl/TracePatch) 的公开内容与用户提供的个人简历生成。

## 页面结构

- `index.html`：首页、精选项目、技术笔记入口、个人介绍。
- `projects/index.html`：项目列表。
- `projects/gamereach.html`、`projects/tracepatch.html`：项目介绍、架构步骤、边界、源码与报告链接。
- `writing/index.html`：博客/技术笔记列表。
- `writing/*.html`：两篇**示例文章**；发布前建议校对、改写，并补充自己的实验截图。
- `resume.html`：公开版简历（不含手机号、邮箱）。
- `assets/styles.css`：配色、字体、组件、响应式样式；`assets/main.js`：深浅色切换、手机导航。
- `.nojekyll`：跳过 Jekyll 特殊处理，按静态文件直接发布。

## 本地预览

本项目不需要 Python 后端、Node.js、付费 API、数据库或构建步骤。可直接双击 `index.html`；推荐在项目根目录运行：

```bash
python -m http.server 8000
```

然后浏览器打开 http://localhost:8000/ 。Windows 的 `py -3 -m http.server 8000` 也可以。

## 发布为个人主页 `https://usbfl.github.io/`

1. 在 https://github.com/new 创建名为 **`usbfl.github.io`** 的公开仓库（注意不是 `suiyi.github.io`）。
2. 将此文件夹中的**所有文件和目录（包括隐藏的 `.nojekyll`）**上传到新仓库的根目录。建议以 `main` 为默认分支。
3. 打开新仓库 `Settings > Pages > Build and deployment`。
4. `Source` 选择 **Deploy from a branch**，`Branch` 选择 **main**、**/(root)**，保存。
5. GitHub 处理部署后，在 `https://usbfl.github.io/` 查看；部署状态可在仓库的 `Actions` 或 `Settings > Pages` 中检查。

注意：`usbfl/suiyi.github.io` 已用于另一个 Alpha Lab 项目，不要覆盖它。现有 GameReach 和 TracePatch 仓库也无需复制源码到主页仓库。

## 更新方法

- 修改个人介绍：编辑 `index.html` 首页 Hero 部分。
- 修改简历：编辑 `resume.html`。
- 修改项目：编辑 `projects/gamereach.html` 或 `projects/tracepatch.html`。
- 添加文章：复制 `writing/agent-verified.html`，修改标题、正文和 meta description；并在 `writing/index.html` 新增文章链接。如果希望首页也展示，则在 `index.html` 的 `.note-grid` 加一项。
- 换主题：编辑 `assets/styles.css` 开头的 CSS 变量。
- 图片/插图：放入 `assets/`，以相对路径引用，避免在网页中暴露 API Key 或其它机密。
- 下载简历：如确定要公开 PDF，可自己筛选联系方式后，把 PDF 放入 `assets/resume-public.pdf`，再在 `resume.html` 添加链接。**不要直接上传含隐私信息的完整简历。**

## 项目演示链接说明

GameReach 与 TracePatch 的 README 分别包含 `https://usbfl.github.io/GameReach/` 与 `https://usbfl.github.io/TracePatch/` 等展示链接。本演示沿用这些链接，但**未确认这些链接当前从公网可访问**。若点击后 404，先检查各自仓库 `Settings > Pages` 是否开启，以及发布源是否设置为文档中的 `main /docs`。

## 设计取舍

主页承担叙事和导航；项目仓库承担源码与测试证据。使用纯 HTML/CSS/JS 是为了部署简单、长期维护成本低；未来文章增多后可迁移至 Astro、Hugo 等静态网站生成器。
