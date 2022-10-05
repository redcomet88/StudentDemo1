# 开源 Django 学生管理前后端分离 Vue +  Django + MySQL DEMO 01  CRUD
## 0 联系方式
作者支持定制
QQ: 3397640089 (备注：github来的)
QQ: 1693353672 (备注：github来的)
B站 更多作品展示: https://space.bilibili.com/1583208775/
## 1 功能介绍

主要实现了登录、注册用户管理以及学生信息的CRUD，是一个使用vue + django + mysql实现的前后端分离的样例程序， 开源的地址评论区给出。

### 1.1 实现的功能

- [ ]  前后端分离页面
- [ ]  主页
- [ ]  登录与注册
- [ ]  学生管理：查询、增加、修改、删除

### 1.2 架构图

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bbe51c24-9315-4bea-a19b-0f12001c5fd9/Untitled.png)

### 1.3 功能实现截图

## 2 技术架构

### 2.1 前端

- vue
- axios
- bootstrap

### 2.2 后端

- django
- django rest framework
- pymysql
- django-cors-headers

### 2.3 数据库

- mysql
- 表：  tb_user (用户表) 、 tb_student (学生表)

## 3 开发笔记

### 3.1 项目的初始化

创建一个新的app。

```bash
python manage.py startapp student
```

编写models.py。

```python
from django.db import models

# Create your models here.
class User(models.Model):
    realname = models.CharField(max_length=255, blank=True, default='')
    username = models.CharField(max_length=255, blank=True, default='')
    password = models.CharField(max_length=255, null=False)
    avatar = models.CharField(max_length=255, blank=True, default='')
    phone = models.CharField(max_length=255, blank=True, default='')
    email = models.CharField(max_length=255, blank=True, default='')
    age = models.IntegerField(default=18)
    intro = models.TextField(blank=True, default='')
    addr = models.CharField(max_length=255, blank=True, default='')
    gender = models.CharField(max_length=10, blank=True, default='M')
    bal = models.DecimalField(decimal_places=2, max_digits=17, default=0.0)

    class Meta:
        db_table = "tb_user"

class Student(models.Model):
    sno = models.CharField(max_length=255, blank=True, default='')
    realname = models.CharField(max_length=255, blank=True, default='')
    major = models.CharField(max_length=255, blank=True, default='')
    sclass = models.CharField(max_length=255, blank=True, default='')
    grade = models.CharField(max_length=255, blank=True, default='')
    age = models.IntegerField(default=18)

    class Meta:
        db_table = "tb_student"
```

利用django提供的命令来自动生成数据库。

```bash
### migrate 命令则运行这些迁移来自动创建数据库表。
python manage.py makemigrations
### 该 makemigrations 命令查找所有可用的模型，为任意一个在数据库中不存在对应数据表的模型创建迁移脚本文件。
python manage.py migrate
```

到此步骤后两个数据表都已经生成。

### 3.2 用户管理部分开发

编写serializers.py

编写views.py

编写urls.py

启动

### 3.3 登录与注册开发

TODO

### 3.4 学生管理开发

TODO