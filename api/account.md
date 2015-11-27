# 账户模块 

[1.通过uid获取账号信息](#1)

---
##<a id="1">1.通过uid获取账号信息</a>

### URL
/account/get_by_uid.json.json

### 请求方式
POST

### Header
Content-Type : application/json

### 请求参数
     参数      | 必选 	    | 类型及范围     |说明
-------------  | ---------- | -------------  |---------- 
uid            | true	    | long          | 用户id

### 请求Json示例
	{ 
	  "uid" : 234523,
	}

### 返回Json示例
#### 请求成功
	{
		"success":"true",
		"data" : {
		  "uid" : 234523,
		  "type" : "1",
		  "type_txt" : "跑步大使"
		}
	}

#### 请求失败
	{
		"error_code":"10000",
		"error_message":"XXXXX"
	}
