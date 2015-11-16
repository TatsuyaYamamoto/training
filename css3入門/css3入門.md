1. CSS3とはなにか？
1. remを使ってみよう
1. rgba()､hsla()を使ってみよう
1. opacity()で透明度を操作しよう
1. 属性セレクタを使ってみよう
1. nth-childなどを使ってみよう
1. nth-of-typeなどを使ってみよう
1. もっと擬似クラスを見てみよう
1. border-radiusを使ってみよう
1. background-sizeを使ってみよう
1. 複数の背景画像を使ってみよう
1. linear-gradient()を使ってみよう
1. radial-gradient()を使ってみよう
1. box-shadow､text-shadowを使おう
1. transformで要素を変形させてみよう
1. ベンダープレフィックスを使おう
1. transitionを使ってみよう
1. animationを使ってみよう


## remを使ってみよう

- em
	- 親要素のpxの何倍かを表す
	- どの基準かわからなくなる、、、
- rem
	- ルート要素(html)を基準にする
	- 基準フォントが常におなじになる

## rgba()､hsla()を使ってみよう

- css3の色の指定
- 偶数
	- red, blue, green, alpha
- hsl/hsla
	- 直感的な色の操作が便利！
	- Hue(色相)
		- カラーホイールの角度ので色を指定する(0-365)
	- Saturation(彩度)
		- 0-100%
	- Lightness(明るさ)
		- 0-100%
	- Alpha


## opacity()で透明度を操作しよう

要素全体を透明にするプロパティ

- opacity
	- 0-1を指定


## 属性セレクタを使ってみよう

- css2.1で前やったこと
	- a[href]
	- a[href="foo"]
	- a[href~="foo"]
- css3では
	- a[href^="foo"] fooから始まる
	- a[href$="foo"] fooで終わる
	- a[href*="foo"] fooを含む
 
```
/*a[href^="http"] { color: orange; }*/
 
/*a[href$=".com"] { color: orange; }*/
 
a[href*=".co.jp"] { color: orange; }
```


## nth-childなどを使ってみよう

順番を表す擬似クラスの拡張


- css2.1で使った擬似クラス
	- :first-child
	- 子要素のなんばんめか

 
- li:last-child
	- 最後の要素
- li:nth-child(3)
	- 三番目
- li:nth-child(odd)
	- 奇数
- li:nth-child(even)
	- 偶数
- li:nth-child(3n+1)
- li:nth-last-child(4)
	- 後ろから、４番目
- li:only-child
	- 子要素が一つのみのとき

## nth-of-typeなどを使ってみよう

- ntf-childはあるようその子要素、の順番を指定する
- nth-of-typeは指定した子要素のみの、順番を指定する
	- sectionの中のp要素の間に他の要素があっても、**番目のp要素の指定、が出来る

- p:first-of-type
- p:last-of-type
- p:nth-of-type(3)
- p:nth-last-of-type(4)

```
h2:only-of-type
{
  background: violet;
}
```

## もっと擬似クラスを見てみよう


- :not()
	- 除外するものを指定する

	```
	li:not(.target){
		// .target以外のli要素
	}
	```

- empty
	- 中身がからの要素だけを指定する

	```
	li:empty{color: violet;} // 中身が空のli要素のみ紫にする
	```
- enabled
	- 要素がenabledのとき
- disabled
	- 要素がdisabledのとき
- checked
	- 要素がcheckedのとき
	
- 隣接する要素を指定したいとき！

	```
	input[type="checkbox"]:checked +
	label{
	}
	
	// チェックされているcheckboxがに隣接するlabel要素
	```
	
## border-radiusを使ってみよう

角丸を付ける


- border-radius: 10px
	- 角丸を付ける
- border-radius: 10px/20px;
	- 楕円の角丸を付ける
- border-bottom-right-radius: 10px;
	- 右下に角丸を付ける
- border-radius: 10px　20px 30px;
	- 左上、右上左下、右下に角丸を付ける
- border-dadius: 50%
	- 要素を円にする
- 要素の背景をつければアイコンになるよ！

## background-size

- backgroundをそのまま書くと、そのままの寸法が表示される
- background-size: 50%;		//横幅が50%になる(縦横比も維持)
- background-size: 50% 100%;		//横幅が50%、縦幅は100%
- background-size: cover	//縦横比を維持しながら背景領域をカバーする(はみ出たところはカット)
- ackground-size: contain	//比を維持しながら、全体を表示する
- 上下左右に均等に切り取る、はみ出させるときは
	- background-position: 50% 50%;

## 複数の背景画像を使ってみよう

```
header{
	backgount:
				url(hoge.jpg) no-repeat 0 0,
				url(fuga.jpg) no-repeat 30px 30px,
				url(fuga.jpg) no-repeat 30px 30px;
```


## linear-gradient()を使ってみよう

- 線形グラデーション
	- css3のグラデーションは画像を生成するためのもの
	- backgroung-image: linear-radient(skyblue, blue);


```
div {
  width: 200px;
  height: 200px;
  background-image: repeating-linear-gradient(
    lightgreen, skyblue 20px);
}
div {
  width: 200px;
  background-image: linear-gradient(to left top, skyblue, blue);
}
```

## adial-gradient()を使ってみよう

- 円形グラデーション

```
div {
  width: 200px;
  height: 200px;
  background-image: radial-gradient(circle 20px at 30px 40px, skyblue, blue);
}

div {
  width: 200px;
  height: 200px;
  background-image: repeating-radial-gradient(
    skyblue, blue 20px);
}
```

## box-shadow､text-shadowを使おう

- 領域やテキストに影を付ける
- box-shadow
	- 四角い領域に影を付ける
- text-shadow
	- inset使えない


```
div {
  width: 200px;
  height: 100px;
  background: #fff;
  				// 影の位置, ぼかし幅, 影の大きさ, 色　を指定する
  box-shadow: 10px 20px 4px 10px  rgba(0,0,0,.4) inset,
  10px 20px 4px 10px skyblue;
}
 
h1 {
  text-shadow: 2px 2px 0   rgba(0,0,0,.4);
  // 4番目の影の大きさしてが出来ない
  // inset使えない
}
```

## transformで要素を変形させてみよう


-  transform:translate(20px, 40px);
	-  x, y方向へ移動させる
-  transform:translateX(20px);
	-  X方向へ移動させる
-  transform:scale(0.5, 1.5);
	-  倍率指定
-  transform:skew(10deg, 20deg);
	-  傾斜
-  transform:rotate(30deg);
-  transform-origin: 50% 50%;
-  transform-origin: 0 0;
	-  変形の基点

## ベンダープレフィックスを使おう


- ベンダープレフィックス
	- 実験的な拡張機能という明示的な宣言
	- -moz-
	- -o-
	- -webkit-
	- -ms-
- 普通の命令にベンダープレフィックスを付ける！

	```
	-webkit-transform:rotate(30deg);
	transform:rotate(30deg);
	```

## transitionを使ってみよう

- transition
	- 要素のアニメーションを設定する

```
div{
	width: 100px;
	height: 40px;
	background-color: skyblue;

	transition-property: all;	// どれをアニメーションするか
	transition-duration: 2s;	// どれだけかけるか
	transition-timing-function:ease;	// 変化のクセ
	transition-delay:0.8s;		// 開始までの時間
}

div:hover{
	background-color: orange;
	width: 500px;
}
```


## animation

- キーフレームを使った複雑なアニメーション
- transitionより複雑なanimatinoを実現するもの

```
div#aaa{
	border: solid black;
	width: 100px;
	height: 40px;
	background-color: orange;

	-webkit-animation-name: slidein;
	-webkit-animation-duration: 1s;
	-webkit-animation-delay: 0s;
		-webkit-animation-timing-function: ease;
  -webkit-animation-iteration-count: 3;	//繰り返し回数 infinitで無限
  /*-webkit-animation-direction: alternate;*/	// 繰り返しを左右におこなうか

}
@-webkit-keyframes slidein{
	// アニメーションの様子を詳しく記述する
	//最初
	0%{
		margin-left: 100%;
		background-color: blue;
	}
	// 70%終わったら
	70%{
		margin-left: 50%;
		background-color: blue;
	}
	100%{
		margin-left:100%;
		background-color: skyblue;
	}
}
```