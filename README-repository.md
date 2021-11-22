# How to manage trendcreate.pages.dev repository

## 開発 FLOW

`main`branchは実際にWebに反映されるbranchとなります。  
deployは`main`branchの更新を [Cloudflare Pages](//pages.cloudflare.com/) が検知し自動で`gatsby build`を走らせサイトを更新してくれます。  
なので普段の開発は`main`branchから`develop`ブランチを切りこっちで開発を進めます。  
このrepositoryはただの小規模なWebサイトである為、`develop`branchに直接commitしても構いませんし、そこから更に`feature`branchを切って開発しても構いません。  
きりの良いところで`main`branchにプルリクを出し一通り変更箇所を確認するようにしてください。

## Pull Request について

自動で[package.json](/package.json)からversionを取得しversionのtagを付け[README.md](/README.md)のバージョンも更新する[Action](/.github/workflows/log_versions.yml)を設定している都合上、  
`main`branchへのプルリクを出す際は[package.json](/package.json)のversionを更新しとく必要があります。  
versionのフォーマットはnpmのフォーマットに従い`1.0.0`の様に3桁の形式とします。  
細かな更新や修正等の場合はマイナーバージョンを、新要素などの更新の場合は真ん中のバージョンを、大きな新要素や大幅な改修などはメジャーバージョンをincrementするようにします。  
またプルリクのtitleとbodyは[README.md](/README.md)にも書かれるため適切なtitle、bodyには更新した内容をすべて箇条書き(`-`を使用)で書きましょう。  
