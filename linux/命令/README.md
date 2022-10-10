# 用户操作

## 创建用户并添加sudo权限

创建一个用户组`groupadd link`

创建一个用户（我这里叫link）：`useradd -m link -g link -s /bin/bash -d /home/link`

设置密码：`passwd link`

添加sudo权限：`vim /etc/sudoers`，在`root ALL=(ALL) ALL`下追加：`link ALL=(ALL) ALL`

## 禁用root用户登录

`vim /etc/ssh/sshd_config`找到`PermitRootLogin`，把`PermitRootLogin yes`改为`PermitRootLogin no`  
（ps: vim下可以使用 / 搜索，n下一个，N上一个，字符串后面加\c可以不区分大小写搜索）

重启服务`service sshd restart`

## gpasswd

```
用法：gpasswd[-a user][-d user][-A user,...][-M user,...][-r][-R]groupname
参数：
    -a：添加用户到组
    -d：从组删除用户
    -A：指定管理员
    -M：指定组成员和-A的用途差不多
    -r：删除密码
    -R：限制用户登入组，只有组中的成员才可以用newgrp加入该组 
```

### 把当前用户加入到某个组：

```sh
sudo gpasswd -a ${USER} 组名
```

