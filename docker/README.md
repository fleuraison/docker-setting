# docker資料

既存のプロジェクトにdockerフォルダを追加して活用して下さい

## 使い方
$ docker-compose up -d
これで起動しますので、あとは
http://localhost/
https://localhost/
でアクセスできます

## コンソール

プログラムソースが動いているところ（webコンテナ）には

```sh
$ cd docker
$ docker exec -it rasp_web73 sh
もしくは
$ winpty docker exec -it rasp_web73 sh
```

nginxコンテナには、
```sh
$ docker exec -it rasp_nginx bash
もしくは
$ winpty docker exec -it rasp_nginx bash
```

mysqlコンテナには

```sh
$ docker exec -it rasp_mysql bash
もしくは
$ winpty docker exec -it rasp_mysql bash
```

で入れます
winptyは、windowsでのgitbash特有のおまじないです


