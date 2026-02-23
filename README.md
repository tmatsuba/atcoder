# atcoder

AtCoder用のGoコーディング環境。[online-judge-tools](https://github.com/online-judge-tools/oj) を使ってテストケースの取得・テスト・提出を自動化している。

## ディレクトリ構成

```
_result/    # 提出済みコード (_result/_<contest>/<question>/main.go)
_template/  # テンプレートファイル
shell/      # 各種スクリプト
contest     # 現在のコンテスト名（gitignore対象）
input       # サンプル入力（gitignore対象）
test/       # oj がダウンロードしたテストケース（gitignore対象）
main.go     # 作業ファイル（gitignore対象）
main        # ビルド済みバイナリ（gitignore対象）
```

## セットアップ

```sh
# online-judge-tools のインストール
pip3 install online-judge-tools

# entr のインストール（ファイル監視）
brew install entr

# AtCoder にログイン
make login
```

## 使い方

### 1. コンテスト開始

```sh
echo "abc123" > contest   # コンテスト名をセット
make b                     # テンプレートから main.go を生成
```

### 2. 問題のダウンロード（テストケース取得）

```sh
make d   # コンテスト名を読み込み、問題番号を入力するとテストケースを取得
```

### 3. 実装・ビルド

```sh
make run   # main.go をビルド
```

### 4. テスト

```sh
make t   # oj でサンプルケースをテスト
```

### 5. 提出

```sh
make s   # oj で提出
```

### 6. 次の問題へ

```sh
make m   # main.go を _result/ に移動してコミット、テンプレートをリセット
```
