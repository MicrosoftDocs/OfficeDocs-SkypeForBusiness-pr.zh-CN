---
title: 将会话边界控制器（SBC）连接到直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft Phone 系统直接路由。
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157932"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>将会话边界控制器（SBC）连接到直接路由 

本文介绍如何将会话边界控制器（SBC）连接到手机系统直接路由。  这是配置直接路由的以下步骤的步骤1：

- **步骤1。将 SBC 与电话系统连接并验证连接**（本文）
- 第 2 步 [为用户启用直接路由](direct-routing-enable-users.md)
- 第 3 步 [配置呼叫路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 

有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。

要将 SBC 连接到直接路由，您需要： 

1. 使用 PowerShell 连接到**Skype For Business Online**管理中心。            
2. 将 SBC 连接到租户。
3. 验证连接。 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 连接到 Skype for business Online 

你可以使用连接到租户的 PowerShell 会话将 SBC 与直接路由接口配对。 若要打开 PowerShell 会话，请按照[为 Windows PowerShell 设置计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中概述的步骤进行操作。 
 
建立远程 PowerShell 会话后，请验证你是否可以查看用于管理 SBC 的命令。 若要验证命令，请在 PowerShell 会话中键入或复制并粘贴以下命令，然后按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

该命令返回此处显示的四个函数，可让你管理 SBC。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a>将 SBC 连接到租户 

若要将 SBC 连接到租户，请在 PowerShell 会话中键入以下内容，然后按 Enter： 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Microsoft 建议使用 SBC 文档中可以找到的信息，在 SBC 中设置最大通话限制。 如果 SBC 处于容量级别，则该限制将触发通知。
  > 2. 仅当 FQDN 的域部分与你的租户中注册的一个域（onmicrosoft.com 除外\*）匹配时，你才可以对 SBC 进行配对。 SBC \*FQDN 名称不支持使用 onmicrosoft.com 域名。 例如，如果您有两个域名：<br/><br/>
  > **contoso**<br/>**** onmicrosoft.com<br/><br/>
  > 对于 SBC 名称，你可以使用名称 sbc.contoso.com。 如果你尝试将 SBC 与名称 SBC 对应，则系统将不会允许你，因为域不属于此租户。<br/>
  > 除了在租户中注册的域，还必须有一个具有该域的用户以及分配的 E3 或 E5 许可证。 如果不是，您将收到以下错误：<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
返回
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
在连接过程中，可以设置其他选项。 但是，在前面的示例中，仅显示所需的最低参数。 
 
下表列出了可在为```New-CsOnlinePstnGateway```设置参数时使用的其他参数。

|必填？|名称|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|
|是|FQDN|SBC 的 FQDN 名称 |无|NoneFQDN 名称，限制63个字符|字符串、[适用于计算机、域、网站和 ou 的 Active Directory 中的命名约定](https://support.microsoft.com/help/909264)的允许和不允许的字符列表|
|否|MediaBypass |指示 SBC 的参数支持媒体绕过，并且管理员希望使用它。|无|True<br/>False|Boolean|
|是|SipSignalingPort |用于通过使用传输层安全性（TLS）协议与直接路由服务进行通信的侦听端口。|无|任何端口|0到65535 |
|否|FailoverTimeSeconds |设置为10（默认值）时，在10秒内网关未接听的出站呼叫将被路由到下一个可用的中继;如果没有其他中继，则会自动删除呼叫。 在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。 默认值为10。|10|数字|整形|
|否|ForwardCallHistory |指示是否通过中继转移呼叫历史记录信息。 如果启用，则 Office 365 PSTN 代理将发送两个标头：历史记录信息和引用者。 默认值为**False** （$False）。 |False|True<br/>False|Boolean|
|否|ForwardPAI|指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。 PAI 标头提供了一种验证呼叫者身份的方法。 如果启用，则隐私： ID 标头也会发送。 默认值为**False** （$False）。|False|True<br/>False|Boolean|
|否|SendSIPOptions |定义 SBC 是否将发送 SIP 选项。 如果禁用，将从监视和通知系统中排除 SBC。 强烈建议你启用 SIP 选项。 默认值为**True**。 |True|True<br/>False|Boolean|
|否|MaxConcurrentSessions |由警报系统使用。 如果设置了任何值，则当并发会话的数量为90% 或高于此值时，警报系统将向租户管理员生成警报。 如果未设置该参数，则不会生成警报。 但是，监视系统将每隔24小时报告并发会话的数量。 |Null|Null<br/>1到100000 ||
|否|MediaRelayRoutingLocationOverride |允许手动选择媒体的路径。 直接路由根据 SBC 的公共 IP 为媒体路径分配一个数据中心。 我们始终选择最接近于 SBC 数据中心的数据。 但是，在某些情况下，可以将美国范围内的公共 IP 分配给位于欧洲的 SBC。 在这种情况下，我们将使用非最佳媒体路径。 此参数允许手动设置媒体流量的首选区域。 Microsoft 仅建议设置此参数（如果通话记录清晰地指明自动分配媒体路径的数据中心）不会向 SBC 数据中心分配最接近的数据中心。 |无|ISO 格式的国家代码||
|否|已启用|用于为出站呼叫启用此 SBC。 可用于在其更新或维护期间临时删除 SBC。 |False|True<br/>False|Boolean|
 
## <a name="verify-the-sbc-connection"></a>验证 SBC 连接 

若要验证连接，请执行以下操作： 
- 检查 SBC 是否在成对的 SBCs 的列表中。 
- 验证 SIP 选项。 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>检查 SBC 是否位于成对的 SBCs 的列表中 

连接 SBC 后，通过在远程 PowerShell 会话中运行以下命令验证 SBC 是否存在于成对的 SBCs 列表中： 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

配对网关应显示在列表中，如下面的示例所示，并且**Enabled**参数应显示值**True**。 


返回：
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a>验证 SIP 选项流 

若要使用传出 SIP 选项验证配对，请使用 SBC 管理界面并确认 SBC 是否收到对其传出选项消息的 200 OK 响应。

当直接路由看到传入选项时，它将向 "传入选项" 消息的 "联系人标题" 字段中配置的 SBC FQDN 开始发送传出 SIP 选项消息。 

若要使用传入 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 是否向来自直接路由的选项消息发送回复，并且它发送的响应代码为 200 OK。


## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
