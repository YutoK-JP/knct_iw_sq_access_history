# knct_iw_sq_access_history

呉高専 IW スクエアの入退室システム

## ディレクトリ構成

```
├── README.md 本ファイル

├── index.html 最初に開かれるページ、入室と退室を選べる

├── enter 入室用のフォルダ
│   ├── (index.html 学生番号を入力するページ)
│   ├── (number-of-people.html 使う人数を入力するページ)
│   └── submitted.html 送信後に表示されるページ

├── leave 退室用のフォルダ
│   ├── (index.html 学生番号を入力するページ)
│   ├── used-equipments.html 使った設備を入力するページ
│   └── submitted.html 送信後に表示されるページ

├── reset.min.css リセットCSS
├── common.css 共通のスタイルファイル

├── kvs-indexeddb-2.1.1.js ページ遷移時にブラウザにデータを保持するためのライブラリ
├── settings.js 送信先のURLなどが書かれているファイル
├── storage.js "kvs-indexeddb-2.1.1.js"を使いやすくするための関数をまとめたファイル
├── utils.js 便利関数などをまとめたファイル

├── code.gs Google Apps Script用のファイル、これでスプレッドシートに書き込んでいる

└── start.bat 入退室システム用のPCのスタートアップに置くファイル、詳細は後述
```

## 使い方

1. zip ファイルなどでダウンロードする
2. 解凍して PC のデスクトップにコピーする
3. バーコード読み郎というソフトをダウンロードしてデスクトップにコピーする
4. Windows のスタートアップに `start.bat` のショートカットを作成する

## `start.bat` とは

PC が起動した後にバーコード読み郎と入退室システムを自動起動し、22 時に自動でシャットダウンするプログラム
入退室システムは Google Chrome のキオスクモードというモードで起動している

## 改変時に気をつけること

改変などは自由に行って構わないが、後の世代が編集しやすい状態を保つように気をつけること
例えば本リポジトリでは npm を使ったり、バンドルしたりしていないがそれは初心者などでも必要最低限な知識で改変できるようにするためにあえて使っていない

## 以前のシステムからの変更点

利便性を向上させるため、人数入力画面を削除  
　→個人の入退室に向けたシステムに変更  
入退室の選択画面を削除  
　→入力段階を減らし高速化するため