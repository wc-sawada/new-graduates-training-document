# その他決め事など

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

* ヘッダーとフッター追加  
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
