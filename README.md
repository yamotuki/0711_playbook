# 0711_playbook  

## ansible version  
1.9.4 で動作確認中　  
2.0系で動くかどうかは不明。sudo yum install epel-release; sudo yum install ansible でインストールしたもの。  

## playbookを流す前にやるべきこと  
実際には、ちゃんとこの部分もかけばいけるものもある。それについては★マークを付ける。
* sudoer  wheel 設定 　★
* sudo yum install libselinux-python   (どこかで入れればよい？　selinux 設定まえ) ★
* 手元のansible control 環境の公開鍵をadminユーザのadmin.pubのリストに追加しておく

## コマンド   
### adminユーザの作成
`ansible-playbook  -u vagrant -k -c paramiko -i inventories/front_vagrant  user-playbook.yml`  

### いろいろセッティング
adminユーザを作成した上で用いる。現在のところ ansible 2.1.0の問題か分からないが、adminユーザに直接入って流そうとすると問題が起こるので-u vagrantでユーザ指定。
`ansible-playbook -u vagrant -k -c paramiko -i inventories/front_vagrant  front-playbook.yml`  

## userの役割  
* admin: install とかサーバ管理のためにinfra全権を持っているユーザ
* common: アプリケーションを動かすためのユーザ。sudo権限なし。rubyなどはこのユーザにのみインストールされる

