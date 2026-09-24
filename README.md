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
`zanki/index.html` だけは Google Fonts（Dela Gothic One / M PLUS Rounded 1c / DotGothic16）を読み込む。
それ以外のページは外部リソースなしで、ダークモードは `prefers-color-scheme` に追従する。

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
