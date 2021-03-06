# clusterExpansion


## 描述
扩容集群

## 请求方式
POST

## 请求地址
https://jmr.jdcloud-api.com/v1/regions/{regionId}/cluster:expansion

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域ID|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clusterExpansion**|[ClusterExpansion](clusterexpansion#clusterexpansion)|True| |描述集群扩容信息|
|**clientToken**|String|False| |用于保证请求的幂等性。由客户端生成，长度不能超过64个字符。<br>|

### <div id="clusterexpansion">ClusterExpansion</div>
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clusterId**|String|True| |集群ID|
|**expansionNum**|String|True| |扩容节点个数|
|**nodeType**|String|False| |扩容节点类型。 Task：计算节点，Core：存储和计算节点|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](clusterexpansion#result)| |
|**requestId**|String| |

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**status**|Boolean|是否开始扩容集群|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
