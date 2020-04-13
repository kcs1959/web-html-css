# 概要

教科書 P11~76

* Webサイトの基本
* 環境構築
* HTMLの基本
* 画像とリンクの表示

# Webサイト作成によく使われる言語

プログラミング言語と言えば色々あるが、
Webサイトを作れる言語は現状ほぼ一本化されている。
それが、HTML、CSSとJavaScriptの組み合わせだ。

## HTML(HyperText Markup Language)

主にWebページの内容を「タグ」によってマークアップし、文書内の役割を指定するのに使われる。

```HTML
<html>
	<h1>適当なHTML</h1>
	<p>本文</p>
	<br/>
	<p>本文2</p>
</html>
```

複数のバージョンがあるが、現在はHTML5(2014年勧告)が主流。

HTMLを中学や高校で習う人も多いだろうが、多分内容が古いのであまり役に立たない。

```HTML
<marquee>横に動く</marquee> <!--HTML5では廃止されたよ！-->
```

あくまで文書の内容を整えるのに専念し、レイアウトや装飾は後述のCSSに任せるのが現代流。

## CSS(Cascading Style Sheets)

Webページの見た目や構造などのスタイルを指定するための言語。

```CSS
/*h1(見出し)に装飾を加える*/
h1 {
	color: #ff0000;
	line-height: 1em;
	font-size: 40px;
}
```

現在はCSS3が主流(CSS4も少しずつ勧告され始めている)。

## JavaScript

Webサイトに動きを付けたり、振る舞いを与えるための言語。

```JavaScript
//無限にアラートが出続ける
//逮捕案件
while(1)
{
   alert("無限アラート");
}
```

所謂プログラミング言語なので、計算などにも利用できる。

## その他

### PHP, Ruby等

Webサーバ上で動作し、動的にHTMLを生成することで動きのあるサービスを作ることができる。

PHPは[去年の資料](https://github.com/kcs1959/web-php)があるので興味があったら参考にしてね

### React, Vue, Angular等

上記のJavaScriptを拡張し、利便性や生産性を高めたフレームワーク。言語もJavaScriptだけでなくTypeScriptなどで書くことができる。

本講習会では使わないです

# 環境構築

## エディタ

既に好きなものがある人はそれを使おう。

ない人は[https://code.visualstudio.com/](https://code.visualstudio.com/)からVisual Studio Codeをダウンロード！

# 
