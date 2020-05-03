# 概要

教科書P135~198

* CSSの基本
* CSSでスタイリング
* CSSでレイアウト

## CSSとは？

HTML文書に対して色や大きさ、配置などの見た目を設定する

拡張子は.css

> style.css の表記が多いかな？

## 記述ルール(CSSファイル内)

[セレクタ] { [プロパティ]: [値]; }

* セレクタ: スタイルを設定する箇所の名前やid
* プロパティ: 何を装飾するかの指定
* 値: 色やピクセル数など

```CSS
h1 {
	color: #ff0000;
	line-height: 1em;
	font-size: 40px;
}
```

## CSS組み込みの方法

* インライン
* エンベッド
* 別ファイルから読み込み ←基本はこれ使う

### インライン

style属性内にプロパティと値を記述する

```HTML
<h1 style="color: #ff0000;">赤い見出し</h1>
```

>結果:
><h1 style="color: #ff0000;">赤い見出し</h1>

### エンベッド

headタグ内にstyleタグを用意して記述する

```HTML
<html>
	<head>
		<style>
			h1 {
				color: #ff0000;
			}
		</style>
	</head>
	<body>
		<h1>見出しだよ!</h1>
	</body>
</html>
```

>結果:
><iframe src="./SampleF.html"></iframe>

headに記述したcssはhtmlファイル全体に適用される

### 別ファイル

.cssファイルを用意して読み込む

style.css
```CSS
h1 {
	color: #00ff00;
}
```

index.html
```HTML
<html>
	<head>
		<!--同じ階層にstyle.cssがあるとする-->
		<link href="./style.css" rel="stylesheet" type="text/css">
	</head>
	<body>
		<h1>見出しだよ!</h1>
	</body>
</html>
```

同様の結果が得られる(SampleG参照)

## セレクタについて

p, h1などhtmlタグの名前と同じ(タイプセレクタ) → 読み込まれたhtmlのそのタグ全体に適用される

### IDセレクタ

```CSS
#hogehoge {
	color: #0000ff;
}
```

みたいな感じで前に#つけるとIDセレクタになる

このidを指定したタグにスタイルを適用する

idはHTMLファイルに一意でなければならない

```HTML
<h1 id="hogehoge">文字が青くなる</h1>
<h1>特に変わらない</h1>
```

NG例
```HTML
<h1 id="hogehoge">idを</h1>
<h1 id="hogehoge">２回以上適用するのはNG</h1>
```

> identitiyなのでね

### classセレクタ

```CSS
.fugafuga {
	color: #0000ff;
}
```

みたいな感じで前に.つけるとclassセレクタになる

このclassを指定したタグにスタイルを適用する

classはHTML内で何回使っても良い

```HTML
<h1 class="fugafuga">文字が青くなる</h1>
<h1>特に変わらない</h1>
<h1 class="fugafuga">何回使っても良い</h1>
```

### 子孫セレクタ

```CSS
.fuga p {
	color: #ff0000
}
```

セレクタに半角スペースを開けて続けてセレクタを記述するとその子孫のみに適用するものになる

```HTML
<div class="fuga">
	<p>赤くなる</p>
<\div>
<p>赤くならない</p>
```

## CSSの優先順位

読み込み順番で考える

CSSファイルは上から順に読み込むので下のほうが優先度が高い

CSSファイルに書くよりインラインの方が優先度が高い

IDセレクタ > classセレクタ > タイプセレクタ

## 擬似クラス

特定の状態にある時(hoverとか)のスタイルを記述する

[セレクタ] : [擬似クラス] {

}

```CSS
a:link {
	color: #ff0000;
}
```

他にも
link:hover, link:visited, li:first-childとかがある

## 疑似要素

要素のある特定の箇所にスタイルを適用する

[セレクタ] :: [疑似要素] {

}

見出しの前に星を追加する
```CSS
h2::before {
	content: "★";
}
```

他にも
::after, ::first-line, ::first-letter などがある

## スタイリング

### 文字サイズ

[font-sizeプロパティ](https://developer.mozilla.org/ja/docs/Web/CSS/font-size)で設定

```CSS
p {
	font-size: 1.6em;
}
```

単位がたくさんある

* em: 親要素の1文字を1emとしたときの大きさ
* rem: htmlタグで指定された1文字を1remとしたときの大きさ
* px: 画面のピクセル数
* mm: 長さ(印刷用)

基本emを使えばいいんじゃないかな

### 行間

[line-heightプロパティ](https://developer.mozilla.org/ja/docs/Web/CSS/line-height)で設定

```CSS
p {
	line-height: 1.6;
}
```

単位はfont-sizeと同じだが、何も指定しないとフォントサイズにその数字を掛けたものになる

文字の頭から次行の文字の頭までの長さ(つまりline-height: 1;で行間0)


