# はしごマップ（hashigo-map.com）

はしごシリーズの入口ページ。`public/` をそのまま Cloudflare Pages の `hashigo-map` プロジェクトへ公開する（main への push で自動公開）。

## ドメイン構成

| URL | 中身 | Pages プロジェクト | 旧ドメイン（転送元） |
|---|---|---|---|
| hashigo-map.com | このポータル | hashigo-map | — |
| cinema.hashigo-map.com | たっぷりひたれ！はしごシネマ | hashigo-cinema | hashigo-cinema.com |
| museum.hashigo-map.com | ゆったりめぐれ！はしごミュージアム | bakuhatsu-art-museum | hashigo-museum.com |
| yose.hashigo-map.com | しびれろ！はしご寄席 | hashigo-yose | hashigo-yose.com |
| camp.hashigo-map.com | 燃やせ！はしごキャンプ | hashigo-camp | hashigo-camp.com |
| shop.hashigo-map.com | かいまわれ！はしごショッピング | hashigo-shop | — |

- 旧ドメインはパスを保ったままサブドメインへ 301 転送する。更新期限が来たら手放す
- ハイフンなしの転送用ドメイン（hashigocinema.com / hashigomuseum.com / hashigoyose.com）は更新しない
- pages.dev は Cloudflare Access で自分だけ閲覧可（他のはしごサイトと同じ設定）
- 全サイト noindex（`_headers`）

## 新しいはしごサイトを足すとき

1. Pages プロジェクトの「カスタムドメイン」に `○○.hashigo-map.com` を追加（DNS は自動）
2. そのサイトの `public/site-info.js` の `SITE_URL` を同じURLにする
3. このポータルの `public/index.html` にカードを1枚足す

## 初回だけ

リポジトリの Secrets に `CLOUDFLARE_API_TOKEN` と `CLOUDFLARE_ACCOUNT_ID` を登録（他のはしごサイトと同じ値）。
