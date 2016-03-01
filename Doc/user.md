## 用户模块

/user
- [查看用户信息](#user_{userId}_get)
- [更新完善用户信息](#user_{userId}_put)



类:
- [***User***](#class_user)

[返回索引页](index.md.html)

<a id="user_{userId}_get"></a>

---
### 查看用户信息
>GET: /user/{userId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token  
userId|query|**int** |用户id

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[401](index.md.html#401)|未登录

返回数据: [***User类***](#class_user)

[返回顶部](#)

<a id="user_{userId}_put"></a>

---
### 更新完善用户信息
>PUT: /user/{userId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token  
userId|query|**int** |用户id
nickname|query|**string** |昵称
sex|query|**int** |性别，0表示女性，1表示男性，2表示其他
headUrl|query|**string** |头像链接
city|query|**string** |所在市
position|query|**string** |职业
description|query|**string** |个人简介

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](index.md.html#401)|参数错误
[401](index.md.html#401)|未登录

返回数据: [***User类***](#class_user)

[返回顶部](#)

<a id="class_user"></a>

---

## ***User类***
字段|类型|描述
-|
nickname|**string** |昵称
sex|**int** |性别，0表示女性，1表示男性，2表示其他
headUrl|**string** |头像链接
city|**string** |所在市
position|**string** |职业
skills|array([***Skill类***](skill.md.html#class_skill)) |擅长的领域
description|**string** |个人简介
courses|array([***Course类***](course.md.html#class_course)) |参与课程
friends|array([***User类***](user.md.html#class_user)) |好友
[返回顶部](#)
