# 皇·旗飘扬 RISE OF THE NINE EMPERORS — MV 发布 Landing Page

双溪大年斗母宫九皇大帝《皇·旗飘扬》MV 发布落地页。纯静态网站（HTML/CSS/JS），无需后端、无需构建工具，可直接部署到 Vercel。

## 网站内容

- 开场「敲钟入殿」点击页：点击后触发背景音乐播放，并进入正式页面（浏览器政策不允许网页一进入就有声音自动播放，这是业界通用的合规做法，效果等同于「一进站就有音乐」）
- Hero 区：封面图 + 标题
- 3 个按钮，点击后新分页打开 Google Drive：完整 MV 视频、音乐 MP3 下载、歌词图片
- 随喜打赏 / 功德善款区块，含 QR code
- 右下角小圆钮可随时静音 / 开声音

## 目录结构

```
mv-site/
├── index.html          ← 网站本体（所有 CSS/JS 都写在这一个文件里）
├── assets/
│   ├── cover.jpg        ← 封面图（Hero 背景）
│   ├── theme.mp3         ← 背景音乐（= MV 主题曲）
│   └── qr-donation.png   ← 打赏 QR code（目前是占位图，见下方说明）
└── README.md
```

## 上线前必做：换成你自己的打赏 QR code

`assets/qr-donation.png` 现在是一张占位图（写着「请替换 QR CODE」）。
把你真正的收款 QR code 图片改名成 **qr-donation.png**，覆盖掉这个文件即可，网页不用改任何代码。

## 部署方法：GitHub + Vercel（零代码基础也能跟着做）

### 第一步：把代码放上 GitHub

1. 打开 https://github.com/new ，新建一个 repository（例如取名 `sptbk-mv-9emperors`），Public 或 Private 都可以，不要勾选「Add a README」（我们已经有了）。
2. 在你电脑的终端机（Terminal / Git Bash）里，`cd` 进这个 `mv-site` 资料夹，然后执行：

   ```bash
   git init
   git add .
   git commit -m "皇·旗飘扬 MV landing page"
   git branch -M main
   git remote add origin https://github.com/<你的GitHub用户名>/sptbk-mv-9emperors.git
   git push -u origin main
   ```

   （如果你是从我这边收到的 zip 檔案，先解压，然后在解压出来的资料夹里跑上面这几行）

### 第二步：连接 Vercel 自动部署

1. 打开 https://vercel.com ，用你的 GitHub 账号登入（第一次会要求 Authorize）。
2. 点 **Add New → Project**。
3. 选择你刚刚推上去的 `sptbk-mv-9emperors` repo，点 **Import**。
4. Framework Preset 选 **Other**（因为这是纯静态网站，不需要 build），其他设定保持默认。
5. 点 **Deploy**，等大约 30 秒~1 分钟。
6. 部署完成后，Vercel 会给你一个网址，例如 `https://sptbk-mv-9emperors.vercel.app` —— 这就是可以直接分享出去的网站。

### 之后要更新内容怎么办？

以后只要修改 `mv-site` 资料夹里的文件（例如换 QR code、改文字），再执行：

```bash
git add .
git commit -m "更新内容"
git push
```

Vercel 会自动侦测到 GitHub 有新的 commit，自动重新部署，不用每次都手动操作。

### 绑定自己的网域（可选）

如果你有自己的网域（例如 `sptbk.org`），可以在 Vercel 项目的 **Settings → Domains** 里添加，然后照 Vercel 给的指示去你的网域服务商（如 GoDaddy / Namecheap）设定 DNS 就可以。

## Google Drive 权限提醒

网站上 3 个按钮连去的 Google Drive 文件，权限已经确认是「知道链接的任何人皆可查看」（anyone with the link – reader），一般访客点击可以直接看到 / 下载，不需要额外开权限。如果之后你把文件搬到别的资料夹或重新上传，记得再次确认分享设定还是「任何人可查看」，否则访客会看到「要求存取权限」的画面。
