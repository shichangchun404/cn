# deleteMask


## 描述
删除敏感信息遮蔽规则

## 请求方式
DELETE

## 请求地址
https://dbaudit.jdcloud-api.com/v1/regions/{regionId}/instances/{insId}/databases/{dbId}/maskRules/{maskRuleId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域 Id|
|**insId**|String|True| |审计实例ID|
|**maskRuleId**|String|True| |敏感信息遮蔽规则ID|
|**dbId**|String|True| |数据库ID|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String| |


## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
