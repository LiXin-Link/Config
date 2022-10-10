# 解决Docker必须使用sudo操作的问题

1. 创建docker组：`sudo groupadd docker`
2. 将当前用户加入docker组：`sudo gpasswd -a ${USER} docker`
3. 重启服务：`sudo systemctl restart docker` （或者`sudo service docker restart`）
4. 刷新docker成员：`newgrp - docker`