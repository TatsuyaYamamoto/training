1. CSSとはなにか？
1. はじめてのCSS
1. セレクタとプロパティを理解しよう
1. もっとセレクタを使ってみよう
1. 属性セレクタを使ってみよう
1. 擬似クラスを使ってみよう
1. 擬似要素を使ってみよう
1. セレクタの詳細度を理解しよう
1. プロパティの値を指定しよう
1. ボックスモデルを理解しよう
1. borderで境界線のスタイルを変えよう
1. paddingで余白を制御しよう
1. marginとmarginの相殺を理解しよう
1. 文字に関するプロパティを使ってみよう
1. list-styleでリストのスタイルを変えよう
1. cursorでカーソルの形状を変えよう
1. backgroundで背景スタイルを変えよう
1. displayで要素の配置方法を変えよう
1. positionで位置を調整してみよう
1. z-index､overflowを理解しよう
1. line-height､vertical-alignを理解しよう
1. float､clearを使ってみよう 

## はじめてのCSS

- headタグ内のstyleタグにかく
- タグ内のstyle属性に書く
- 外部ファイルに書く

	```
	<link rel="stylesheet" href="hogehoge.css">
	```

## セレクタとプロパティを理解しよう

- どの要素にどのようにかくか
	
	```
	// セレクタ {プロパティ名: 値}
	p { color: skyblue; }
	```

- セレクタ
	- *
		- ユニバーサルセレクタ
		- すべて
	- 要素名
		- p, h1, div
	- #id
	- .class


## もっとセレクタを使ってみよう

複数のセレクタの書き方で意味が変わる

- h1, p{hoge: fuga;}
	- 複数のセレクタに同じスタイルを適用する
- div span{hoge: fuga;}
	- divの下にあるspanすべて
- div > b{hoge: fuga;}
	- divの直下にあるspanに適用する
- p + p{hoge: fuga;}
	- pの次に来るp要素
- a.point{hoge: fuga;}
	- p要素、かつpointクラスが付いたものに適用する


## 属性セレクタ

- aタグのうち、title属性があるもの

	```
	a[title]{hoge: fuga;}
	```

- aタグのうち、href属性がhttp://hoge.comのもの

	```
	a[href="http://hoge.com"]{hoge: fuga;}
	```
	
- 完全一致じゃない場合
	- aタグのうち、class属性内にsearchが含まれているもの

	```
	a[class~="search"]{hoge; fuga;}
	```

## 擬似クラスを使ってみよう

- 要素が特定の状態の時に指定するスタイル

- ul li
	
	```
	ul li:first-child { color: skyblue; }
	```
	
	- CSS3では*番目とか色々指定できる

- aタグ
	
	```
	a:link { color: violet; }
	a:visited { color: orange; }
	a:hover { color: pink; }
	a:active { color: red; }
 	```
 	
 	- 指定は上の順番で！cssの読み込みの関係
 
 - ある要素にフォーカスが当たったとき
 	
 	```
	input:focus { background: skyblue; }
	```

##  擬似要素を使ってみよう

ある要素の一部を指定する


- pタブの一行目

	```
	p:first-line{}
	```

- pタブの一文字目

	```
	p:first-letter{}
	```

- ある要素の直前直後にある要素を付け加えるとき

	```
	p:before{
		content: "hogegege";
	}
	p:after{
		content: "fugaga";
	}
	```


## セレクタの詳細度を理解しよう

- 複数のセレクタが指定された場合、どれが優先されるか
- 4種類ある
	- styleを直接タグに書く
	- id
	- 属性、擬似クラス
	- 要素、擬似要素
- あと、!important

```
/* 0, 0, 0, 1 */
a { color: skyblue !important; }
/* 0, 0, 1, 1 */
a.link { color: pink; }
/* 0, 0, 1, 1 */
a.search { color: orange; }
/* 0, 1, 0, 1 */
a#site { color: blue; }
```


## プロパティの値を指定しよう

- プロパティ
	- 長さ
	  - px
	  - em
	  - %
	- 色
	  - 名前
	  - RGB
	    - Red 0-f / 00-ff / 0-255 / 0%-100%
	    - Green
	    - Blue

``` 
body { font-size: 16px; }
h1 { font-size: 2em; } /* 32px */
h2 { font-size: 150%; } /* 24px */
 
h1 { color: blue; }
h1 { color: #00f; }
h1 { color: #0000ff; }
h1 { color: rgb(0, 0, 255); }
h1 { color: rgb(0%, 0%, 100%); }
```


## ボックスモデルを理解しよう

- 要素はそれぞれ四角い領域を確保する

- 要素の幅
	- width
- 要素の高さ
	- hight
	- hightで%を使うときは親要素の大きさを明示的に書く！
- 要素の枠
	- border
- 枠と要素の間
	- padding
- 枠と親要素との余白
	- margin


## borderで境界線のスタイルを変えよう

```
div {
  /* border-color: orange;
  border-width: 4px;
  border-style: dotted; */
  /* border: orange 4px dotted; */
  border-top: orange 4px dotted;
}
```

## paddingで余白を制御しよう


``` 
body { margin: 0; }

div {
  background: silver;
  /* padding: 10px 50px; */
  padding: 10px 20px 30px 40px;
}
```

body要素はmarginに初期値がある

## marginとmarginの相殺を理解しよう

- 上下にブロックボックスが並ぶときは、大きいmarginの数字のみが適用される

## 文字に関するプロパティを使ってみよう

```
p {
  color: silver;
  font-size: 24px;
  font-family: Arial;
  font-weight: bold;
  text-align: center;
  text-decoration: underline line-through;
}
```

## list-styleでリストのスタイルを変えよう

リストに関するプロパティ

- list-style-type
- list-style-image
- list-style-position
	- outsideがデフォルト
	- insideだとマーカーがリストの中に入るよ！
- list-styleで一変に記述してもOK
	- 順不同省略OK

	```
	ul{
		list-style: outside lower-alpha;
	}
	u
	```


## cursorでカーソルの形状を変えよう

カーソルの形状を変えるプロパティ

```
.help{
	cursor: help;
}
.dragme{
	curdor: move;
}
.img{
	cursor: url("hogehoge.jpg"), auto;
}
```

- 画像ファイルを使うときは、ファイルがなかったときの指定をする


## backgroundで背景スタイルを変えよう

- 要素の背景の設定

```
body{
	background-color: silver;
}
body{
	background-image: url();
	background-repeat: no-repeat;
	background-position: 10px, 10px;
	background-attachment: fixed;	/* スクロールに画像がついていくかどうか */
}
```

- backgroundプロパティで順不同で一度に書くことも出来る


## displayで要素の配置方法を変えよう


- htmlの要素の配置はブラウザでそれぞれ初期値が設定されている


- 下に積み重なる要素・・・ブロックボックス
	- h1, p
	- ブロックレベル要素
- 左に詰められる要素・・・インラインボックス
	- span aタグ
	- インラインレベル要素

- 要素によって配置の方法をかえたいとき、、
	- displayプロパティ
		- block
			- ブロックボックスにする
		- inline
			- インラインボックスにする
			- 幅、高さの指定が無効
		- list-item
			- リストのように左にマーカーをおく
		- inline-block
			- 左に詰めれれるが、ブロックボックスの性質
			- 幅と高さを指定出来る、inlineボックス
		- none
			- 要素を表示しない

## positionで位置を調整してみよう

要素の位置を調整する


- position
	- static
		- 初期値
	- relative
		- staticに対してずらす
		- top, left, right, bottomを指定する
	- fixed
		- スクロールにしても固定する
		- 配置の基準点はウィンドウの左上
	- absolute
		- 親要素のpositionを基準に位置を指定する
		- 親要素がstaticなら
			- windowの左上が基準
		- 親要素がstatic以外なら
			- 親要素の左上

## z-index､overflowを理解しよう

- z-index
	- 要素の重なり方を指定する
	- position static以外の要素のみに有効
- overflow
	- ブロック要素のコンテンツが幅高さを幅を超えているばあい
	- visible
		- デフォルト
		- そのまま表示
	- hidden
		- 隠れる
	- scroll
		- スクロールさせる

## line-height､vertical-alignを理解しよう

- ボックスモデル内の行単位に行ボックスが確保される
- line-height
	- 行ボックスの高さを指定する
- font-size
	- フォントの上から下までの高さを規定するためのプロパティ
- line-heightとfont-sizeの差分は上下に均等に配置される

```
p{
	line-hight: 1.5; // 単位なしだとfont-sizeの1.5倍
}
```


- vertical-align
	- 文章の途中や前後に表示する画像などのインラインレベル要素の縦位置の指定
	- imgとか
	- 初期値はbaseline(英文字の土台のライン)

## float､clearを使ってみよう

- float
	- 通常の配置の流れから切り離して、左右に配置する
	- 要素はブロックボックスを生成するので、widthを付ける
- clear
	- floatした要素の下に配置する
	- right
		- 右にfloatした要素の下に配置する
	- left
		- 左にfloatした要素の下に配置する
	- both
		- 両方

```
/*
float
clear
*/
 
h1, h2, p, img {
  border:1px solid #ddd;
}
 
img {
  float: right;	// ここだけ浮いてるように配置される。
  					// 他の要素はimg要素がなように配置される
  					// 行ボックスの中身はfloatされた要素を避ける
  width: 100px;
}
 
h2 {
  clear: right;
}
```
