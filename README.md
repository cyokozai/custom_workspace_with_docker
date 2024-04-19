# Create a your workspace with Docker!

---

## はじめに

自前のプログラミング開発環境を整備するため、Dockerで開発環境を作成します。
慣れればそんなに難しくないので`example`と`README`を眺めてtemplateを自分なりに書き直してみてね。

### TL;DR

- Dockerを使った開発環境の構築
- 一度`Dockerfile`を書いて保存しておけば、いつでも立て直し可能
- 少し設定をいじれば、本番環境としてデプロイも可能

---
 
## Dockerのインストール

まずはDockerのインストールから始めます。
[公式ページ][Docker CE の入手]の手順を参考に操作します。
インストールできたとして進めます。

---

## Dockerfileを書こう

### Dockerfileとは

Dockerはイメージを元にコンテナをデプロイします。
`Dockerfile`はイメージの設計図です。

### Dockerfileの書き方

[ここの公式リファレンス][Dockerfile リファレンス]を参考に書き方を勉強してください。

---

## 参考文献

- [Docker CE の入手]
- [Dockerfile リファレンス]

[Docker CE の入手]: https://docs.docker.jp/get-docker.html
[Dockerfile リファレンス]: https://docs.docker.jp/v1.11/engine/reference/builder.html
