# 店舗ヘルプ（iPad画面）

店舗の iPad から LINE WORKS の社員グループにヘルプを呼ぶ画面。GitHub Pages（https://pom-inc-jp.github.io/gas-lineworks-store-help-ipad/）で公開し、処理は店舗連絡Bot（pom-inc-jp/gas-lineworks-store-bot の GAS）が行う。

- **このリポジトリのファイルは直接編集しない。** 中身は gas-lineworks-store-bot の `tools/build-ipad-page.js`（storeBot_ipad.gs の IPAD_HTML から作る）と `tools/make-ipad-icons.py` で作って置く
- 合言葉もウェブアプリの URL もここには入っていない。iPad で開く URL の `#` の後ろ（g=ウェブアプリのID、k=合言葉 / s=QR の共有キー）にだけ入り、GitHub には送られない
- 公開リポジトリ（GitHub Pages を無料で使うため）。検索エンジンには出さない（noindex）

## ページ

- `index.html` … 全店舗のボタン
- `<slug>/index.html` … 店舗ごとのページ（その店舗のヘルプボタンと「スマホで続ける」だけ）。ホーム画面のアイコン（`<slug>/icon-180.png`）と名前（「○○ヘルプ」）も店舗ごと
  - recoco_shibuya（RECOCO渋谷）、casse（CASSE）、recoco_shimokita（RECOCO下北沢）、selphoto（セルフォト）、retopo_shibuya（RETOPO渋谷）
- `qr.html` … 各店舗のページの QR コード一覧（`#g=…&k=…` 付きで開く）。iPad のカメラで読み取ってホーム画面に追加する
- `img/` … 店舗ボタンの画像（LINE のリッチメニューから切り出したもの）
- `qrcode.js` … qrcode-generator 1.4.4（MIT License, Kazuhiko Arase）

## iPad への置き方

1. GAS（店舗連絡Bot）のエディタで storeBot_ipad.gs の showIpadUrl を実行し、ログの「QRコードの一覧」の URL を開く
2. 各店舗の iPad のカメラで、その店舗の QR を読み取る → Safari の共有 →「ホーム画面に追加」
3. QR には合言葉が入っている。店舗の iPad 以外に見せない。合言葉が漏れたら setupIpadToken で作り直し、置き直す

## 履歴

- 2026-10-22 GitHub Pages 版を作る（Google の注意書きの帯を出さないため）
- 2026-10-24 店舗ごとの表示（ロゴを小さく、縦横で余白なく広げる）
- 2026-11-03 店舗ごとのページ・アイコン・QR 一覧。pom-inc-jp に移管し、名前を gas-lineworks-store-help-ipad に
