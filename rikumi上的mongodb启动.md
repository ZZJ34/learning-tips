## rikumi上的mongodb启动



➜  ~ mongo --port=27881
MongoDB shell version v4.0.2
connecting to: mongodb://127.0.0.1:27881/
MongoDB server version: 4.0.2
> show dbs
> 2019-10-08T16:04:58.353+0800 E QUERY    [js] Error: listDatabases failed:{
>         "ok" : 0,
>         "errmsg" : "command listDatabases requires authentication",
>         "code" : 13,
>         "codeName" : "Unauthorized"
> } :
> _getErrorWithCode@src/mongo/shell/utils.js:25:13
> Mongo.prototype.getDBs@src/mongo/shell/mongo.js:67:1
> shellHelper.show@src/mongo/shell/utils.js:876:19
> shellHelper@src/mongo/shell/utils.js:766:15
> @(shellhelp2):1:1
> use admin
> switched to db admin
> db.auth({user:'admin', pwd:'heraldmongo#FKGFW'})