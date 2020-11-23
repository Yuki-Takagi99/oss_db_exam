## 第4章 標準付属ツール

- pg_ctl
    - PostgreSQLの起動や停止、状態確認などに使う管理ツール
    - pg_ctlを実行するユーザはPostgreSQLの管理ユーザでなければならない。
    - rootユーザでpg_ctlを実行することはできない。

    ```
    $ pg_ctl initdb -D ~
    # 指定したディレクトリにデータベースクラスタを作成する

    $ pg_ctl start
    # PostgreSQLをバックグラウンドで起動する

    $ pg_ctl stop
    # PostgreSQLを停止する

    $ pg_ctl restart
    # PostgreSQLを再起動する

    $ pg_ctl reload
    # PostgreSQLに設定ファイルを再読み込みさせる

    $ pg_ctl status
    # PostgreSQLが起動しているかどうか確認する

    $ pg_ctl kill
    # プロセスにシグナルを送信する
    ```

- データベースユーザ

- データベースユーザの作成と削除

- データベースの作成と削除

- createuser / dropuser

- createdb / dropdb

- psql

- PostgreSQLの管理

- SQLコマンドの実行