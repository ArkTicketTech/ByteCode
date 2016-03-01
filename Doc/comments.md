## 评论模块

- [新增课程评论](#comments_{coursesId}_{userId}_post)
- [删除课程评论](#comments_{coursesId}_{userId}_delete)
- [获取课程评论详情](#comments_{commentId}_get)
- [修改课程评论详情](#comments_{coursesId}_put)
- [获取课程评论列表](#comments_{coursesId}_get)

[返回索引页](index.md.html)


- [***Comment类***](#class_comment)


<a id="comments_{coursesId}_{userId}_post"></a>

---

### 新增评论
>POST: /comments/{courseId}/{userId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
courseId|query|**id**|课程Id


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误

返回数据: [***Comment类***](#class_comment)

[返回顶部](#)


<a id="comments_{coursesId}_{userId}_delete"></a>

---

### 删除评论
>DELETE: /comments/{courseId}/{userId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
courseId|query|**id** |课程Id

返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程

返回数据: bool

[返回顶部](#)



<a id="comments_{commentId}_get"></a>

---

### 获取评论详情
>GET: /comments/detail/{commentId}

参数

参数|参数类型|数据类型|描述
-|
commentId|query|**int** |评论Id


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到评论
返回数据:  [***Comment类***](#class_comment)

[返回顶部](#)


<a id="comments_{commentId}_get"></a>

---

### 修改评论详情
>PUT: /comments/detail/{commentId}

参数

参数|参数类型|数据类型|描述
-|
commentId|query|**int** |评论Id
content|query|**string**|内容
likeNum|query|**int**|点赞


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到评论
返回数据:  [***Comment类***](#class_comment)

[返回顶部](#)


<a id="comments_{coursesId}_get"></a>

---

### 获取评论列表
>GET: /comments/{courseId}

参数

参数|参数类型|数据类型|描述
-|
courseId|query|**int** |课程Id



返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程
返回数据:  Array( [***Course类***](#class_course) )

[返回顶部](#)





<a id="class_comment"></a>

---

### ***Comment类***

字段|类型|描述
-|
id|**int** |id
detail|**json** |评论详情（发起者，内容，点赞，从属，浏览等）
time|**long** |发布时间

[返回顶部](#)
