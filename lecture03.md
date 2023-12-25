# 第3回課題

## 【課題】
- サンプルアプリケーションの起動

<img width="1512" alt="スクリーンショット 2023-12-21 0 01 59" src="https://github.com/1127akinori/RaiseTech/assets/149952775/1fb5afc2-256d-441c-9a39-a5ab53e71e8f">

- APサーバーについて
Puma vesion5.6.5
Railsを動かすためのアプリケーションサーバーの一種

<img width="1512" alt="スクリーンショット 2023-12-24 14 57 02" src="https://github.com/1127akinori/RaiseTech/assets/149952775/a98e9caa-14cb-4ba7-a62f-6d3fdc26c4cd">
```
akinori:~/environment/raisetech-live8-sample-app (main) $ rails s
=> Booting Puma
=> Rails 7.0.4 application starting in development 
=> Run `bin/rails server --help` for more startup options
Puma starting in single mode...
* Puma version: 5.6.5 (ruby 3.1.2-p20) ("Birdie's Version")
*  Min threads: 5
*  Max threads: 5
*  Environment: development
*          PID: 12222
* Listening on http://127.0.0.1:8080
* Listening on http://[::1]:8080
Use Ctrl-C to stop
```

- DBサーバーについて調べる



<img width="1512" alt="スクリーンショット 2023-12-21 0 01 59" src="https://github.com/1127akinori/RaiseTech/assets/149952775/1fb5afc2-256d-441c-9a39-a5ab53e71e8f">

## サンプルアプリケーションの起動で行ったこと

- `ruby -v`でrubyのバージョン確認を行う
- 　指定されたバージョンを`rvm install`でインストールして`rvm use 指定したバージョン`で使用する
 - RVM（Ruby Version Manager）とは
 - Ruby環境をインストール・操作・管理することができるコマンドラインツール
 - `ruby -h` `rvm -h`でコマンド一覧を表示させれる 
   
   - **sudoコマンド**とは
     - 一般ユーザーがソフトをインストールしたり、ソフトを実行したりする場合、Linuxではsudoを一番始めに宣言して使用する
     - 宣言することで管理者権限で実行することが可能となる

- `node -v`でNodeのバージョン確認をする
- 指定のバージョンを`nvm install 17.9.1`でインストールする
  - **NVM**（Node Version Manager）とは
    - Node.jsのバージョン管理を行うためのソフトウェアツール
  - **Node.js**とは
    - JavaScriptをサーバー側で動作させるプラットフォーム
    
- `nvm use 17.9.1`で使用するバージョンを切り替える
- `npm install -g yarn`でyarnをインストールする
  - **NPM**（Node Package Manager）とは
    - 主にJavaScriptで開発されたプラグラム部品（モジュール）を管理するためのパッケージ管理システムの一つ
  - **Yarn**とは
    - JavaScriptをサーバーサイドで動かすための実行エンジンである「Node.js」上で動作するパッケージマネージャーの一つ
    - npmより高速で、並列インストールをサポートし、パッケージのインストール速度を向上させる
  - 「npm install -g yarn」の「**-g**」
    - インストール先がグローバル。デフォルトはローカル
    - rootが所有する{prefix}/lib/node_modules/にパッケージがインストールされる
   
- `yarn -v`でバージョンの確認をし、問題がなければもう一度`bin/setup`を行う
- `bin/cloud9_dev`でアプリケーションの起動をする
    
    **⇒ アクセスの権限がない（実行ができない）ため拒否される**
- `ls -la bin`でbinディレクトリ内すべてのファイルやディレクトリを詳細な情報と共に表示し、隠しファイルも含めて表示する
  - パーミッション情報を確認する
  - cloud9_devは`-rw-rw-r--`となっており、アクセス権限がないことがわかる
  - パーミッション情報は、1桁目がファイル情報で、「d」であればディレクトリ、「-」であればファイルを意味する
  - 1桁目以降は、3文字1セットで、左から「所有者」「グループ」「その他のユーザー」を表す
  - パーミッションの有効無効は0～7の数値で表す  
    
     | アクセス権 | 数値| 説明 |
     |:---|:---|:---|
     | --- | 0 | 読み込み書き込み不可 |
     | --x | 1 | 実行のみ |
     | -w- | 2 | 書き込みのみ |
     | -wx | 3 | 書き込み実行のみ |
     | r-- | 4 | 読み込みのみ |
     | r-x | 5 | 読み込み実行のみ |
     | rw- | 6 | 読み込み書き込みのみ |
     | rwx | 7 | 読み込み書き込み実行ができる |


- `sudo chmod 775 bin/cloud9_dev`でcloud9_devのアクセス権限を変更する
   - 上図の数値を元に変更
   - `ls -la bin`で権限が変更されているかを確認する
   - `-rwxr-xr-x`となっていた為、「755」で変更が適用されていることがわかる
- `bin/cloud9_dev`で再度アプリケーションの起動をする
- **Block host**と表示された為、`Ctrl＋C`でアプリケーションを停止する
- 「config」フォルダ ⇒「environments」フォルダ内にある「**development.rb**」ファイルを開く
-  Block hostの画面に表示されている下記を「development.rb」ファイルの一番下にペーストする
   - config.hosts << "9946160ad4a34eef9979c3602ca44997.vfs.cloud9.ap-northeast-1.amazonaws.com"
　

   ![04](/images-lecture03/2023-12-04_234356.png)
   - `config.hosts <<`も入力しなければ起動しない
   - `end`がきちんと反映されていないと起動しない ⇒ `syntax error`が表示された
    
- `bin/cloud9_dev`で再度アプリケーションの起動をする
   - 起動に成功
   - 動作確認も完了

<br>

### -  APサーバーについて調べる  -

 - Railsを動かすためのサーバー（Railsのバージョンは**7.0.4**）
 - **Puma version 5.6.5**を使用
   
   ![05](/images-lecture03/2023-12-04_235002.png)
 - サーバーを`Ctrl＋C`で停止させた後、引き続きアクセスは出来ない
   
   ![06](images-lecture03/2023-12-04_235116.png)
 - `rails s`でアプリケーションサーバーを再起動すると再びアクセスが可能

<br>

### -  DBサーバーについて調べる  -

 - **MySQL version 8.0.35**を使用
 - バージョンの確認はMySQLログイン時、またはログインしてからのコマンドで確認が出来る
 
   ![07](/images-lecture03/2023-12-05_004744.png)

   ![08](/images-lecture03/2023-12-05_004942.png)
   
 - サーバーを終了させた後、`rails s`を入力しても引き続きアクセスは出来ない
 
   ![09](/images-lecture03/2023-12-05_001344.png)

   ![10](/images-lecture03/2023-12-05_000638.png)
 
 - 再起動をすると`active（running）`になりアクセスが可能になる
 
   ![11](/images-lecture03/2023-12-05_000853.png)

   ![12](/images-lecture03/2023-12-05_001249.png)

<br>

## 【所感】
工程が上手く理解できず、課題を進めるのに非常に時間が掛かった。

それぞれが互いにどのように作用しているか等、一度実践しただけではわからなかった。

今回こうして作業内容を整理し直すことで、それでもまだ不十分であるとは思うが、理解に繋がったように思う。

「簡単なアプリケーション」と聞いていたが、起動時の動作が単純なアプリケーションでも初学者の自分には複雑だった。

実際の業務となると、もっと難解な作業になるのだろうがまったく想像がつかない。


