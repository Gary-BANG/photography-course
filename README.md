# 光影手记 · Gary 的摄影课

面向 iPhone 17 Pro 初学者与 2026 年北加州旅行的个人摄影教程。15 节完整课程，5 个摄影概念实验、5 张旅行拍摄卡、理解题与本地练习本。深色界面与低强度流动极光背景，支持减少动态效果偏好。

## 直接使用

所有网站文件位于 `dist/`，采用原生 HTML、CSS 和 JavaScript 模块，无需安装依赖或构建。以静态服务器打开 `dist/` 即可：

```bash
python3 -m http.server 8000 --directory dist
```

访问 `http://localhost:8000`。不要直接双击 HTML 使用 `file://`，浏览器可能阻止模块脚本加载。

## GitHub Pages 部署

1. 新建你自己的 GitHub 仓库，将这些源码文件上传或推送到 `main` 分支。
2. 仓库 Settings → Pages → Build and deployment → Source 选择 **GitHub Actions**。
3. 仓库中的 `.github/workflows/pages.yml` 会在 main 推送后把 `dist/` 部署到 GitHub Pages。也可从 Actions 手动运行。
4. 在 GitHub Pages 显示的地址打开网站。资源使用相对路径，兼容项目子路径。

本交付没有替你创建 GitHub 账号下的新仓库，也没有修改既有仓库。当前在线演示通过 Sites 独立托管；下载包提供迁移到 GitHub Pages 的完整静态源码。迁移后浏览器记录不会自动转移。

## 文件

- `dist/index.html`：站点外壳与导航。
- `dist/styles.css`：响应式视觉、移动端与打印样式。
- `dist/app.js`：路由、实验室、答题进度、IndexedDB练习本、WebGL背景。
- `dist/lessons.js`：15节课程、场景卡与官方资料链接；从这里维护内容。
- `dist/assets/`：真实摄影图片、作者与许可证清单。
- `.github/workflows/pages.yml`：GitHub Pages自动部署。

## 数据与边界

学习进度保存在 localStorage，练习文字与照片保存在 IndexedDB。没有后端上传、照片AI分析、云同步或账户系统。浏览器清理、隐私模式、换设备或换域名可能让记录不可用。导出功能只导出文字JSON；重要原始照片应另行备份。

文件选择最多4张JPEG/PNG/WebP、单张不超过12MB。HEIC需要先导出为JPEG。相片预览采用浏览器对象URL，路由切换时释放。所有用户文本插入页面前做HTML转义。

实验室通过同一张真实照片的处理与图形叠加解释趋势：裁切不是实际光学换镜，亮度模拟不是精确传感器曝光，冷暖模拟不是Kelvin标定，运动球轨迹不是实拍。每个实验均就地标明。

背景是原创程序化WebGL极光/流动渐变，不是Navier–Stokes流体物理求解器。低更新频率、尺寸上限、隐藏标签暂停；可手动关闭，并响应prefers-reduced-motion。WebGL不可用时显示静态渐变。

## 图片与内容

图片来自Unsplash，原作、作者和许可记录见网站“照片与资料来源”与 `dist/assets/credits.json`。这些图片不是iPhone17 Pro的样张；篮球图片为Riverside外场，不是Chase Center。

设备参数与操作主要参考Apple官方文档，核实日期2026-10-31。在线手册可能滚动更新到新机型，维护内容时必须确认适用机型，不能把其他机型的功能移植为17 Pro原生功能。天气、月相、步道、场馆规定需要出发前再核实。

课程沿用对话中确定的15课路线。第一课初始标记为已学，第二课作为首次进入时的下一课；之后以当前浏览器的实际完成记录为准。理解题正确后可标记课程完成；练习勾选用于自我记录。
