# 邀请模块 

[1.将邀请为好友的记录批量添加至数据库](#1)

---
##<a id="1">1.将邀请为好友的记录批量添加至数据库</a>

### URL
/invite/batch_add.json

### 请求方式
POST

### Header
Content-Type : application/json

### 请求参数
     参数      | 必选 	    | 类型及范围     |说明
-------------  | ---------- | -------------  |---------- 
uid            | true	    | long          | 用户id
invites        | true	    | array (size < 1000)        | 邀请记录列表 

### 请求Json示例
	{ 
	  "uid" : 234523,
	  "invites" : [{
	    "invited_id" : 1222 //long类型
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
