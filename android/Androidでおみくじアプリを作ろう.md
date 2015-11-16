# Androidレイアウト入門
## 目次

1. おみくじアプリを作ってみよう
1. 開発の準備を整えよう
1. 画面を作っていこう
1. 乱数を表示させてみよう
1. おみくじを表示させてみよう
1. テキストの色を変えてみよう
1. テーマを変えてみよう
1. strings.xmlを使ってみよう


## 画面を作っていこう
- 部品を上下に並べたいときはLinearLayout
- 要素の中身を寄せる
	- android:gravity=center
- 文字
	- android:textSize
	- android:textStyle
- イベント登録
	- android:onClick="***"
	- activity内のメソッドを呼ぶ



## 乱数を表示させてみよう

- Viewのメソッドの引数はView
- findViewById(R.id.***)
- randomクラス
- TextView.setText(***)


## おみくじを表示させてみよう


## テキストの色を変えてみよう
- 色の指定
	- keyword
		- Color.RED, Color.BLACK
		- 12種類しかない
	- RGB
		- Color.rgb(255,0,0)
	- argb
		- Color.argb(127, 255,0,0)
	- 16進数
		- Color.parseColor("#ff0000")
- TextView.setTextColor


## テーマを変えてみよう

- アクションバーやテキストの色等を統一的に
	- 予めテーマが設定されている
- Mnifestファイル
	- android:theme
	- values > styles > AppTheme
- styles.xmlで指定したテーマとactivutyのプレビューは連動していない！
	- エミュレーターで確認するのが大事！


## strings.xmlを使ってみよう


- strings.xmlで文字列の抜き出しが出来る
- View
	- android:tet="@string/hogehoge"
- strings.xml
	- <string name="hogehoge">なかみの部分！</string>