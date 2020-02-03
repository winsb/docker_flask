# docker_flask
## 概要
dockerでflask+nginx+uwsgiを構築する。

## 構築環境
- python(pipenv):3.7
- flask:1.1.1
- nginx:1.17.8
- uwsgi:2.0.18

## 動作環境
- Docker Desktop for Windows 2.1.0.5 (https://docs.docker.com/docker-for-windows/install/)

## 使い方

### 準備
```
docker-compose build --no-cache
```

### 起動
```
doucker-compose up -d
```

### アクセス
http://localhost/

### 編集
./appディレクトリ内のファイルを編集する。
python moduleのinstallはPipfileに追加する。
flaskの使い方は[Flask](https://a2c.bitbucket.io/flask/)を参照してください。

### 停止
```
doucker-compose down
```

## 注意
- Windowsでは./appで`pipenv install`するとuwsgiでエラーが出る場合があります。その場合はPipfileから一時的にuwsgiを削除するとinstallできることがあります。
- buildなどで失敗する場合はDockerやWindowsの設定を確認してください。

## 参考
- https://qiita.com/trrrrrys/items/a905f1382733dfb9c8c1
- https://qiita.com/morinokami/items/e0efb2ae2aa04a1b148b