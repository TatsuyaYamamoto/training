1. HTMLとはなにか？
1. 必要なツールを用意しよう
1. タグと属性を理解しよう
1. はじめてのHTML
1. meta､linkタグを使ってみよう
1. styleタグを使ってみよう
1. id､class､style属性を使ってみよう
1. セクションについて理解しよう
1. アウトラインを意識してみようh1-h6タグで見出しを付けよう
1. p､hr､pre､key､divを使おう
1. ol､ul､li､dl､dt､ddでリストを作ろう
1. strong､br､spanを使ってみよう
1. aタグでリンクを設定しよう
1. imgタグで画像を表示させよう
1. tableタグで表組みを作ろう
1. formタグでフォームを作ろう
1. inputタグで入力部品を作ろう
1. textarea､buttonタグを使ってみよう
1. checkbox､radio､labelを使ってみよう
1. selectタグでセレクトボックスを作ろう
1. HTML5から使える属性を使ってみよう
1. 文字参照を使ってみよう
1. コンテンツモデルを理解しよう


## 必要なツール
- ブラウザ
	- chromeで
- テキストエディタ
	- atom
- フォント
	- Ricty Diminished

## 基本的な用語

1. タグ
	- 文章にはタグで意味付けをする
1. 属性
	- タグに付帯情報を与える

```
<タグ 属性=値 属性=値>文章</タグ>

<タグ/>
```

## はじめてのHTML

## meta､linkタグを使ってみよう


- <!DOCTYPE html>
	- 文章宣言
	- 決まり文句
- html lang="ja"
	- 言語設定
- head
	- titleタグ
	- meta charset
	- meta name="description"  content="説明文"
	- linkタグ
		- rel="shortcut icon" href="**.ico"
			- ファビコン

## styleタグを使ってみよう


- styleタグはcssを書くことが出来る

	```
	body {background; skyblue}
	```

- 外部ファイルにcssを記述する
	- linkタグ
	
	```
	<link rel="stylesheet" href="hoge.css">
	```
	
## id､class､style属性を使ってみよう

- すべてのタグに付けられる属性・・・グローバル属性
	- id
		- ページ内に1つしか無い要素に使う
		- ページ内をジャンプしたり
		- プログラムが要素を取得したりする
	- class
		- ページ内に複数ある要素を指定するときに使う
		- 複数のクラスを同時に扱える(空白で区切る)
	- style
		- スタイルを直接指定する
	
## セクションについて理解しよう、アウトラインを意識してみよう

- bodyタグ内で使うタグ
- 文章のセクションを区切るためのタグ
	- header
	- footer
	- nav
		- ナビゲーション
	- article
		- それ自体で独立しているメインのコンテンツ
		- 有志記事、ブログエントリー
		- そのまま切り取っても大丈夫なようなもの
	- aside
		- 副次的なコンテンツ
	- section
		- 上記の何かに当てはめられない情報の塊
	- h1 - h6
		- セクションにつける見出し
		- body全体でh1-h6じゃない
		- セクションの塊ごとに順番をつける


## 

セクションより細かいレベルのグルーピング

- pタグ
	- パラグラフ
- hrタグ
	- 話題転換
	- horizontal rule
- preタグ
	- 改行や字下げを維持する
- blockauote
	- 引用
- div
	- スタイリング用

## ol､ul､li､dl､dt､ddでリストを作ろう

- ol: orgered list
- ul: unordered list
- li: list item



- dl: definition list
- dt: definition term
- dd definition description




## strong､br､spanを使ってみよう

- strong
	- 重要な箇所を表す
- br
	- line break
	- 改行
- span
	- 意味は無い
	- テキストの一部に装飾を施すときに使う

## aタグでリンクを設定しよう

- リンクを貼るためのリンク
- aタグ
	- href属性
	- target属性
- ページ内リンク
	- href="#hogehoge"

## imgタグで画像を表示させよう

- imgタグ
	- src="hoge.jpg"
	- width, height属性
	- alt属性
		- 代替情報
		- 表示されなくても、"正しいmarkup"になるよ

## tableタグで表組みを作ろう

- table
- thead
- tbody
- tr: table row
- th: table header
- td: table data

```
<table>
	<thead>
		<tr>
			 <th>size</th><th>price</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			 <td>S</td><td>150</td>
		</tr>
	</tbody?
```

## formタグでフォームを作ろう、 inputタグで入力部品を作ろう

- ユーザーからの入力を受け付けてデータを送信する


- formタグ
	- action属性
		- どこに送るか
	- method属性
		- get
		- post
- inputタグ
	- name属性
		- 送信内容(value)のkeyってことっぽい
	- value属性
	- size
		- 幅
	- maxlength
		- 最大文字数
	- placeholder
		- 薄く表示させる内容
	- type = "password"
	- type = "hidden"
		- 画面上に表示されない
		- 送信する内容が決まっているもののnameとvalueを書いてsubmitと一緒に送信させる

 

```
<form action="survey.php" methpd="post">
	<p>メールアドレス：<input type="text" name="email"></p>
	<p>メールアドレス：<input type="text" value="送信”"></p>
</form>
```


- textareaタグ
	- name属性
	- cols属性
	- rows属性
- buttonタグ
	- type="submit"で送信できる！
	- ボタン内の内容をよりリッチに出来るよー
	- type="button"
	- disable属性
		- 無効化

## checkbox､radio､labelを使ってみよう

- inputタグ
	- type="checkbox"
		- checkedを書くとチェック済みになる
		- name, valueで送信データーを設定する
	- type="radio"
- labelタグ
	- 紐付けた要素のクリックでもチェックできる

## selectタグでセレクトボックスを作ろう

- selectタグ
	- selected
	- multiple
		- 複数選択させる
	- size属性
	- name属性
- optionタグ
	- name属性

```

<select name="city">
	<option value="tokyo">tokyo</option>
	<option value="osaka" selected>osaka</option>
</select>	
```



## HTML5から使える属性を使ってみよう

- type属性
	- email
	- number
	- date
- required
- novalidate
	- チェック無効化
- 注意事項：使えるブラウザが限られている


## 文字参照を使ってみよう

- タグとして解釈されてしまうケース、記号をどうするか
- 文字参照
	- &lt;
	- &gt;
	- &quot;

## コンテンツモデルを理解しよう

- 全てのタグにはカテゴリとコンテンツモデルが定義されている
- カテゴリ：どの分類か
- コンテンツモデル：どのカテゴリーのタグを入れられるか
	- トランスペアレント：親要素のコンテンツモデルを使ってね

