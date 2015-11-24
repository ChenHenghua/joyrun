# 朋友模块 

[1.批量添加好友](#1)

---
##<a id="1">1.批量添加好友</a>

### URL
/friend/batch_add.json

### 请求方式
POST

### Header
Content-Type : application/json

### 请求参数
     参数      | 必选 	    | 类型及范围     |说明
-------------  | ---------- | -------------  |---------- 
uid            | true	      | long         | 用户id
friends        | true	      | array         | 朋友列表 

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
