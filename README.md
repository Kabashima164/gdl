# gdl-docker

AppleSilicon製のコンピュータにGDL-GnuDataLaungageを入れるためのDocker-composeファイルです

>**Note**<br>
>前提としてhomebrewとgitが導入されている必要があります<br>
>https://brew.sh/index_ja

### インストールと設定
・dockerのインストール<br>
`arch -arm64 brew install --cask docker`<br>
（MacではDocker-Desktopしか使えないようです）

・XQartzのインストール<br>
`arch -arm64 brew install --cask xquartz`<br>

・XQartzの設定
設定からネットワーク・クライアントからの接続を許可を押します　<br>
<img width="583" alt="スクリーンショット 2023-04-18 13 38 23" src="https://user-images.githubusercontent.com/85889884/232672801-b648810a-1bbd-4cdb-a5d5-6e12ff991648.png">

・コマンドラインからlocalhostからの接続を許可します<br>
`xhost + localhost`

### コンテナの実行<br>
・docker-compose.ymlのダウンロード<br>
`git clone https://github.com/Kabashima164/gdl-docker.git`

・コンテナの実行<br>
`cd gdl-docker`<br>
`docker compose up -d`

・コンテナの中にはいる<br>
`docker container exec -it gdl-docker bash`

### 実行してみる<br>
`cd gdl-src`<br>
`gdl`<br>
`plot,sin(findgen(200)/100*!pi)`<br>
これでsinのプロットが表示されれば成功です！


