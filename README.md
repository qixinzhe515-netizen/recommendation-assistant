# 推荐助手

这是一个移动端优先的网页 App。它和点餐 App 一样，先按静态网页运行，部署到 HTTPS 后可以在 iPhone Safari 里通过“分享 -> 添加到主屏幕”当作简单 App 使用。

## Run

```bash
python3 server.py
```

Then open:

```text
http://localhost:8787
```

On another device in the same home Wi-Fi, open the network URL printed by the server, for example:

```text
http://192.168.1.4:8787
```

That address is only for local Wi-Fi testing. For public testing, deploy to a public HTTPS host.

## Public Test Deployment

Recommended first stable deployment:

```text
GitHub Pages
```

Push this folder to a GitHub repository, then enable GitHub Pages for the repository. After deployment, testers can open the HTTPS URL on iPhone Safari and use Share -> Add to Home Screen.

This folder also includes `render.yaml` for a minimal Render deployment. Render will run:

```bash
python3 server.py
```

## 文件

- `index.html`：页面结构
- `styles.css`：视觉样式
- `app.js`：问答、推荐、分享逻辑
- `manifest.webmanifest`：Web App 配置
- `service-worker.js`：离线缓存和安装能力
- `icon.svg`：主屏幕图标
- `server.py`：本地和 Render 静态服务
- `render.yaml`：Render 部署配置

## 当前状态

- 页面分为问卷页、需求页、推荐商品页。
- 问卷答完后会进入“你需要什么”，问卷隐藏；左上角才显示“重新答题”。
- 推荐结果只展示 1 个商品、商品图、基础介绍和推荐原因。
- CSS/JS 使用固定版本号加载，避免手机浏览器看到旧脚本导致按钮失效。
- 已补齐 PWA 基础配置：manifest、icon、service worker、iPhone 主屏幕 meta。
- 已开始接入真实商品库：推荐结果优先展示真实商品标题、真实主图、购买链接；当前先覆盖鼠标和电动牙刷，后续继续扩充。
