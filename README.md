# apps.us-cloud.uk

SchaeferAnjon 的软件总站。首屏是一块小桌面，按一天里的钟点轮流演五个软件（MeetCaption、TypeRight、GetNewWord、ParaRead、Ask Free），访客点过就停；下面是一行一个的清单，带下载和官网入口。

- 页面在 `site/`，一个 `index.html` 加每个软件一个图标，不用构建。下载按钮打开时去 GitHub 接口取各软件最新一版的文件，取不到就指向发布页。
- 推到 main 后 `.github/workflows/pages.yml` 发到 GitHub Pages（schaeferanjon.github.io/apps），服务器上 cloudflared 把 apps.us-cloud.uk 转给本机 Caddy，Caddy 再转到 Pages。
- 加一个软件：在 `site/index.html` 的 `APPS`、`URLS`、`IC`、`ORDER`、`TIME`、`DEMO` 和两种语言的 `T`（`c.`、`t.`、`m.` 三句）里各加一项，给它一张墙纸（`.wp[data-w]`）和光的位置（`.desk[data-t] .sun`），照 `demoGNW` 写一个演示，再放一个 160×160 的图标；`.rail` 的列数跟着软件数改。安装包名带版本号的（ParaRead、TypeRight），在页尾加一行 `latest(...)`，按文件名认出最新一版。
