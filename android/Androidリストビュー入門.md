# Androidリストビュー入門

## リストビューを扱ってみよう


- リスト上にテキスト、アイコン、イベントを付与していく



## 開発の準備を整えよう




## リストビューを設置しよう

- リストビューを使うときはwidth, heightをmatch_parentにする
	- じゃないと、毎回大きさを計算しないといけない
- ListViewの中身の行のレイアウトは別レイアウトファイルを作成する


## データを表示してみよう

- リストビューを使うには、、、、
	1. データを準備
		- arrayListで準備して
	1. adapter
		- arrayAdapter
			- 引数
				- context
				- 行のレイアウト(ListViewじゃないぞ！)
				- データ
	1. ListViewに表示
		- setAdapter()

## setEmptyView()

- リストのアイテムがなかった時に、別のアイテムを表示させる。
- ListViewと並列に記述する
	- TextViewを使うよー

- setAdpater()する前にsetEmptyVIew(R.id."textview")をする


## 複雑な行レイアウト

アイコンと２行の文字列のリスト

- リストアイテムのレイアウトファイルに書いていく
	
	```
	<linear>
		<image>
		<linear>
			<test></text>
			<text></text>
		</linear>
	<l/inear>
	```
	
## 独自のAdapter


## ViewHolder

- 要素の参照を保持するクラスで検索を一回にする


## タップしたときの処理を実装しよう

リストアイテムにタップイベントを付与する