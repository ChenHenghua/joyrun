# 朋友模块 

[1.将好友批量添加至数据库](#1)

[2.检测是否有同类账户添加该用户](#2)

[3.检测好友是否能添加](#3)

---
##<a id="1">1.将好友批量添加至数据库</a>

### URL
/friend/batch_add.json

### 请求方式
POST

### Header
Content-Type : application/json

### 请求参数
     参数      | 必选 	    | 类型及范围     |说明
-------------  | ---------- | -------------  |---------- 
uid            | true	    | long          | 用户id
friends        | true	    | array (size < 1000)        | 朋友列表 

### 请求Json示例
	{ 
	  "uid" : 234523,
	  "friends" : [{
	    "id" : 1222, //long类型
      	    "gender" : "1", // 1男 2女  
            "remark" : "张三",
      	    "nick": "爱跑人大卫"
	  }]
	}

### 返回Json示例
#### 请求成功
	{
		"success":"true"
	}

#### 请求失败
	{
		"error_code":"10000",
		"error_message":"XXXXX"
	}

---
##<a id="2">2.检测是否有同类账户添加该用户</a>

### URL
/friend/added_by_same_type_acc.json

### 请求方式
POST

### Header
Content-Type : application/json

### 请求参数
     参数      | 必选 	    | 类型及范围     |说明
-------------  | ---------- | -------------  |---------- 
uid            | true	    | long           | 用户id
fid            | true	    | long           | 要添加的uid

### 请求Json示例
	{ 
	  "uid" : 234523,
	  "fid" : 232321
	}

### 返回Json示例
#### 请求成功
	{
		"success":"true",
		"data" :{
		   "isAddedBySameAcc" : true
		}
	}

#### 请求失败
	{
		"error_code":"10000",
		"error_message":"XXXXX"
	}

---
##<a id="3">3.检测好友是否能添加</a>

### URL
/friend/isAddable.json

### 请求方式
POST

### Header
Content-Type : application/json

### 请求参数
     参数      | 必选 	    | 类型及范围     |说明
-------------  | ---------- | -------------  |---------- 
uid            | true	    | long           | 用户id
fid            | true	    | long           | 要添加的uid

### 请求Json示例
	{ 
	  "uid" : 234523,
	  "fid" : 232321
	}

### 返回Json示例
#### 请求成功
	{
		"success":"true",
		"data" :{
		   "isAddable" : false,
		   "reason" : "已经有同类好友添加该用户"
		}
	}

#### 请求失败
	{
		"error_code":"10000",
		"error_message":"XXXXX"
	}
