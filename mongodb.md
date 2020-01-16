## mongodb

#### 内建角色

> 数据库用户角色：read、readWrite
>
> 数据库管理角色：dbAmin、dbOwner、userAdmin
>
> 所有数据库角色：readAnyDatabase、readWriteAnyDatabase、userAdminDatabase、dbAdminAnyDataBase
>
> 超级用户角色：root  
>
> <以下角色间接或直接提供了系统超级用户的访问>
>
> dbOwner、userAdmin、userAdminAnyDatabase

#### 角色说明

> read：允许用户**读取**指定数据库
>
> readWrite：允许用户**读写**指定数据库
>
> dbAdmin：允许用户在指定数据库中执行**管理函数**，如索引创建、删除、查看统计或访问system.profile
>
> userAdmin：允许用户向syste.users集合写入，可以在指定数据库里创建、删除和管理用户
>
> readWriteAnyDatabase：只在admin数据库可用，赋予用户所有数据库的读写权限
>
> userAdminAnyDatabase：只在admin数据库可用，赋予用户所有数据库的userAdmin权限
>
> dbAdminAnyDatabase：只在admin数据库可用，赋予用户所有数据库的userAdmin权限
>
> root：只在admin中可用，超级账号，超级权限

