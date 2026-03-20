# WezTerm — macOS 聽寫支援版本（Apple Silicon）

> 基於 [Erog38/wezterm feat/macos-dictation](https://github.com/Erog38/wezterm/tree/feat/macos-dictation) 分支的預編譯版本，加入 macOS 系統聽寫（Dictation）的 IMKit 整合支援。

**[English →](README.md)**

---

## ⚠️ 系統需求

- **僅支援 Apple Silicon Mac**（M1 / M2 / M3 / M4）
- Intel Mac（2020 年以前）**不支援**
- 建議 macOS 12 Monterey 以上

---

## ⬇️ 下載

前往 [**Releases**](https://github.com/swchen44/wezterm-macos-dictation/releases/latest) 下載 `WezTerm-macos-arm64.dmg`。

---

## 📦 安裝步驟

**1. 掛載並安裝**

雙擊 `.dmg` 檔案，將 `WezTerm.app` 拖入 `/Applications`。

**2. 解除 Gatekeeper 封鎖（必要）**

因為此版本沒有 Apple 開發者簽名，macOS 會擋住它。**開啟前必須先執行：**

```bash
xattr -cr /Applications/WezTerm.app
```

**3. 開啟**

雙擊 `/Applications/WezTerm.app` 即可。

---

## 🈳 中文顯示設定（建議）

建立 `~/.config/wezterm/wezterm.lua` 以正確顯示中文字符：

```bash
mkdir -p ~/.config/wezterm
```

```lua
local wezterm = require 'wezterm'

return {
  font = wezterm.font_with_fallback {
    'JetBrains Mono',
    'Heiti TC',   -- macOS 內建繁體中文字體
  },
  unicode_version = 14,
}
```

---

## 🎙️ 使用 macOS 聽寫功能

開啟 WezTerm 後，按 **連按兩下 `Fn` 鍵**（或鍵盤上的麥克風按鈕）啟動系統聽寫，即可語音輸入文字。

---

## ⚠️ 已知限制

| 限制 | 說明 |
|------|------|
| 僅支援 Apple Silicon | arm64 架構，Intel Mac 不支援 |
| 未經 Apple 簽名 | 需手動執行 `xattr -cr` 解除 Gatekeeper |
| 社群分支，非官方版 | 基於 feat/macos-dictation，尚未合併至 WezTerm 主線 |
| 聽寫語言 | 依賴系統設定中的聽寫語言，需在「系統設定 → 鍵盤 → 聽寫」中啟用 |

---

## 🔗 相關連結

- [原始碼分支：Erog38/wezterm feat/macos-dictation](https://github.com/Erog38/wezterm/tree/feat/macos-dictation)
- [WezTerm 官方文件](https://wezfurlong.org/wezterm/)
- [English README](README.md)
