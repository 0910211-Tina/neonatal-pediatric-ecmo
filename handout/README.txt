把講義 PDF 放進這個資料夾，然後打開 index.html，
在 <script> 開頭的「設定區」填上檔名：

    const HANDOUT = { url: "handout/你的檔名.pdf", label: "下載講義 PDF", meta: "PDF · 61 頁" };

存檔、推上 GitHub，網站就會自動換成可下載的按鈕。
在填上檔名之前，網頁會顯示「準備中」，不會出現壞掉的連結。
