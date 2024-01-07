# 第3回課題

## 【課題】
- サンプルアプリケーションの起動

[(第３回課題１.png)](https://github.com/1127akinori/RaiseTech/blob/lecture03/%E7%AC%AC%EF%BC%93%E5%9B%9E%E8%AA%B2%E9%A1%8C%EF%BC%91.png)

- APサーバーについて
Puma vesion5.6.5
Railsを動かすためのアプリケーションサーバーの一種

[(第３回課題2.png)](https://github.com/1127akinori/RaiseTech/blob/lecture03/%E7%AC%AC%EF%BC%93%E5%9B%9E%E8%AA%B2%E9%A1%8C%EF%BC%92.png)
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
https://github.com/1127akinori/RaiseTech/blob/lecture03/%E7%AC%AC%EF%BC%93%E5%9B%9E%E8%AA%B2%E9%A1%8C%EF%BC%93.png

## 【感想】
railsを起動させるために、講座の動画を何回も止めて真似して、、、を繰り返しやっとできた。実際の業務となると、もっと複雑になると思うので、深掘りして学習する必要があると感じた。
アプリケーション起動中に別の窓で操作を行ったが、はじめはこれで大丈夫なのかと思ったが、cdでディレクトリの移動をしていれば問題なく操作できることを知れた。


