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

[参照 メリット・デメリットとかも記載されてる](https://digitalidentity.co.jp/blog/creative/dynamic-serving.html)

***

## HTML
* コーディング場所  
以下ファイルにコーディングします！  
`pages/index.vue`

```
<template>
  <Tutorial/>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
```

↓

```
<template>
  <main>
    〜ココに書いていく〜
  </main>
</template>
```

* ヘッダーとフッター記述場所  
layoutsディレクトリ作成し、default.vue作成  
`layouts/default.vue`  
https://nuxtjs.org/ja/docs/directory-structure/layouts/

```
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

```
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
そんなのもあるんだな〜くらいでOK

***

## 画像
* 格納場所  
assets/images/ディレクトリを作成  
`assets/images/配下`

* 命名  
コンテンツ名_要素名

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
(Chrome DevTools の使い方)[https://murashun.jp/article/performance/chrome-devtools.html]

***