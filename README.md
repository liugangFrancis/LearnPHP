# LearnPHP


更改linux 数据库密码


更改aws 密钥
1. 从aws或者自己生成 获取pem 文件即私钥文件
2. 命令行输入   ssh-keygen -y 
3. 输入pem 文件路径
4. 得到公有密钥：
如：ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQClKsfkNkuSevGj3eYhCe53pcjqP3maAhDFcvBS7O6V
hz2ItxCih+PnDSUaw+WNQn/mZphTk/a/gU8jEzoOWbkM4yxyb/wB96xbiFveSFJuOp/d6RJhJOI0iBXr
lsLnBItntckiJ7FbtxJMXLvvwJryDUilBMTjYtwB+QhYXUMOzce5Pjz5/i8SeJtjnV3iAoG/cQk+0FzZ
qaeJAAHco+CY/5WrUBkrHmFJr6HcXkvJdWPkYQS3xqC0+FmUZofz221CBt5IMucxXPkX4rWi+z7wB3Rb
BQoQzd8v7yeb7OzlPnWOyN0qFU0XA246RA8QFYiCNYwI3f05p6KLxEXAMPLE

如果提示失败：注意pem 是否存在，是否能够访问：不能访问执行： sudo chmod 400 my-key-pair.pem

5. 登录ec2服务器 ，替换或者删除 ~/.ssh/authorized_keys
替换里面内容 或者添加上面得到的公有密钥


更改linux mysql服务器账号密码

使用数据库查询语句直接更新用户表
mysql -uroot -p
输入旧密码
mysql>use mysql;  // 进入mysql 表
mysql>update user set password=passworD('new password') where user='root'
mysql>flush privileges; // 重新加载权限表，更改权限


在忘记root密码时，可以采用如下方法:安全模式
mysqld_safe --skip-grant-table&
mysql -u root mysql
mysql> update user set password=password('new password') where user='root';
mysql> flush privileges;  // 重新加载权限表，更新权限








