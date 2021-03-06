# describeIpv6Gateway


## 描述
查询IPv6网关实例详情

## 请求方式
GET

## 请求地址
https://cps.jdcloud-api.com/v1/regions/{regionId}/ipv6Gateways/{ipv6GatewayId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域ID，可调用接口（describeRegions）获取云物理服务器支持的地域|
|**ipv6GatewayId**|String|True| |IPv6网关ID|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describeipv6gateway#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**ipv6Gateway**|[Ipv6Gateway](describeipv6gateway#ipv6gateway)|IPv6网关实例详细信息|
### <div id="ipv6gateway">Ipv6Gateway</div>
|名称|类型|描述|
|---|---|---|
|**region**|String|地域，如cn-north-1|
|**ipv6GatewayId**|String|IPv6网关实例ID|
|**ipv6GatewayName**|String|IPv6网关名称|
|**vpcId**|String|私有网络ID|
|**vpcName**|String|私有网络名称|
|**createTime**|String|创建时间|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Bad request|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|
