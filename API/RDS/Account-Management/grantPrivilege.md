# grantPrivilege


## 描述
授予账号的数据库访问权限，即该账号对数据库拥有什么权限。一个账号可以对多个数据库具有访问权限。<br>为便于管理，RDS对权限进行了归类，目前提供以下两种权限<br>- ro：只读权限，用户只能读取数据库中的数据，不能进行创建、插入、删除、更改等操作。<br>- rw：读写权限，用户可以对数据库进行增删改查等操作

## 请求方式
POST

## 请求地址
https://rds.jdcloud-api.com/v1/regions/{regionId}/instances/{instanceId}/accounts/{accountName}:grantPrivilege

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域代码，取值范围参见[《各地域及可用区对照表》](../Enum-Definitions/Regions-AZ.md)|
|**instanceId**|String|True| |RDS 实例ID，唯一标识一个RDS实例|
|**accountName**|String|True| |账号名，在同一个实例中账号名不能重复|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**accountPrivileges**|[AccountPrivilege[]](grantprivilege#accountprivilege)|True| |账号的访问权限|

### <div id="accountprivilege">AccountPrivilege</div>
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**dbName**|String|False| |数据库名称，具体规则可参见帮助中心文档:[名称及密码限制](../../../documentation/Database-and-Cache-Service/RDS/Introduction/Restrictions/SQLServer-Restrictions.md)|
|**privilege**|String|False| |账号对数据库所具有的权限，权限的具体定义可以参见[枚举参数定义](../Enum-Definitions/Enum-Definitions.md)|

## 返回参数
无


## 返回码
|返回码|描述|
|---|---|
|**200**|OK|

## 请求示例
POST
```
public void testGrantPrivilege() {
    GrantPrivilegeRequest grantPrivilegeRequest = new GrantPrivilegeRequest();
    grantPrivilegeRequest.setAccountName("dj_ac");
    grantPrivilegeRequest.setInstanceId("mysql-wp4e9ztap2");
    grantPrivilegeRequest.setRegionId("cn-north-1");
    AccountPrivilege accountPrivilege1 = new AccountPrivilege();
    accountPrivilege1.setDbName("dj_db");
    accountPrivilege1.setPrivilege("rw");
    List<AccountPrivilege> aps = new ArrayList<AccountPrivilege>();
    aps.add(accountPrivilege1);
    grantPrivilegeRequest.setAccountPrivileges(aps);
    GrantPrivilegeResponse grantPrivilegeResponse = rdsClient.grantPrivilege(grantPrivilegeRequest);
    System.out.println(new Gson().toJson(grantPrivilegeResponse));
}

```

## 返回示例
```
{
    "requestId": "bpa08gdtob57p1ok65p1wpn86k9r7i1w"
}
```
