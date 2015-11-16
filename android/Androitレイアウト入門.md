# Androidレイアウト入門
## 目次
1. レイアウトについて学ぼう (02:05)
1. 用語の整理をしておこう (02:37)
1. Designタブを使ってみよう (02:41)
1. LinearLayoutを使ってみよう (02:11)
1. Viewの幅や高さを指定してみよう (02:04)
1. 余白と寄せ方について理解しよう (02:42)
1. android:layout_weightを使おう (01:53)
1. RelativeLayoutを使ってみよう (02:42)
1. FrameLayoutを使ってみよう (01:56)
1. TableLayoutを使ってみよう (02:41)



## 用語の整理をしておこう

### View

- View
	- ラベルやボタンの部品のこと
	- いろいろある
		- TextView
		- EditText
		- Button
		- imageView
		- などなど
- ViewGroup
	- Viewをまとめて配置したいとき
	- Viewのいれもの
	- 内包するViewの配置方法で色々ある
		- Linear
		- TableLayout
		- RelativeLayout
		- FrameLayout
- ViewGroupも組み合わせられる
	- ViewGroupの中にViewGroupを入れる


### 配置、余白

- android:layout_height
- android:layout_width
- android:padding
- androir:layout_margin
- android:gravity
	- Viewの中の中身を寄せるとき
- android:layoutGravity
	- VIew自体を上下左右に寄せる


## Designタブを使ってみよう

- 部品の配置方法は2つ
	- designタブ
	- textタブ
- ComponentTreeで部品の構造がわかる
- Propertyでそれぞれの要素を変えられる
	- ここで変えると、textviewのxmlも変わる
- 部品は左のパレットで追加できる
	- Relativeなら親要素に対して相対的に配置出来る


## LinearLayoutを使ってみよう
- option command l でフォーマットができる！
- xmlnsは名前空間？の指定
- LinearLayoutは縦横順番に内包している要素を並べる
	- 方向を指定するのが、android:orientation
	- panddingとかはrelativeと違っていらない？
	
## Viewの幅や高さを指定してみよう

- 横幅と縦幅の指定方法
- 幾つかのkeyword
	- match_parent
		- 親要素の幅に合わせる
	- wrap_content
		- 中身の幅に合わせる
	- 任意の数字
		- ***dp

## 余白と寄せ方について理解しよう (02:42)

- 余白
	- android:layout_margin
	- android:padding
- 寄せ方
	- android:gravity
	- android:layout_gravity
- 一方向に設定するなら、後ろにkeywordを設定する
	- layout_marginBottom


## android:layout_weightを使おう

- LinearLayoutの余白を書く要素に振り分ける
	- 割合で指定して、余白を詰める！
- android:layout_weightで指定する
- orientationの方向によって、layout_width(or height)が意味なくなる
	- その場合は0dpを指定する


## RelativeLayoutを使ってみよう

- 数値を相対的に指定できる
- 相対的に要素を配置するには、その対象に名前が必要
	- android:id="@+id/a"
- 親要素に対して真ん中
	- android:layout_centerInParent="true"
- 他要素に対して揃えるには
	- andorid:layout_align***
- 近接に奥には
	- android:layout_belowとかtoRightOf

## FrameLayoutを使ってみよう

- 内包されるViewを重ねて表示できる
- 後から書いたものがどんどん重なっていく


## TableLayoutを使ってみよう

- 表組みのようなレイアウト
	- Layoutの中にTableRow(ViewGroup)で行を作られる
- android:layout_span
	- 何列分の要素かを指定できる
- androdi:layout_column
	- 何列目の要素かを0から順番に指定出来る