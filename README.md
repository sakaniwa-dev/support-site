# support-site

作ったアプリの公開ページ。GitHub Pages で配信している。

## 残機 (ZANKI)

| URL | 中身 |
|---|---|
| https://apps.apple.com/jp/app/id6804644002 | App Store |
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

## App Store

    https://apps.apple.com/jp/app/id6804644002

2026年8月26日公開。v1.0、無料、約1MB。掲載情報の確認:

```bash
curl -s "https://itunes.apple.com/lookup?id=6804644002&country=jp" | python3 -m json.tool
```

App Store のリンクは `zanki/index.html` に3箇所（ナビ／ヒーロー／使ってみる）、
`index.html` に1箇所ある。差し替えるときは全部直すこと。

## スクリーンショットの差し替え

アプリ側リポジトリ（`sakaniwa-dev/zanki`）の `screenshots/` にある
1320×2868 の原本を、横 660px に縮めて `zanki/assets/` に置いている。

```bash
sips -Z 660 ../zanki/screenshots/01-home.png --out zanki/assets/01-home.png
```
