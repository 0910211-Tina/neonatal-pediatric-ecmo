# 小兒 ECMO 呼吸照護 — 研討會資源頁

115 學年度進階小兒學術研討會（2026/09/06）演講用的單頁網站。
講者：曾筠婷 呼吸治療師。

## 內容

| 區塊 | 說明 |
|---|---|
| 01 講義 | PDF 下載（尚未上傳，目前顯示「準備中」） |
| 02 考題 | 10 題線上作答，選完立刻顯示正確答案與解析，不計分 |
| 03 文獻 | 16 篇核心文獻 + 延伸引用，附 DOI 連結 |
| 04 滿意度 | Netlify Forms 收件，不需後端 |

## 檔案

```
index.html      整站（HTML + CSS + JS 全在這一支）
netlify.toml    Netlify 設定（靜態站，不需 build）
handout/        講義 PDF 放這裡
```

## 要放講義 PDF 的時候

1. 把 PDF 檔放進 `handout/`
2. 打開 `index.html`，找到 `<script>` 最上方的設定區：

```js
const HANDOUT = { url: "", label: "下載講義 PDF", meta: "" };
```

3. 填上路徑，例如：

```js
const HANDOUT = { url: "handout/小兒ECMO_2026_講義.pdf", label: "下載講義 PDF", meta: "PDF · 61 頁 · 8 MB" };
```

4. 推上 GitHub，Netlify 會自動重新部署。

`url` 是空字串時，網頁顯示「準備中」，不會出現壞掉的下載連結。

## 滿意度問卷（Netlify Forms）

表單名稱：`satisfaction`。第一次部署後要到 Netlify 後台
**Forms → Enable form detection** 打開偵測，之後回應會出現在 Forms 分頁，可匯出 CSV。

已包含 honeypot（`bot-field`）防機器人。表單以 AJAX 送出，送出後留在同一頁顯示感謝訊息。

> 測試時同一個 IP 連續送假資料常會被 Akismet 判為 spam，找不到回應請先看 Spam 分頁。

## 部署

靜態站，沒有 build 步驟、沒有任何 API 金鑰。

```
GitHub repo → Netlify「Import from Git」→ publish directory 留空（netlify.toml 已設為 "."）
```

推到 main 就自動重新部署；PR 會有 deploy preview。

## 授權與注意事項

考題與解析內容為講者教學用途。文獻引用請以原文為準——
解析中標註「⚠」的段落是引用時必須同時說明的但書，請勿單獨截圖流傳。
