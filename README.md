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
