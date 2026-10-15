# 第3回 Webエンジニアリング演習 レポート
## 学籍番号
 4724214
## イメージとコンテナの違い

イメージは仮想環境のスナップショットであり実態を持たない

コンテナは仮想環境そのもであり、実態をもつ

## Dockerfileの各行の役割

FROMはDocker hubのどのイメージを使うのか指定している
COPYはindex.htmlをnginxのhtml配信用ディレクトリにコピーして配信できるようにしている。


## 動作確認

### 変更後の見出し

```
@4724214 ➜ /workspaces/web-eng-docker (class-03-docker) $ curl http://localhost:8080
<!doctype html>
<html lang="ja">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Web Engineering Class 03</title>
    </head>
    <body>
        <h1>Docker Composeで配信中</h1>
        <p>Web Engineering Class 03</p>
    </body>
</html>
```
### docker compose psの結果

```
@4724214 ➜ /workspaces/web-eng-docker (class-03-docker) $ docker compose ps
NAME                   IMAGE                COMMAND                  SERVICE   CREATED              STATUS              PORTS
web-eng-docker-web-1   web-eng-docker-web   "/docker-entrypoint.…"   web       About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp
```
