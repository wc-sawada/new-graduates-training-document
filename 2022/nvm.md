## nvm
1. nvm-setup.zipをダウンロード  
https://github.com/coreybutler/nvm-windows/releases

2. zipファイルを解凍してnvm-setup.exeを実行し、インストール

3. インストール後、コマンドプロンプトを開き、以下コマンドを実行

```
nvm install 16.14.2
```

* Node.jsのバージョン  
https://nodejs.org/ja/download/releases/

4. 以下コマンドを実行し、インストールされているか確認

```
nvm list

[実行結果]
  * 16.14.2 (Currently using 64-bit executable)
```

5. 任意のバージョンを使うとき

```
nvm use 16.14.2
```

5. Node.jsのバージョン確認

```
node -v
v16.14.2
```
4. 完了です。お疲れ様でした！
* 導入分かりやすい記事  
https://helog.jp/development/nvm-windows/