# support-site

作ったアプリの公開ページ。GitHub Pages で配信している。

## 残機 (ZANKI)

| URL | 中身 |
|---|---|
| https://sakaniwa-dev.github.io/support-site/zanki/ | 紹介ページ |
| https://sakaniwa-dev.github.io/support-site/zanki/support/ | サポート／プライバシーポリシー |

**`zanki/support/` の URL は App Store Connect の サポートURL と
プライバシーポリシーURL の両方に登録する。リンク切れにしないこと。**
公開後に切れると、アプリが取り下げられることがある。

## 構成

    index.html                 アプリ一覧（入口）
    zanki/
      index.html               紹介ページ
      support/index.html       サポート／プライバシーポリシー
      assets/                  スクリーンショットとアイコン

アプリごとに1ディレクトリ。外部リソースは読み込んでいない。
CSS を同梱した素の HTML で、ダークモードは `prefers-color-scheme` に追従する。

## 残機が公開されたら

`zanki/index.html` の「使ってみる」セクションに

```html
<!-- 公開されたら下のボタンを App Store のリンクに差し替える -->
```

というコメントがある。そこに App Store のリンクを足し、
ヒーローの `App Store 審査中` バッジを消す。

## スクリーンショットの差し替え

アプリ側リポジトリ（`sakaniwa-dev/zanki`）の `screenshots/` にある
1320×2868 の原本を、横 660px に縮めて `zanki/assets/` に置いている。

```bash
sips -Z 660 ../zanki/screenshots/01-home.png --out zanki/assets/01-home.png
```
