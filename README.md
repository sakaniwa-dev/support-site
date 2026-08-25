# support-site

iPhone アプリ **残機 (ZANKI)** の公開サイト。GitHub Pages で配信している。

| URL | 中身 |
|---|---|
| https://sakaniwa-dev.github.io/support-site/ | アプリの紹介ページ |
| https://sakaniwa-dev.github.io/support-site/zanki/ | サポート／プライバシーポリシー |

`zanki/` の URL は App Store Connect の **サポートURL** と
**プライバシーポリシーURL** の両方に登録してある。**リンク切れにしないこと。**
公開後に切れると、アプリが取り下げられることがある。

## 構成

    index.html      紹介ページ
    zanki/index.html サポート／プライバシーポリシー
    assets/         アプリのスクリーンショットとアイコン

外部リソースは読み込んでいない。1ファイルに CSS を同梱した素の HTML。
ダークモードは `prefers-color-scheme` に追従する。

## 公開されたら

`index.html` の「使ってみる」セクションに

```html
<!-- 公開されたら下のボタンを App Store のリンクに差し替える -->
```

というコメントがある。そこに App Store のリンクを足し、
ヒーローの `App Store 審査中` バッジを消す。

## スクリーンショットの差し替え

アプリ側リポジトリの `screenshots/` にある 1320×2868 の原本を、
横 660px に縮めて `assets/` に置いている。

```bash
sips -Z 660 ../zanki/screenshots/01-home.png --out assets/01-home.png
```
