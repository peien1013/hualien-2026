# 2026 花蓮宜蘭行程查詢

團員輸入姓名即可查詢自己的車票、住宿、接駁與繳費資訊。

- **前台**：靜態網頁，放在 GitHub Pages
- **後台**：Google Apps Script（JSONP API）＋ Google 試算表

## 為什麼放 GitHub Pages

Apps Script 的網頁是包在跨網域 iframe 裡執行，Facebook / LINE / IG 的
App 內建瀏覽器會擋掉，客人點連結只會看到空白畫面。
改成靜態網頁後，任何瀏覽器都能正常開啟。

## 維護

- 改畫面 → 編輯 `index.html` → commit / push（GitHub Pages 自動更新）
- 改資料（車次、名單、費用）→ 直接改 Google 試算表，前台即時反映
- 後端 API 網址寫在 `index.html` 的 `API_URL`

## 2026-10-10 改成跟正式版一樣

- `index.html` ＝ Apps Script 正式版查詢頁（/exec 的 userHtml）原樣，`<head>` 後面多一段「GitHub Pages 版相容層」：`google.script.run` → JSONP、`google.script.url.getLocation` 讀這頁網址的 `?k=`。
- 正式版查詢頁改了之後要重做這一頁再 push（不然 GitHub 版會停在舊畫面，手機會跑版）。
