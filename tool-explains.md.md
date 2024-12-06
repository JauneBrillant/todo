# Volta

- Node.jsのバージョン管理ツール
- 高速 + モダン + クロスプラットフォーム + シンプル

### コマンド

```bash
# 安定動作の最新版をインストール
$ volta install node

# バージョンを指定してインストール
$ volta install node@22.12.0

# インストールされたnodejsのすべてを表示
$ volta list
```

### なぜNode.jsのバージョン管理ツールが必要か

- 複数のnodejsが必要なプロジェクトを抱えているとする。
- Aではv10.24.1が採用されていて、Bではv23.3.0が採用されていた場合、プロジェクト事に切り替える必要があるが、設定ファイル(package.json)にversionを記載することで自動で切り替えてくれる。voltaはこれを監視している。
- これにより、開発チームメンバー全員の開発環境を統一し、環境の不一致を防ぐ

```bash
# プロジェクトのnodejsのバージョンを固定
$ volta pin node@22.12.0

# volta pinコマンドでsettings.jsonに下記が追加される
"volta": {
    "node": "22.12.0"
}
```

### 代替

- NVM(Node Version Manager)
  - 最も一般的なNode.jsのバージョン管理ツール
  - Windowsでは使えない(wslなら可)

<br><br>

# Node.js

- javascript実行環境

### サーバサイドjavascript誕生

- ブラウザ上でしか動けなかったjavascriptが、Node.jsを入れたパソコンすべてで動かせるようになった。
- Node.jsではOSの機能にjavascriptでアクセスできるため、自由なファイルの読み書きや、ネットワーク通信などのOSの機能を扱えるようになる (ブラウザでのjavascript実行環境でOSの機能にアクセスできるとセキュリティ上まずい)
- サーバーサイドの処理は、ファイル操作(csvを読み込んで...)、データベース接続、ネットワーク通信(GETリクエストを受け取って...)など

### 便利なパッケージマネージャーnpm

- npm (node package manager)
- Node.jsに付属

```bash
# reactをインストール
$ npm install react

# typescriptをインストール
$ npm install typescript

# package.jsonのdependenciesに書かれているライブラリをすべてインストール
# この機能により、package.jsonをチームで共有するだけで全員が同じ環境を再現できる
$ npm install
```

### Node.jsとnpmの関係性は？

```
Node.js = 実行環境
npm = その実行環境で必要なライブラリやモジュールを管理するツール
```

### サーバーサイドでjavascriptを使わなくても、Nodejsが必要な理由

- 開発ツールチェインが優秀
- つまり環境構築がめっちゃ楽 + ビルド(ソースコードを実行可能な形に変換・処理するプロセス)も楽
- なのでたとえクライアント側でしかjavascriptを使わないとしてもNode.jsがマストになっている

#### 開発ツールチェイン

- npm : パッケージ(ライブラリやモジュール)を管理する
- webpack: javascript,css,画像などをまとめて一つのファイルにする(最適化されてパーフォーマンスが向上)
- babel: 最新のjavascript構文を古い公文に変換する(トランスパイル)。これにより古い環境でも動作するようになる。
- prettier: フォーマッター
- eslint: コードの静的解析ツール。構文の誤りや、使っていない変数などを指摘

など

### 代替

- Deno
- Bun

<br><br>

# React Native

- reactでスマホアプリ開発ができる
- 一つのコードベースでIOSとAndroidの両方に対応

### React NativeとExpoの関係性

```
React Native = reactでのスマホアプリ開発のフレームワーク
Expo = React Nativeでの開発をより便利にするライブラリ
```

### 代替

- Flutter

### React Native vs Flutter

- 正直どっちでもいいが、reactの勉強になるのでReact Nativeを採用

<br><br>

# Andorid Studio

- IDE(統合開発環境)
- Andoroidエミュレータが組み込まれているためマスト
