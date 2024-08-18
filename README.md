# NMS デプロイメント

## 概要

この GitHub Actions は, 指定された NMS バージョンをローカル Maven リポジトリにデプロイするためのワークフローです。
NMS（Net Minecraft Server）アーティファクトを GitHub リリースからダウンロードし, 指定されたパスに展開します。

## 使用方法

このワークフローを実行するには, 以下の入力パラメータを設定する必要があります。

### 入力パラメータ

- `versions` (必須): デプロイする NMS バージョンを改行で区切って指定します。
- `github-token` (必須): NMS リポジトリにアクセスするための GitHub パーソナルアクセストークン (PAT) を指定します。
- `nms-repository` (オプション): プリビルドされた NMS アーティファクトを含むリポジトリ。デフォルトは `TeamKUN/NMSBuilds` です。
- `deploy-path` (オプション): NMS アーティファクトをデプロイするパス。デフォルトは `~/.m2/repository` です。

## トークンの指定

このアクションは内部で `TeamKUN/NMSBuilds` リポジトリを参照しています。  
そのために, 上記リポジトリの `read` 権限を持つ Fine-granted PAT を作成し, このアクションに渡して下さい。
