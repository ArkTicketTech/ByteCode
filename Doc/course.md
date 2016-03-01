## 课程模块

- [新增课程](#courses_{userId}_post)
- [删除课程](#courses_{coursesId}_delete)
- [获取课程详情](#courses_detail_{courseId}_get)
- [修改课程详情](#courses_detail_{courseId}_put)
- [获取课程列表](#courses_{courseTypeId}_{courseFounderId}_{coursePlanId}_{keyWord}_{keyWordType}_get)
- [获取选课的成员列表](#courses_usersList_{courseId}_get)
- [获取课程进度](#courses_progress_{courseId}_{userId}_get)
- [保存课程进度](#courses_progress_{courseId}_{userId}_put)


[返回索引页](index.md.html)


- [***Course类***](#class_course)


<a id="courses_{userId}_post"></a>

---

### 新增课程(应该放到admin？)
>POST: /courses/{userId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
planDetails|json|**string**|课程详情
photoUrl|json|**Array** |图片数组(可选)
planName|json|**string** |课程名称(必选)

返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误

返回数据: [***Course类***](#class_course)

[返回顶部](#)


<a id="courses_{courseId}_delete"></a>

---

### 删除课程(应该放到admin？)
>DELETE: /courses/{courseId}

参数

参数|参数类型|数据类型|描述
-|
courseId|query|**id** |课程Id

返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程

返回数据: bool

[返回顶部](#)



<a id="courses_detail_{courseId}_get"></a>

---

### 获取计划详情
>GET: /courses/detail/{courseId}

参数

参数|参数类型|数据类型|描述
-|
courseId|query|**int** |课程Id
courseDetails|json|**string**|课程详情
photoUrl|json|**Array** |图片数组(可选)
courseName|json|**string** |课程名称(必选)


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程
返回数据:  [***Course类***](#class_course)

[返回顶部](#)



<a id="courses_detail_{courseId}_put"></a>

---

### 修改计划详情
>PUT: /courses/detail/{courseId}

参数

参数|参数类型|数据类型|描述
-|
courseId|query|**int** | 课程Id
courseDetails|json|**string**|课程详情
photoUrl|json|**Array** |图片数组(可选)
courseName|json|**string** |课程名称(必选)


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到计划
返回数据:  [***Course类***](#class_course)

[返回顶部](#)


<a id="#courses_{courseTypeId}_{courseFounderId}_{coursePlanId}_{keyWord}_{keyWordType}_get"></a>

---

### 获取课程列表
>GET: /plans/{courseTypeId}/{courseFounderId}/{coursePlanId}/{keyWord}/{keyWordType}

参数

参数|参数类型|数据类型|描述
-|
courseTypeId|query|**int** |课程类型Id
courseFounderId|query|**int** |课程创建者Id
coursePlanId|query|**int** |课程所属计划Id
keyWord|query|**string** |搜索关键字
keyWordTypeId|query|**int** |搜索关键字类型



返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程
返回数据:  Array( [***Course类***](#class_course) )

[返回顶部](#)



<a id="courses_userlist_{courseId}_get"></a>

---

### 获取选课的成员列表
>GET: /courses/userlist/{courseId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
courseId|query|**int** |课程Id

返回码

返回码|描述
-|
200|OK
[401](#index.md.html#401)|未登录
[404](#index.md.html#404)|找不到课程

返回数据:  Array([***User类***](#class_user))

[返回顶部](#)


<a id="user_projects_post"></a>

---

### 添加项目经验
>POST: /user/projects

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
title|json|**string** |职位(可选)
photoUrl|json|**Array** |图片数组(可选)
name|json|**string** |项目名称(必选)
detail|json|**string** |项目详情(可选)
fromtime|json|**long** |起始时间(必选)
totime|json|**long** |结束时间(必选)
返回码

返回码|描述
-|
200|OK
[401](#index.md.html#401)|未登录
[400](#index.md.html#400)|参数错误
返回数据:  [***Project类***](#class_project)

[返回顶部](#)


<a id="projects_{projectId}_get"></a>

---

### 获取项目经验
>GET: /projects/{projectId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
projectId|query|**int** |项目经验Id

返回码

返回码|描述
-|
200|OK
[401](#index.md.html#401)|未登录
[404](#index.md.html#404)|找不到这个项目经验
返回数据:  [***Project类***](#class_project)

[返回顶部](#)


<a id="projects_{projectId}_put"></a>

---

### 修改项目经验
>PUT: /projects/{projectId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
projectId|query|**int** |项目经验Id
title|json|**string** |职位(可选)
photoUrl|json|**Array** |图片数组(可选)
name|json|**string** |项目名称(必选)
detail|json|**string** |项目详情(可选)
fromtime|json|**long** |起始时间(必选)
totime|json|**long** |结束时间(必选)
返回码

返回码|描述
-|
200|OK
[401](#index.md.html#401)|未登录
[403](#index.md.html#403)|没有权限
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到这个项目经验
返回数据:  [***Project类***](#class_project)

[返回顶部](#)


<a id="courses_progress_{userId}_{courseId}_get"></a>

---

### 获取课程进度
>GET: /plans/progress/{userId}/{courseId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
courseId|query|**string**|课程Id



返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程
返回数据:  [***Course类***](#class_course)

[返回顶部](#)
[返回顶部](#)


<a id="class_course"></a>

---

### ***Course类***

字段|类型|描述
-|
id|**int** |id
name|**string** |课程名称
photoUrl|**Array** |图片(数组)
detail|**string** |项目详情
BelongPlan|**Array** |属于的计划
TypeId|**Id** |类型
progress|**json**|进度

[返回顶部](#)
