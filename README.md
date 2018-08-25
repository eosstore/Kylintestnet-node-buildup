# Kylintestnet-node-buildup
how to quickly build nodeos on CryptpKylin

##1.先下载成功下载eosio源码##

git clone https://github.com/EOSIO/eos.git --recursive

cd eos

git submodule update --init --recursive

git checkout <tagxxx>

./eosio_build.sh
安装，安装的默认路径是/usr/local/eosio/bin/路径下：

./eosio_install.sh

##2.下载eosstore程序启动包##

git clone https://github.com/eosstore/Kylintestnet-node-buildup.git

##3.从eosstore获取最新的data数据备份并放到eos-data目录下##

./get_ubuntu_data.sh https://s3-ap-northeast-1.amazonaws.com/cryptokylin-eosstore/2018-08-23-02_12_54.tar.gz

##4.用部署systemctl服务，并且启动eosio程序##

./set_kylinservice.sh

systemctl start kylin.service
注意：代码下载路径默认是/root，当前的路径是/root/Kylintestnet-node-buildup/eosio-node/,如果路径不正确，需要自己修改kylin.service中的nodeos启动路径。

##5.查看log##

tail -f kylin.log
