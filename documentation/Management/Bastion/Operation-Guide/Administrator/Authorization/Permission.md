# 权限管理

权限管理中将规则、用户与主机资产联系在一起，以达到控制某个用户只能访问他权限内的目标主机。

权限管理的授权场景包括：

- 对主机/主机组添加运维规则
- 给用户/用户组授权主机/主机组运维权限
- 给主机/主机组添加资源账号等


**新建授权**

以对主机/主机组添加运维规则 为例

操作步骤

1、 进入权限 > 授权管理页，选择 新建授权

 ![](/image/Bastion/hostRule.png) 

  在新建授权页面，填写授权名称，选择关联的单个或多个主机/主机组，选择关联规则，点击确定完成授权操作。
  
  您可以在 权限 > 规则管理页查看所有运维规则。
  
2、授权成功之后，选择的规则会对目标主机生效。



给用户/用户组授权主机/主机组运维权限 为例 
  
操作步骤

1、 进入权限 > 授权管理页，选择 新建授权

 ![](/image/Bastion/userRole.png) 

  在新建授权页面，填写授权名称，选择关联的单个或多个主机/主机组，选择单个或多个用户/用户组，选择资产账户，点击确定完成授权操作。

2、授权成功之后，系统会自动将资源账号推送到目标主机，并给所选用户完成主机授权


**停用权限**

权限被停用之后相关规则将失效，直到管理员重新设置为启用。

操作步骤

1、 进入权限 > 权限管理页

2、 在权限管理列表中，单击 停用


**启用权限**

操作步骤

1、 进入权限 > 权限管理页

2、 在权限管理列表中，单击 启用


**编辑权限**

操作步骤

1、 进入权限 > 权限管理页

2、 在权限管理列表中，单击 编辑，重新编辑权限

