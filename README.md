# ローコード画面遷移フレームワーク
## 概要
Javaを用いたサーバーサイドの画面遷移において、JavaEEのJAX-RSや、SpringBootが提供している各種フレームワーク等を使用するのが主流である。  
開発現場においては、上記の技術を用いて画面遷移のアプリケーションの作りこみを行うのが普通であるが、  
頻繁に利用する画面遷移パターンとして、大きく分けて「DBからデータを取得して画面遷移」と「DBにデータ保存をして画面遷移」の2パターンに分別されると考える。  
上記2パターンを行えるインターフェース（もしくはアノテーション）を実装＆提供する事により、画面遷移アプリケーションのコード量を減らすことを目的とする。    
上記提供する機能の事を「ローコード画面遷移フレームワーク」として、本書では取り扱う。  

## 言語
Java SE 8

## 環境
Apache Tomcat 9  
PostgreSQL 13  
Eclipse  
Maven

## 機能
### DBからデータを取得して画面遷移  
　利用者は、リソースメソッド（※GETメソッド）から本機能を呼び出す事により、  
　DBからデータを取得して、クライアントに返却する画面を取得することが出来る。  
　画面の情報や、DBからデータを取得する情報に関しては「設定ファイルの提供」に記載する。  
　処理内でエラーが発生した場合には、一律で、エラー画面を返却する。  

### DBにデータ保存をして画面遷移  
　利用者は、リソースメソッド（※POSTメソッド）から本機能を呼び出す事により、  
　リクエストパラメータの情報を、DBにデータを保存して、クライアントに返却する画面を取得することが出来る。  
　画面の情報や、DBからデータを保存する情報に関しては「設定ファイルの提供」に記載する。  
　処理内でエラーが発生した場合には、一律で、エラー画面を返却する。  
  
### 設定ファイルの提供  
アノテーションを利用する上での設定情報を記載するファイル。  
形式はXML、文字コードUTF-8。改行コードはCRLFとする。  
本設定ファイルに、記載可能な情報は、  
遷移画面の情報（※次画面のリソースパスやシステムエラー画面のリソースパス）や、  
テーブル操作する上でのSQLファイルパス等を想定する。  

  以上
