# Vagrant入門
## 目次

1. Vagrantとはなにか？
1. Boxを取得してみよ
1. vagrantbox.esを使ってみよう
1. 仮想マシンを立ち上げてみよう
1. 仮想マシンの停止･再起動･削除
1. 仮想マシンに接続してみよう
1. Webページを表示させてみよう
1. 共有フォルダを使ってみよ
1. Provisioningを使ってみよう１
1. Provisioningを使ってみよう２
1. 自分でBoxを作ってみよう
1. pluginを使ってみよう
1. saharaを使ってみよう


## Boxを取得してみよう

1. Boxを取得
	- vagrant box add ***

	```
	vagrant box add hashicorp/precise32
	```
	
	- BOXの確認

	```
	vagrant box list
	```
	
1. 仮想マシンを初期化

## vagrantbox.esを使ってみよう

- vagrantbox.esからBoxを取得できる
- boxを削除するには

	```
	vagrant box remove
	```
- 追加されたboxは
	
	```
	~/.varant.d/boxes
	```
## 仮想マシンを立ち上げてみよう

- テンプレート１つで複数個のVMが立ち上げられるよ
- 初期化
	```
	vagrant init [box name]
	```
- VagrantFileが出来る
- 仮想マシンを立ち上げる
	- Vagrantfileがあるディレクトリで
	
	```
	vagrant up
	```
## 仮想マシンの停止･再起動･削除

- 状態操作
	- 状態を見る
		- status
	- スリープさせる
		- suspend
	- 復帰させる
		- resume
	- 終了させる
		- halt
	- 再起動
		- reload
- VM自体を削除
	- destroy

## 仮想マシンに接続してみよう

- VMに接続
	
	```
	vagrant ssh
	```

- ネットワークの設定
	- vagrant fileで行う
	- デフォルトでプライベートIPアドレスが設定されているので、これでOK
		- http://192.168.33.10/

## 共有フォルダを使ってみよう

- VMのファイルをlocal上で編集したい
	- 共有フォルダがあるよ
- vagrantfileがあるディレクトリ <--> VM: /vagrant
- シンボリックリンクを使えば、VMへのデプロイが楽


## Provisioningを使ってみよう

- Provisioning
	- vagrant upをした後に実行される一連の処理
- シェルで1行各だけなら、、、
	- vagrantfileに書くだけ
	- config.vm.provision :shell, :inline => "echo hello waaa!"


- 外部ファイルにかくなら、、、
	- config.vm.provision :shell, :path => "provision.sh"
	
	```
	sudo yum -y install httpd
	sudo service httpd start
	sudo chkconfig httpd on
	```

- 既にVMが立ち上がっていれば、provisioningだけを走らせられる！
	
	```
	vagrant provision
	```

## 自分でBoxを作ってみよう

- 今動いているVMをそのままBOX化する

	```
	vagrant package
	```