## 第3章 インストール

- データベースクラスタ($PGDATA)
    - データベースの格納領域のこと。
    - データベースクラスタの実体はファイルシステム上の1つのディレクトリ。
    - データベースクラスタはよく**$PGDATA**と表記される。
    - データベースクラスタとPostgreSQLサーバは1対1で対応する。この1対1の組を**インスタンス**と呼ぶ。

- データベースクラスタの作成
    - initdbコマンドで作成する。

- データベース
    - テーブルやインデックスなどのデータベースオブジェクトの集合のこと。
    - データベースクラスタ内に複数のデータベースを作成できる。

- template0とtemplate1
    - データベース作成の際のコピー元となるテンプレートデータベースの種類。
    - デフォルトでは**template1**が新しいデータベースのテンプレートとして使われる。
    - template0はオブジェクト追加済みのtemplate1を使いたくない時に使用する。

- initdb
    - 指定したディレクトリにデータベースクラスタを作成するコマンドのこと。

- PostgreSQLの管理ユーザ
    - initdbでデータベースクラスタを作成したユーザが**PostgreSQLの管理ユーザ**となる。

- ロケール
    - 文字の並び順、文字の分類、ログメッセージの言語や数字、日付の書式などを指定するもの。

- ロケールの設定
    - ロケールを設定するとデータベースの検索性能が低くなると言われており、日本語で扱う場合はロケールを無効(--no-locale)にすることが推奨されている。

- エンコーディング
    - 文字をバイト列で表現するときのルールのこと。
    - 文字をデータベースに格納するときのエンコーディングを**データベースエンコーディング**と呼ぶ。
    - クライアントが使用するエンコーディングを**クライアントエンコーディング**と呼ぶ。
        - クライアントエンコーディングでは**SJIS**が使用可能である。
        
- エンコーディングの設定
    - エンコーディングはデータベース単位で指定できる。
