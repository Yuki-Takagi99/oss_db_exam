##  第2章 データペースの基礎知識

- データベースマネジメントシステム(DBMS)
    - データを一元管理するためのソフトウェアの総称。

- データベースマネジメントシステムの機能
    - データの機密保護
        - アクセス制限をきめ細かく設定できる。
    - トランザクション制御
        - **トランザクションとは、分割できないまとまった処理**のこと。
        - DBMSはトランザクションの処理が同時に実行されても、同じデータの更新が同時に行われないように**排他制御**する。
    - データの整合性保持
    - 障害からの安全な復旧
        - バックアップとログを用いて、障害復旧直前の状態に復旧させることができる。
    - アプリケーションプログラムのためのインターフェース提供

- データモデリング
    - データモデルを作成すること。

- 概念データモデル
    - **対象世界を抽象化して、データ構造を概念的に捉えた結果を表現したモデル** 
    - 特定の種類のデータベースには依存しない。
    - 作成には**ERモデル** がよく用いられる。
    - **ERモデルとは、Entity(実体)とRelationship(関連)** のこと。
    
- 論理データモデル
    - **データとデータ間の関係を論理的に表現したもの**
    - そのままデータベースに実装可能なデータモデル

- SQL
    - データベースのデータを定義したり操作したりするための言語

- 命令クエリ
    - データベースを操作するための命令のこと

- SQLの分類
    - DDL(データ定義言語)
        - テーブルやインデックスの作成/変更/削除など
        - CREATE, ALTER, DROPなど
    - DML(データ操作言語)
        - データの参照/追加/削除など
        - SELECT, INSERT, UPDATE, DELETEなど
    - DCL(データ制御言語)
        - 権限の設定・取り消し/データの更新確定/取り消し
        - GRANT, REVOKE, COMMIT, ROLLBACKなど

- 正規化
    - データベースに実装する際に冗長なデータがあり不具合が出るケースなどを解消するために**正規化**を行う。

- 候補キーと主キー
    - 主キーの決定する際は、最初に候補キーを明確にする。
    - 候補キーは、**行を一意に識別できる単独の属性または必要最小限の属性の集合**である。
    - 主キーは、候補キーの中から1つ選択する。(NULLを含めることはできない)

- 第一正規形
    - **非正規形が持つ繰り返し項目を解消し、複数の値を持つ属性を分割した状態**

- 第二正規形
    - **第一正規形であり、全ての非キー属性が候補キーに完全関数従属である状態**

- 第三正規形
    - **第二正規形であり、全ての非キー属性がどの候補キーに対しても推移的に関数従属していない状態**

