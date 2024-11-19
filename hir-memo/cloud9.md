cloud9が使えなくなったので代替でEC2をパブリックサブネットに作成する。
EC2にはsshでアクセスする。

```
sudo ssh -i [秘密鍵のディレクトリ] ec2-user@[AWSのパブリックIPアドレス] -p 22
```

まずgitをインストールするところから始まる。

```
 sudo yum update
 sudo yum install git

 git version
# git version 2.40.1
```

あとは書籍通り git clone。

Nodeもインストールする必要あり。
nvmを使ってバージョン指定した上で入れる。

```
git clone https://github.com/creationix/nvm.git ~/.nvm
source ~/.nvm/nvm.sh
```

viで設定

```
vi .bash_profile
```

下記を追加

```
# nvm
if [[ -s ~/.nvm/nvm.sh ]] ; then
        source ~/.nvm/nvm.sh ;
fi
```

書籍のバージョンに合わせてインストール

```
nvm install 14.16.1
nvm use 14.16.1
```

node -v できちんと表示されればOK