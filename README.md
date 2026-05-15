# 滑輪與輪軸互動教學

這是一個依據國小自然六下單元「滑輪與輪軸」重點重新整理的單頁互動教學網頁。

主要檔案：

- `index.html`：可直接發布到 GitHub Pages 的互動網頁
- `build_interactive_lesson.py`：可重跑產生 `index.html` 的 Python 程式
- `optimized_prompt.md`：本次任務使用的最佳化提示詞

## Email 驗證碼登入

GitHub Pages 是靜態網站，不能自己安全寄送 email 或保存驗證碼。本頁已加入 Supabase Email OTP 登入流程；要讓它真的寄出驗證碼，請完成以下設定：

1. 建立 Supabase 專案。
2. 到 Supabase Auth 的 email template，把登入信件內容設為包含 `{{ .Token }}`，這樣會寄出一次性驗證碼。
3. 在 `index.html` 中填入：

```js
const SUPABASE_URL = "你的 Supabase Project URL";
const SUPABASE_ANON_KEY = "你的 Supabase anon public key";
```

完成後推送到 GitHub Pages，使用者必須輸入自己的電子郵件與信中的驗證碼，才能進入教材頁面。
