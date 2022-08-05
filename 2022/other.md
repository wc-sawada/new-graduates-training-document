# その他、決め事など

## 思い出すこと
[Progate](https://prog-8.com/)で、やった内容

***

## レスポンシブデザイン？ダイナミックサービング？
今回は*PCのみのコーディング*

* ダイナミックサービングとは
1つのURLに対して、2つのHTMLを用意し、ユーザーがアクセスした端末によって  
サーバーサイドでPC向けのHTMLとスマートフォン向けのHTMLを出し分けることを指す  

* レスポンシブデザインとは
1つのHTMLで配信し、スマホ、タブレット、パソコンごとに、CSS（画像の大きさやレイアウトなど表示の指定）を用意して表示を変更させる方法  

参照： [ダイナミックサービングとは？レスポンシブWebデザインとの違いを解説！](https://digitalidentity.co.jp/blog/creative/dynamic-serving.html)

***

## HTML
* コーディング場所  
以下ファイルにコーディング  
`pages/index.vue`

```vue:pages/index.vue
<template>
  <Tutorial/>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
```

↓ 書き換える

```vue:pages/index.vue
<template>
  <main>
    〜ココに書いていく〜
  </main>
</template>
```

* ヘッダーとフッター記述場所  
layoutsディレクトリ作成し、default.vue作成  
https://nuxtjs.org/ja/docs/directory-structure/layouts/

`layouts/default.vue`
```vue:layouts/default.vue
<template>
  <div>
    ～ヘッダー記述～
    <Nuxt />
    ～フッター記述～
  </div>
</template>

```

* コーディングルール  

インデントは*2スペース*

```vue:pages/index.vue
<template>
  <main>
    <h1>タイトルです </h1>
    <p>文章です</p>
  </main>
</template>
```

* ドキュメント  
[基礎知識](https://developer.mozilla.org/ja/docs/Learn/HTML/Introduction_to_HTML)  
[ブロック/インライン要素、実体参照](https://developer.mozilla.org/ja/docs/Learn/HTML/Introduction_to_HTML/Getting_started#html_comments)  
[コンテンツの構造化](https://developer.mozilla.org/ja/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)　

***
## CSS
* 英語で付ける(ローマ字できればNG)

```
ex)

◯ center　☓ chuo
```

* 数字から始まるのはNG

```
ex)

◯ text01　☓ 01text
```

* 複数の単語を組み合わせる場合はハイフンかアンダースコア(※どちらかに統一)

```
ex)

◯ section-title、section_title　☓ section title、section.title
```

```
ex)

<header class="header">
  <img class"header-logo" scr="">
  <ul class="header-list">
    <li>リスト1つ目の要素</li>
    <li>リスト2つ目の要素</li>
  </ul>
</header>
```

CSSの命名規則には色んな種類がありcss設計というものがありますが、  
[css設計](https://www.northdetail.co.jp/blog/1953/)  
今回は、そんなのもあるんだな〜くらいでOK

***

## ページ単位のCSS

```
ex)

<template>
  <div >
    ...
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
  div{
    color: red;
  }
</style>
```

`scoped`プロパティを`style`要素に付与することで、CSS記述が該当の.vueファイル内でのみ有効になる

***
## グローバルなCSS

`assets`配下にcssディレクトリを作成

```
ex)

assets/css/common.css
```

作成したファイルをnuxt.config.jsのcssセクションで読み込む  
`nuxt.config.js`
```javascript:pages/nuxt.config.js
module.exports = {
  // ...
  css: [
    "~assets/scss/common.css"
  ],
}
```

***
## 画像
* 格納場所  
assets/images/ディレクトリを作成  
`assets/images/配下`

* 命名  
`コンテンツ名_要素名`
```
ex)
about_title.png
about_image.jpg
about_icon_1.png
about_icon_2.png
```

* 読込方法

```
■HTML
<img src="~/assets/images/hoge.png" alt="hoge">

■CSS
background-image: url(~/assets/images/hoge.png);
```

***

## デバッグ方法
Chrome DevToolsを利用  
[Chrome DevTools の使い方](https://murashun.jp/article/performance/chrome-devtools.html)

***

## 外部ファイルを読み込みたいとき

`nuxt.config.js`
```javascript:pages/nuxt.config.js
export default {
  head: {
    link: [
      { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Roboto' }
    ],
    script: [
      { src: 'https://cdnjs.cloudflare.com/ajax/libs/numeral.js/2.0.6/numeral.min.js' }
    ]
  }
}
```

***

## Googleフォントを使いたいとき

@nuxtjs/google-fontsというNuxt.jsモジュールを利用

ターミナルにて
```
npm i --save-dev @nuxtjs/google-fonts
```

`nuxt.config.js`
```javascript:pages/nuxt.config.js
export default {
・・・
  buildModules: [
    '@nuxtjs/google-fonts' //追加
  ],
  googleFonts: {
    families: {
      Roboto: [100, 400, 500, 700] //読み込みたいGoogle　Fontsを指定
    }
  },
・・・
}

```

```css
body {
  font-family: "Roboto", sans-serif;
}
```

参照：[Nuxt.jsに@nuxtjs/google-fontsを使ってGoogle Fonts（Webフォント）を設定する方法](https://qiita.com/TK-C/items/4a50d0dba3fa7a084eb1)

***
