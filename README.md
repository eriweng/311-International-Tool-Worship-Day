# 專案名稱：311 工具工作坊活動網頁 (March 11 Tool Workshop)

本專案為公司官網所屬的活動專題頁面，包含多語系支援、互動式元件（Slider/Buttons）以及故事導覽功能。

活動首頁 https://www.kingtony.com/2026_Ktday/march11-tool-workship-day.php
社群故事 https://www.kingtony.com/2026_Ktday/story_page.html?utm_source=311-Activity&utm_medium=btn

## 📂 目錄結構說明

```text
├── img/                # 靜態圖片資源
│   ├── frames/         # 動畫或特定框架圖片
│   ├── icon/           # 圖示檔案
│   ├── KT logo-03.png  # 品牌標誌
│   ├── hero_banner.png # 首頁大圖
│   └── sketch_xx.png   # 草圖或設計稿元件
├── js/
│   └── i18n.js         # 多語系切換邏輯核心
├── lang/               # 多語系語系檔 (JSON 格式)
│   ├── cn.json         # 繁體/簡體中文
│   ├── en.json         # 英文
│   ├── jp.json         # 日文
│   └── ... (共 13 國語系)
├── style/              # 樣式表
│   ├── zz-btn.css      # 按鈕組件樣式
│   └── zz-slider.css   # 輪播圖組件樣式
├── march11-tool-workship-day.php # 活動主程式入口
├── story_page.html     # 故事介紹頁面
├── update_lang_files.py # 語系檔案自動化更新腳本
└── .gitignore          # Git 忽略清單

```

---

## 🚀 主要功能與技術細節

### 1. 多語系支援 (Internationalization)

專案具備強大的多語系擴充能力，目前支援 13 種語言（包含 ar, br, cn, en, es, fr, hu, jp, ko, pl, ru, th, vi）。

* **核心控制**：由 `js/i18n.js` 負責偵測瀏覽器語系或使用者切換，並載入對應的 `lang/*.json`。
* **語系維護**：若需大量修改語系內容，可使用 `update_lang_files.py` 進行自動化處理。

### 2. 頁面組件

* **活動主頁**：`march11-tool-workship-day.php` 整合了工具工作坊的報名與資訊。
* **故事頁面**：`story_page.html` 用於展示品牌故事或工作坊背景。
* **UI 組件**：樣式已模組化，`zz-slider.css` 負責處理頁面中所有滑動切換的視覺效果。

---

## 🛠 維護與開發指南

### 更新語系檔

1. 修改 `lang/` 資料夾下對應的 `.json` 檔案。
2. 若有新增欄位，請確保所有語言的 JSON 檔案皆有同步對應的 Key。
3. （可選）執行 `python update_lang_files.py` 以確保語系檔案格式一致性。

### 圖片資源規範

* 所有新上傳的產品圖片建議放在 `img/` 根目錄，並遵循 `名稱_lg.png` 的命名規範（例如：`Torque_Wrench_lg.png`）。
* 圖示類請統一放入 `img/icon/`。

---

## ⚠️ 注意事項

* **PHP 環境**：主入口為 `.php` 檔案，請確保伺服器環境支援 PHP 解析。
* **路徑引用**：在 HTML/PHP 中引用資源時，請使用相對路徑以確保在官網子目錄下能正常顯示。
