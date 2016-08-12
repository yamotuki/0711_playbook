# 0711_playbook  

## ansible version  
1.9.4 で動作確認中　  
2.0系で動くかどうかは不明。sudo yum install epel-release; sudo yum install ansible でインストールしたもの。  

## playbookを流す前にやるべきこと  
実際には、ちゃんとこの部分もかけばいけるものもある。それについては★マークを付ける。
* sudoer  wheel 設定 　★
* admin ユーザ作る  useradd admin -G wheel 　★
* sudo yum install libselinux-python   (どこかで入れればよい？　selinux 設定まえ) ★
  
## コマンド   
`ansible-playbook -u vagrant -k -c paramiko -i inventories/front_vagrant  front-playbook.yml`  
