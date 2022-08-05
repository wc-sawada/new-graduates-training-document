## Nuxt.js

[【公式】 Nuxt.js](https://nuxtjs.org/)

1. どこか任意の場所をVisual Studio Codeで開く(trainingディレクトリとか作ると◎)  

2. ターミナルを開き、以下、コマンドを実行

```
npx create-nuxt-app [プロジェクト名]
```

3. 以下、質問に答える

```
?Project name:
→EnterでOK

?Programming language:
→JavaScriptかTypeScriptを選択してEnter

? Package manager:
→Npmを選択

? UI framework:
→見た目を整えるフレームワーク Noneを選択

? Nuxt.js modules:
→なしで大丈夫

? Linting tools:
→お好みで(今回は、なしで大丈夫)

? Testing framework:
→テストフレームワーク お好みで(今回は、なしで大丈夫)

? Rendering mode:
→SSRを選択

? Deployment target:
→Netlifyと連携するので、Static (Static/JAMStack hosting) を選択

? Development tools:
→利用する開発ツール jsconfig.jsonを選択

? What is your GitHub username?
→GitHubのユーザー名

? Version control system:
→Git

```

4. 作成したプロジェクトに移動

```
cd [プロジェクト名]
```

4. 以下コマンドで起動

```
npm run dev

```
プロジェクト作成完了！  

http://localhost:3000/


5. GitHubへアクセスしリポジトリを作成する  
https://github.com/

[この記事](https://qiita.com/_mamezou_/items/8f3711eb64c4bb2c51f6#%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%81%AE%E4%BD%9C%E6%88%90)が分かりやすい


6. 画面右上の「＋」からNew repositoryを押下

7. 以下入力し、Create repositoryを押下

```
Repository name : プロジェクト名
Description : 説明hogehoge(フロント研修 とか)
```

8. リポジトリが完成 Code → HTTPS → コピーマーク

9. Visual Studio Codeに戻り、ターミナルで以下コマンド実行

```
// gitの初期化をします。
git init

// 以下のようにアップロードします。
git add .
git commit -m "first commit"
git branch -M main
git remote add origin [https or ssh でのリンク]
git push -u origin main
```

*※git initで作られたブランチはデフォルトがmasterになっているのでmainに変更している*  
*※Gitコマンドで連携できなかったら、リポジトリクローンしてそのまま手作業でソース移動…*
4. 完了です。お疲れ様でした！