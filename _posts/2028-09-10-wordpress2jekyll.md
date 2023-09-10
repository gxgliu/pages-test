---
title: WordPressからJekyll（Github Pages）への移行手順
date: 2023-09-10 13:00:00 +0900
layout: post
permalink: /2023/09/10/wordpress-to-jekyll/
catetories:
  - IT
tags:
  - Jekyll
---

## 概要
AWS EC2で構築したWordPressを、github.ioのpagesに移行したい。
理由は、毎月2000円台の出費がかかることに対し、投稿頻度や閲覧数はそれほど多くないため、コスパを検討した上で移行を決めた。

## 移行する上での参考資料
+ [Jekyllの使い方 GitHub Pagesを使ってブログサイトを公開する方法](https://simple-it-life.com/2020/08/16/migrate-blog-to-github/)
  + 参考になるポイント
    + 公開するには <user>.github.io という名前のリポジトリを作成すること。
    + 各ページの下にgoogle adsenseのコンテンツを追加するには、以下のようにするといい
      ```
      <% include google-adsense-content.html %>
      ```
    + 下書き（ドラフト）やPrivateとして公開したくないものは、_drafts/ディレクトリにファイルを置けばよい。
    + ドラフトのファイルをローカルPCで動作確認したい場合は、以下のようにビルドすればいい。
      ```
      $ jekyll s --drafts
      ```
    + .gitignoreに_draftsを書くのを忘れずに。
  + [Imgur API を使ってサクッと画像アップロードしてみた](https://pisuke-code.com/web-basic-usage-of-imgur-api/)
    + 参考になるポイント
      + 画像をアップロードするサンプルコード（Javescript）
      + jonsのレスポンス形式（そこから、アップロード先のURLを取得することが可能） 

## 作業手順
### リポジトリ作成
別のgithub.comのuserで、<user>.github.ioというリポジトリを作成した。
![image](https://github.com/gxliu28/pages-test/assets/6185457/1d24cfe9-c058-45b2-bc1a-ebc2117c6273)

