# Product Management CLI
## 概要
Product Management CLI は、Javaで実装したコマンドライン型の商品管理アプリケーションです。
商品の登録・検索・削除・一覧表示に加え、CSVファイルへの保存・読込機能を備えています。
本プロジェクトでは、オブジェクト指向の基本設計を意識し、責務を分離したシンプルな構成を採用しています。
 
⸻
 
###主な機能
* 商品登録
* 商品一覧表示
* 商品検索（商品番号）
* 商品削除
* CSVファイル保存
* CSVファイル読込
* 入力値チェック
* 商品番号自動採番（001～999）
 
⸻
 
##クラス構成
ProductManagementCLI
│
├── Product.java
│        商品データ(Model)
│
├── ProductRepository.java
│        商品管理(Repository)
│
├── CsvUtil.java
│        CSV保存・読込(Utility)
│
└── ProductRegistration.java
         メニュー・画面制御(Main)
 
⸻
 
クラス関係図
                ProductRegistration
                         │
                         │
                         ▼
                ProductRepository
                   │            │
                   │            │
                   ▼            ▼
               Product      CsvUtil
* Product  
    * 商品情報を保持するデータクラス
* ProductRepository  
    * メモリ上の商品管理を担当
* CsvUtil  
    * CSVファイルの保存・読込を担当
* ProductRegistration  
    * ユーザー操作とメニュー制御を担当
 
⸻
 
商品データ
項目	説明
id	商品番号
name	商品名
price	単価
stock	在庫数
例
001
Apple
100
20
 
⸻
 
CSV形式
id,name,price,stock
001,Apple,100,20
002,Orange,200,15
003,Banana,150,30
ヘッダ付きCSVを採用しています。
 
⸻
 
実行方法
コンパイル
javac *.java
実行
java ProductRegistration
 
⸻
 
メニュー
================================
      Product Management
================================

1. 商品登録

2. 商品一覧

3. 商品検索

4. 商品削除

5. CSV保存

6. CSV読込

7. 終了
 
⸻
 
設計方針
本プロジェクトでは、
* データ
* データ管理
* ファイル操作
* 画面制御
をそれぞれ独立したクラスへ分離しています。
View(Main)

↓

Repository

↓

Model
CSV操作はRepositoryへ実装せず、CsvUtilへ分離することで責務を明確にしています。
 
⸻
 
使用ライブラリ
* Java Standard Library
外部ライブラリは使用していません。
 
⸻
 
###今後の改善案
* 商品更新機能
* 商品名検索
* 並び替え機能
* 自動保存
* 起動時自動読込
* JSON対応
* パッケージ分割
* Unit Test追加
 

 
ライセンス
This project is provided for educational purposes.
