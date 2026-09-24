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
      index.html               紹介ページ（原本はアプリ側リポジトリの homepage/index.html）
      support/index.html       サポート／プライバシーポリシー
      assets/                  イラスト（WebP）・スクリーンショット（WebP）・アイコン

アプリごとに1ディレクトリ。CSS / JS を同梱した素の HTML。
全ページが残機の紹介ページと同じデザイン（黄緑 `#E0F352` × 墨 `#191E27`、ライトのみ）で、
外部から読み込むのは Google Fonts（Dela Gothic One / M PLUS Rounded 1c / DotGothic16）だけ。

**プライバシーポリシーの文面を変えるときは、`zanki/support/index.html` の最終更新日も改めること。**
見た目だけの変更なら日付はそのまま。

## App Store

    https://apps.apple.com/jp/app/id6804644002

2026年8月26日公開。v1.0、無料、約1MB。掲載情報の確認:

```bash
curl -s "https://itunes.apple.com/lookup?id=6804644002&country=jp" | python3 -m json.tool
```

App Store のリンクは `zanki/index.html` 末尾の `APP_STORE_URL` の1か所（ボタン3つがここを見る）と、
`index.html` に1箇所ある。差し替えるときは両方直すこと。

## 紹介ページの更新

原本はアプリ側リポジトリ（`sakaniwa-dev/zanki`）の `homepage/`。
向こうで直したら、`index.html` と `assets/*.webp` をこちらにコピーし、
サポートへのリンクを相対パスに戻す（原本は絶対URL、こちらは `support/#support` / `support/#privacy`）。
フッターの「ほかのアプリ」（`../`）はこちらにだけある。

```bash
cp ../zanki/homepage/assets/*.webp zanki/assets/
```

`icon.png` はこちらの 240px 版をそのまま使っている。
