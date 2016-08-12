# 0711_playbook  
一旦書いただけの状態。動作確認はこれから。
TODO user 作成のものを書く
TODO　実行コマンドを書く

# playbookを流す前にやるべきこと  
実際には、ちゃんとこの部分もかけばいけるものもある。それについては★マークを付ける。
* sudoer  wheel 設定 　★
* admin ユーザ作る  useradd admin -G wheel 　★
* sudo yum install libselinux-python   (どこかで入れればよい？　selinux 設定まえ) ★
  
# コマンド   
`ansible-playbook -u vagrant -k -c paramiko -i inventories/front_vagrant  front-playbook.yml`  
