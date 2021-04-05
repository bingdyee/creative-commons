## install MongoDB
[Download MongoDB](https://repo.mongodb.org/yum/redhat/7/mongodb-org/4.4/x86_64/RPMS/mongodb-org-server-4.4.4-1.el7.x86_64.rpm)
```shell
rpm -ivh mongodb-org-server-4.4.4-1.el7.x86_64.rpm

vi /etc/mongod.conf
# bindIp: 0.0.0.0

firewall-cmd --add-port=27017/tcp --permanent
firewall-cmd --add-port=9090/tcp --permanent
firewall-cmd --add-port=3000/tcp --permanent
firewall-cmd --reload

systemctl enable mongod
systemctl start mongod
```

## install nodejs
[Download Node](https://nodejs.org/dist/v14.16.0/node-v14.16.0-linux-x64.tar.xz)

```shell
xz -d node-v14.16.0-linux-x64.tar.xz
tar -xf node-v14.16.0-linux-x64.tar

mv node-v14.16.0-linux-x64 /usr/local/nodejs

ln -s /usr/local/nodejs/bin/npm /usr/local/bin/ 
ln -s /usr/local/nodejs/bin/node /usr/local/bin/
```

## install YApi

npm install -g yapi-cli --registry https://registry.npm.taobao.org

yapi server
