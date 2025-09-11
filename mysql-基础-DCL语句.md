DCL是数据控制语言

1.DCL-管理用户

use mysql;

select * from user;

2.创建用户

create user '用户名'@'主机名' identified by '密码';

3.修改用户密码

alter user '用户名'@'主机名' identified wih mysql_native_password by '新密码';

4.删除用户

drop user '用户名'@'主机名';

![image-20250911110137218](E:\密码存储与注册\image-20250911110137218-1757559698370-5.png)

DCL-权限控制

![image-20250911110311727](E:\密码存储与注册\image-20250911110311727-1757559792962-7.png)

1.查询权限

show grants for '用户名'@'主机名';

2.授予权限

grant 权限列表 on 数据库名.表名 to '用户名'@'主机名';

3.撤销权限

revoke 权限列表 on 数据库名.表名 from '用户名'@'主机名';