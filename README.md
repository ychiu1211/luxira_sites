# Luxira Sites - Cloudflare Pages Deployment

這個專案包含三個靜態網站，每個都可以部署到 Cloudflare Pages。

## 網站列表

1. **luxira.net** - Cloudflare Pages 專案名稱: `luxira-net`
2. **sugarhub.tw** - Cloudflare Pages 專案名稱: `sugarhub-tw`
3. **sugartales.tw** - Cloudflare Pages 專案名稱: `sugartales-tw`

## 部署步驟

### 首次設定

在每個網站資料夾中，先安裝依賴：

```bash
# 進入網站資料夾
cd luxira.net  # 或 sugarhub.tw 或 sugartales.tw

# 安裝 wrangler
npm install
```

### 登入 Cloudflare

首次使用時需要登入：

```bash
npx wrangler login
```

### 部署網站

在任何一個網站資料夾中執行：

```bash
npm run deploy
```

這會將整個資料夾上傳到 Cloudflare Pages 並創建對應的專案。

## 自訂域名

部署完成後，你可以在 Cloudflare Pages 控制台為每個專案設定自訂域名：

1. 登入 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 選擇 **Workers & Pages**
3. 找到對應的專案 (luxira-net, sugarhub-tw, 或 sugartales-tw)
4. 進入 **Custom domains** 設定
5. 新增你的域名 (luxira.net, sugarhub.tw, 或 sugartales.tw)

## 注意事項

- 每次執行 `npm run deploy` 都會將網站部署到 main 分支
- 部署完成後會得到一個 `.pages.dev` 的暫時網址
- 設定自訂域名後，Cloudflare 會自動提供 SSL 憑證
