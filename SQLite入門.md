# SQLite入門

## データベース用語を理解しよう

- データベース
	- アプリ毎のデータの塊
	- DB > table > field
- テーブル
- フィールド、カラム
	- 列
- レコード
	- 行

## データベースを操作

- create tables users(name, email);
- drop table users;
- 改行もできる
- .tables
- .schema


## テーブルを変更

- テーブル名変更
- カラム追加

```
sqlite> alter table users rename to dot_users;
sqlite> .tables
dot_users  test     
sqlite> alter table dot_users add column pwd;
sqlite> .schema dot_users
CREATE TABLE "dot_users"(name, email, pwd);
```

- カラムの削除、リネームは別の方法が要るよ


## データ型を指定


- 使えるデータの型
	- NULL
	- INTEGER
		- 整数値
	- REAL
		- 少数
	- TEXT
		- 文字列
	- BLOB
		- binary large object
- sqliteはデータ型は必須じゃない！
- データ型をしていすると、努力はするけれど確約はしない、、、、

## テーブル作成時のオプション

```
create tables users (id integer primary key autoincrement, name text not null, email text unique, age integer default 20);
```

```
// 条件、インデックス
sqlite> create table lessons (title, count_lessons check(count_lessons>0));
sqlite> .schema lessons
CREATE TABLE lessons (title, count_lessons check(count_lessons>0));
sqlite> create index age on users(age);
sqlite> .schema users
CREATE TABLE users (id integer primary key autoincrement, name text not null, email text unique, age integer default 20);
CREATE INDEX age on users(age);

```

## データを挿入

```
insert into users (name, email, age) values("yamamoto", "yama@moto.com", 20);
```

- nullの時は"null"と書く


## データを抽出


- 普通

```
sqlite> select * from users;
yamamoto|yama@moto.com|20
sqlite> select age from users;
20
sqlite> select * from users limit 3;
yamamoto|yama@moto.com|20
```

- 並べ替え

```
sqlite> select * from users order by age;
yamamoto|yama@moto.com|20
sqlite> select * from users order by age desc;
yamamoto|yama@moto.com|20

```

- where句

```
sqlite> select * from users where namr = yamamoto;
Error: no such column: namr
sqlite> select * from users where name = yamamoto;
Error: no such column: yamamoto
sqlite> select * from users where name = "yamamoto";
yamamoto|yama@moto.com|20
sqlite> select * from users where name = "yama%";
sqlite> select * from users where name like "yama%";
```

## 組み込み関数


- 件数

```
select count(*) from users;
```

- 最大値

```
select max(age) from users;
```


- ランダム

```
select random();
7347506804631522490
```

```
// ランダムに並び替えて1件抽出
select * from users order by random() limit 1;
```


- length、型

```
// 文字列の長さ、型を表示する
select name , length(name), typeof(name) from users;
```


## データ集計


- ユニークな値を抽出

```
select distinct team drom users;
```


- 合計 チームの名前で集計して、チーム名とスコアを出す

```
select team, sum(score) form users group by team;
```


## 日付・時刻


```
sqlite> select current_date;
sqlite> select current_timestamp;
```

```
insert into users (name, created) values ("hoge", current_timestamp);
```



- strftime
	- 時間を表す文字列をあるフォーマットに変換する

```
select strftime('%Y年', current_timestamp);
```