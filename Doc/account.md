## 账户模块

/account
- [注册](#account_signup_post)
- [登陆](#account_signin_post)
- [token登陆](#account_get)
- [修改密码](#account_password_put)
- [完善手机信息](#account_mobile_put)
- [手机验证重置密码](#account_reset_password_post)
- [激活帐号](#account_state_{token}_put)

- [发送验证邮件](#account_send_email_post)
- [发送手机验证](#account_send_verify_post)


类:
- [***Account类***](#class_account)

[返回索引页](index.md.html)

<a id="account_signup_post"></a>

---
### 注册
>POST: /account/signup

参数

参数|描述
-|
username|登录用户名(不可重复)
password|密码
email|电子邮箱(可选，不可重复)
mobile|手机号(可选，不可重复)

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](index.md.html#400)|手机/密码/邮箱 格式错误
[409](index.md.html#409)|重复的手机号或邮箱或登录用户名

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_signin_post"></a>

---

### 账户密码登录
>POST: /account/signin

参数

参数|描述
-|
username|登录账户，可以是登录用户名，手机号，邮箱
password|密码

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](index.md.html#400)|登录账户/密码 漏填
[403](index.md.html#403)|登录过快，限制登录
[404](index.md.html#404)|登录账户/密码 错误

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_get"></a>

---

### token登录
>GET: /account

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token  

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](#index.md.html#400)|参数错误
[401](#index.md.html#401)|未登录

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_token_get"></a>

---

### 刷新token
>GET: /account/token

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token  

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[401](#index.md.html#401)|未登录

返回数据: 新的token

[返回顶部](#)

<a id="account_password_put"></a>

---

## 修改密码
>PUT: /account/password

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token  
oldPassword|form|**string** |原密码
newPassword|form|**string** |新密码

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](index.md.html#400)|参数格式错误
[401](index.md.html#401)|未登录
[404](index.md.html#404)|错误的密码

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_send_email_post"></a>

---

## 发送验证邮件
>POST: /account/send_email

参数

参数|参数类型|数据类型|描述
-|
email|formData|**string** |电子邮箱

返回状态码

状态码|描述
-|
[200](index.md.html#200)|OK
[403](index.md.html#403)|发送过快

[返回顶部](#)

<a id="account_state_{token}_put"></a>

---

## 激活账号
>PUT: /account/state/{token}

参数

参数|参数类型|数据类型|描述
-|
token|query|**string** |激活账号用token，验证后立即刷新

返回状态码

状态码|描述
-|
[200](index.md.html#200)|OK
[404](index.md.html#404)|验证码过期

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_mobile_put"></a>

---

## 完善手机信息
>PUT: /account/mobile

参数

参数|参数类型|数据类型|描述
-|
token|header|**string** |用户的token
mobile|query|**string** |手机号
verify|query|**string** |验证码

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](index.md.html#400)|手机 错误
[404](index.md.html#404)|错误的验证码

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_reset_password_post"></a>

---

## 手机验证重置密码
>POST: /account/reset_password

参数

参数|描述
-|
mobile|手机号
password|密码
verify|验证码

返回码

返回码|描述
-|
[200](index.md.html#200)|OK
[400](index.md.html#400)|手机/密码 错误
[404](index.md.html#404)|错误的验证码

返回数据: [***Account类***](#class_account)

[返回顶部](#)

<a id="account_send_verify_post"></a>

---

## 发送手机验证
>POST: /account/send_verify

参数

参数|参数类型|数据类型|描述
-|
mobile|formData|**string** |手机号

返回状态码

状态码|描述
-|
[200](index.md.html#200)|OK
[403](index.md.html#404)|发送过快

[返回顶部](#)

<a id="class_account"></a>

---

## ***Account类***
字段|类型|描述
-|
user|[***User类***](user.md.html#class_user)|
username|**string** |登录用户名
password|**string** |密码
mobile|**string** |手机号
email|**string** |电子邮箱
state|**int** |用户状态，0表示未激活，1表示激活
token|**string** |验证用的token
expire|**long** |剩余多久过期

[返回顶部](#)
