`python manage.py makemigrations`
- 首先，django会检查创建或修改数据库的合法性，如果不合法会给出提示，比如CharField必须设置max_length，新增了没有默认值的非空字段。
- 第一次执行该操作：会在app下面创建migrations目录，并创建0001_inital.py文件，文件中记录了当前的建表、依赖等信息。
- 下一次执行该操作：
    - 如果有关于model.py的改动，会在migrations下生成已修改内容为名，类似0002_alter_permission_name_max_length.py的文件，文件中记录了你修改字段等信息
    - 如果没有改动则提示：No changes detected
    - 这些改动在此时都没有迁移到数据库！！！

`python manage.py sqlmigrate appname 0001`

可以查看下migrations 0001会对应于什么样子的SQL命令

`python manage.py showmigrations`

- 可以查看当前项目所有的app及对应的已经生效的migration文件，
- [x]表示migrte通过，[]表示未通过
- []migration文件未通过的，可以通过删除migrations下对应名称文件撤销这次更新

`python manage.py migrate`

将改动迁移到数据库，完成建表、修改字段等操作，操作成功后会在数据库django_migrations表中添加一条数据，表示migration文件已迁移,
若迁移不了，找到这条记录，可以删掉，就可以了


## Django 的admin UI
* [simpleui](https://github.com/newpanjing/simpleui)

Element-UI + Vue 加持的产品

* [admin-ui项目-知乎](https://zhuanlan.zhihu.com/p/72053134)