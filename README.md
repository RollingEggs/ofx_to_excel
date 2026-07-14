# OFX → Excel 変換ツール

OFXファイル（銀行明細）をブラウザ上で表に変換し、Excelへタブ区切りで貼り付けできるWebアプリです。
すべての処理はブラウザ内で完結し、ファイルがサーバーに送信されることはありません。

## 使い方

1. OFXファイル（`.ofx` / `.qfx`）をドラッグ＆ドロップ、またはクリックして選択
2. 取引明細が表として表示されます
3. 表を選択して `Ctrl+C`（Mac: `⌘+C`）、または「表をコピー」ボタンでコピー
4. Excelで `Ctrl+V` するとタブ区切りのセルに貼り付けられます

「CSVで保存」ボタンから TSV ファイルとして書き出すこともできます。

## 表示項目

| 列 | OFXフィールド |
|----|--------------|
| 日付 | `DTPOSTED` |
| 種別 | `TRNTYPE`（日本語に変換） |
| 金額 | `TRNAMT` |
| 名称 | `NAME` |
| 摘要 | `MEMO` |
| 取引ID | `FITID` |

## GitHub Pages での公開

このリポジトリは静的な `index.html` のみで動作します。

**方法A: ブランチから公開（手動）**
1. リポジトリの **Settings → Pages** を開く
2. **Source** で「Deploy from a branch」を選択
3. **Branch** を `main`、フォルダを `/ (root)` に設定して保存
4. 数分後 `https://<ユーザー名>.github.io/ofx_to_excel/` で公開されます

**方法B: GitHub Actions（自動）**
`main` ブランチへ push すると `.github/workflows/deploy-pages.yml` により自動デプロイされます。
初回のみ **Settings → Pages → Source** で「GitHub Actions」を選択してください。
