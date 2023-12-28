# 第3回課題

## 【課題】
- サンプルアプリケーションの起動

<img width="1512" alt="スクリーンショット 2023-12-21 0 01 59" src="https://github.com/1127akinori/RaiseTech/assets/149952775/1fb5afc2-256d-441c-9a39-a5ab53e71e8f">

- APサーバーについて
Puma vesion5.6.5
Railsを動かすためのアプリケーションサーバーの一種

<img width="1512" alt="スクリーンショット 2023-12-24 14 57 02" src="https://github.com/1127akinori/RaiseTech/assets/149952775/a98e9caa-14cb-4ba7-a62f-6d3fdc26c4cd">
```

　➖ DBサーバーについて調べる
```
# Mysqlログイン(-pはパスあり)
mysql -u root -p
# Mysqlの起動
sudo service mysqld start
# Mysqlの停止
$ sudo service mysqld stop
# MySQLの再起動
$ sudo service mysqld restart
# Mysqlの状態確認
$ sudo service mysqld status
```

サーバー停止後の画面
<img width="1512" alt="スクリーンショット 2023-12-28 12 21 56" src="https://github.com/1127akinori/RaiseTech/assets/149952775/633b128d-550e-484d-b264-c3744ff62709">




## 【感想】
railsを起動させるために、講座の動画を何回も止めて真似して、、、を繰り返しやっとできた。実際の業務となると、もっと複雑になると思うので、深掘りして学習する必要があると感じた。
アプリケーション起動中に別の窓で操作を行ったが、はじめはこれで大丈夫なのかと思ったが、cdでディレクトリの移動をしていれば問題なく操作できることを知れた。


