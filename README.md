# apps.us-cloud.uk

SchaeferAnjon 的软件总站：MeetCaption、Ask Free、GetNewWord 各一张卡，带演示动画、下载和官网入口。

- 页面在 `site/`，一个 `index.html` 加三个图标，不用构建。下载按钮打开时去 GitHub 接口取各软件最新一版的文件，取不到就指向发布页。
- 推到 main 后 `.github/workflows/pages.yml` 发到 GitHub Pages（schaeferanjon.github.io/apps），服务器上 cloudflared 把 apps.us-cloud.uk 转给本机 Caddy，Caddy 再转到 Pages。
- 加一个软件：在 `site/index.html` 的 `APPS`、`URLS`、`IC` 和两种语言的 `T` 里各加一项，再放一个 160×160 的图标。
