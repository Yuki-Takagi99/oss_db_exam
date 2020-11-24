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
    - データベースに接続するために必要なユーザアカウントのこと。
    - データベースユーザは**データベースクラスタ内で一意（ユニーク）**でなければならない。
    - データベースクラスタには、PostgreSQLの管理ユーザと同名のデータベースユーザが最初から定義されている。

- データベースユーザの作成と削除
    - データベースユーザを作成するときは**createuser**を使う。
    - データベースユーザを削除する時は**dropuser**を使う。

    ```
    $ createuser [接続オプション][オプション][ユーザ名]
    # 指定した名前のデータベースユーザをデータベースクラスタに作成する

    $ dropuser [接続オプション][オプション][ユーザ名]
    # 指定した名前のデータベースユーザを削除する
    ```

- データベースの作成と削除 / createdb, dropdb
    - データベースを作成する時は**createdb**を使う。
        - データベースを作成できるのは、スーパーユーザか作成権限を持つユーザのみ。
    - データベースを削除する時は**dropdb**を使う。

    ```
    $ createdb [接続オプション][オプション][データベース名]
    # 指定した名前のデータベースを作成する

    $ createdb -U user1 examdb
    # ユーザuser1でデータベースexamdbを作成。-Tオプションは未指定なため、テンプレートはtemplate1、所有者はuser1となる。

    $ createdb -E EUC_JP -l C -T template0 testdb
    # エンコーディングとロケールCを個別に指定するため、-Tオプションでテンプレートをtemplate0を指定。ユーザは未指定のためOSユーザと同名になる。

    $ dropdb [接続オプション][オプション][データベース名]
    # 指定した名前のデータベースを削除する

    $ dropdb -U postgres -i testdb
    # データベースtestdbをユーザpostgresで削除する。-iオプションは削除前に確認するオプション。
    ```

- psql
    - psqlはデータベースへの接続やSWLコマンドを実行などを行うコマンド。

    ```
    $ psql -U user1 examdb
    # user1でデータベースexamdbに接続

    examdb=>#
    # 接続すると、入力を受け付ける状態になる
    # 終了するには\qを入力する

    examdb=> SELECT current_user, current_date;
    # 接続しているユーザ名(current_user)と現在の日付を取得
    ```

- メタコマンド
    - psqlで入力を受け付ける状態になった後、メタコマンドを入力できるようになる。
        - \q psqlを終了する
        - \l データベース一覧を表示
        - \d 指定パターンに一致する情報を表示する
    - [参考](https://suwaru.tokyo/%E3%80%90postgresql%E3%80%91psql%E3%83%A1%E3%82%BF%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%83%81%E3%83%BC%E3%83%88%E3%82%B7%E3%83%BC%E3%83%88%E3%83%BB%E8%A7%A3%E8%AA%AC/)
