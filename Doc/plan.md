## 计划模块

- [新增计划](#plans_{courseIds}_{courseDetails}_post)
- [删除计划](#plans_{planId}_delete)
- [获取计划详情](#plans_detail_{planId}_get)
- [修改计划详情](#plans_detail_{planId}_put)
- [获取计划列表](#plans_{planTypeId}_get)
- [获取计划进度](#plans_progress_{userId}_get)


[返回索引页](index.md.html)


- [***Plan类***](#class_plan)



<a id="plans_{courseIds}_{courseDetails}_post"></a>

---

### 新增计划(应该放到admin？)
>POST: /plans

参数

参数|参数类型|数据类型|描述
-|
courseIds|json|**string** |课程Id序列
planDetails|json|**string**|计划详情
photoUrl|json|**Array** |图片数组(可选)
planName|json|**string** |计划名称(必选)

返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误

返回数据: [***Plan类***](#class_plan)

[返回顶部](#)


<a id="plans_{planId}_delete"></a>

---

### 删除计划(应该放到admin？)
>DELETE: /plans/{planId}

参数

参数|参数类型|数据类型|描述
-|
planIds|query|**id** |计划Id

返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到计划

返回数据: [***Plan类***](#class_plan)

[返回顶部](#)



<a id="plans_detail_{planId}_get"></a>

---

### 获取计划详情
>GET: /plans/detail/{planId}

参数

参数|参数类型|数据类型|描述
-|
planId|query|**int** |计划Id
courseIds|json|**string** |课程Id序列
planDetails|json|**string**|计划详情
photoUrl|json|**Array** |图片数组(可选)
planName|json|**string** |计划名称(必选)


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到课程
返回数据:  [***Plan类***](#class_plan)

[返回顶部](#)



<a id="plans_detail_{planId}_put"></a>

---

### 修改计划详情
>PUT: /plans/detail/{planId}

参数

参数|参数类型|数据类型|描述
-|
planId|query|**int** |计划Id
courseIds|json|**string** |课程Id序列
planDetails|json|**string**|计划详情
photoUrl|json|**Array** |图片数组(可选)
planName|json|**string** |计划名称(必选)


返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到计划
返回数据:  [***Plan类***](#class_plan)

[返回顶部](#)

<a id="plans_{planTypeId}_get"></a>

---

### 获取计划列表
>GET: /plans/{planTypeId}

参数

参数|参数类型|数据类型|描述
-|
planTypeId|query|**int** |计划类型Id



返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到计划类型
返回数据:  Array( [***Plan类***](#class_plan) )

[返回顶部](#)


<a id="plans_progress_{userId}_get"></a>

---

### 获取计划进度
>GET: /plans/progress/{userId}

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token



返回码

返回码|描述
-|
200|OK
[400](#index.md.html#400)|参数错误
[404](#index.md.html#404)|找不到计划类型
返回数据:  [***Plan类***](#class_plan)

[返回顶部](#)


<a id="class_project"></a>

---

### ***Plan类***


字段|类型|描述
-|
id|**int** |id
name|**string** |计划名称
photoUrl|**Array** |图片(数组)
detail|**string** |计划详情

[返回顶部](#)
