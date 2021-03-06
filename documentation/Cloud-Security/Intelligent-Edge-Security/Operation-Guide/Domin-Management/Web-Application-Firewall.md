# 应用层防护

## **黑白名单配置**

在应用层防护中，您可以配置精准访问控制规则来阻断或放行指定IP、URL、地域的访问请求，即设置IP黑/白名单，IP黑白名单仅针对配置的特定域名生效。

**操作步骤**

参照以下步骤，配置黑名单和白名单：

1. 登录京东云智能边缘安全控制台。
2. 前往**域名管理**页面。
3. 选择要操作的域名，单击其操作列下的**应用层防护**。
4. 开启WAF防护总开关防护。

![WAF总开关](/image/Intelligent-Edge-Security/WAF总开关.png)
5. 开启白名单或者黑名单开关，单击**设置规则**，新增一条防护规则。
6. IP白名单配置示例：使用下图配置，放行源IP为1.1.1.1的所有访问。

![IP白名单](/image/Intelligent-Edge-Security/IP白名单.png)

**说明：** 如果想完全放行这个IP的所有请求，则不要勾选**匹配动作**下方的继续执行其它防护选项。如果勾选，则来自此IP的请求会继续通过相应的规则校验。

7. IP黑名单配置示例：使用下图配置，阻断源IP为1.1.1.1的所有访问。

![IP黑名单](/image/Intelligent-Edge-Security/IP黑名单.png)

**注意事项**

- 开启WAF防护总开关防护，再开启功能开关，功能开关包括白名单、黑名单、CC防护规则、WEB应用防护攻击，同时配置相应规则，应用层防护功能才生效。
- 多条防护规则之间存在匹配优先级，按照规则列表中从上到下的顺序进行匹配。

## **CC防护规则**

您可以在控制台自定义防护规则，限制单个IP对您的网站上特定路径（URI）的访问频率。例如，您可以配置如下规则：当单个源IP在60秒内访问www.yourdomain.com/login.html超过100次时，封禁该IP10分钟。
5. 单击**新增规则**，添加一条规则。参数描述如下：

| 配置           | 说明                                                         |
| -------------- | ------------------------------------------------------------ |
| 规则名称       | 为该规则命名。                                               |
| URI            | 指定需要防护的具体地址，如/register。支持在地址中包含参数，如/user?action=login。 |
| 匹配规则       | 完全匹配：即精确匹配，请求地址必须与配置的URI完全一样才会被拦截。 |
| 检测时长       | 指定统计访问次数的周期。需要和单一IP访问次数配合。           |
| 单一IP访问次数 | 指定在检测时长内，允许单个源IP访问被防护地址的次数。         |
| 阻断类型       | 指定触发条件后的操作（封禁、人机识别），以及请求被阻断后阻断动作的时长。                                                                   封禁：触发条件后，直接断开连接。                                                                                                              人机交互：触发条件后，用重定向的方式去访问客户端（WAF返回302状态)，通过验证后才放行。例如，单个IP在20s内访问超过5次则进行人机识别判断，在10分钟内该IP的访问请求都需要通过人机识别，如果被识别为非法将会被WAF拦截，只有被识别为合法才会放行。 |
| 持续时间       | 指定后续阻断该IP的时长。                                     |

**示例：**

![自定义CC防护规则](/image/Intelligent-Edge-Security/自定义CC防护规则.png)

**说明：**以图中的配置为例，其含义为：单个IP访问目标地址（完全匹配）时，一旦在60秒内访问超过100次，就直接阻断该IP的访问，阻断操作持续10分钟。 由于WAF需要将集群中的多台服务器的数据进行汇总来统计单一IP的访问频率，统计过程中可能存在一定延时，因此封禁的实际生效时间可能稍有滞后。

**执行结果**

规则添加成功后即时生效，您可以选择**编辑**或者**删除**规则。

![编辑或删除自定义CC规则](/image/Intelligent-Edge-Security/编辑或删除自定义CC规则.png)

## **Web应用攻击防护**

Web应用攻击防护可防护SQL注入、XSS跨站等常见Web应用攻击，且提供不同等级的防护策略：正常、宽松、严格。

1. 在**Web应用攻击防护**下，开启防护，并选择防护**模式**： **说明：**使用过程中出现流量异常，可在通过拨动按钮关闭防护。

![web应用防护攻击](/image/Intelligent-Edge-Security/web应用防护攻击.png)

2. - **拦截模式**：发现攻击后对攻击请求进行拦截。
   - **检测模式**：发现攻击后仅发送告警信息，不会对请求进行拦截。

3. 在**防护规则策略等级**下选择合适的防护策略：

4. - 默认使用**正常**模式规则。
   - 当发现存在较多误拦截，或者业务存在较多不可控的用户输入，选择**宽松**模式。
   - 当您需要更严格地防护路径穿越、SQL注入、命令执行时，建议您选择**严格**模式。