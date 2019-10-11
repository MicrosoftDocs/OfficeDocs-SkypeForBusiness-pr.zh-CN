---
title: 配置直接路由
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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 了解如何配置 Microsoft Phone 系统直接路由。
ms.openlocfilehash: 38938846c594cbb325193e42111ba8dff528f17f
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434928"
---
# <a name="configure-direct-routing"></a>配置直接路由

> [!Tip]
> 观看以下会话，了解直接路由的好处、如何为其规划以及如何部署它： [Microsoft 团队中的直接路由](https://aka.ms/teams-direct-routing)

如果尚未执行此操作，请阅读 "针对先决条件的[计划直接路由](direct-routing-plan.md)"，并查看配置 Microsoft Phone 系统网络之前需要执行的其他步骤。 

本文介绍如何配置 Microsoft Phone 系统直接路由。 它详细介绍了如何将受支持的会话边界控制器（SBC）配对到直接路由，以及如何将 Microsoft 团队用户配置为使用直接路由连接到公共交换电话网络（PSTN）。 为了完成本文中介绍的步骤，管理员需要熟悉 PowerShell cmdlet。 有关使用 PowerShell 的详细信息，请参阅[设置适用于 Windows powershell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

我们建议你确认你的 SBC 已按照 SBC 供应商的建议进行配置： 

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系统（anynode）部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)

你可以配置 Microsoft Phone 系统并使用户能够使用直接路由，然后通过完成以下过程将 Microsoft 团队设置为首选调用客户端： 

- [将 SBC 与 Microsoft Phone 系统配对并验证配对](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [为用户启用直接路由服务](#enable-users-for-direct-routing-service)
- 确保 Microsoft 团队是用户的首选调用客户端

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>将 SBC 与电话系统的直接路由服务配对 

下面是让你将 SBC 连接或配对到直接路由接口的三个高级步骤： 

- 使用 PowerShell 连接到**Skype For Business Online**管理中心 
- 对 SBC 进行配对 
- 验证配对 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 连接到 Skype for business Online 

你可以使用连接到租户的 PowerShell 会话将 SBC 与直接路由接口配对。 若要打开 PowerShell 会话，请按照[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中概述的步骤进行操作。 
 
建立远程 PowerShell 会话后，请验证你是否可以看到用于管理 SBC 的命令。 若要验证命令，请在 PowerShell 会话中键入或复制/粘贴以下内容，然后按 Enter： 

```
Get-Command *onlinePSTNGateway*
```

你的命令将返回此处所示的4个函数，这些函数将允许你管理 SBC。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>将 SBC 与租户配对 

若要将 SBC 与租户配对，请在 PowerShell 会话中键入以下内容，然后按 Enter： 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. 强烈建议使用 SBC 文档中提供的信息，在 SBC 中设置最大通话限制。 如果 SBC 处于容量级别，则该限制将触发通知。
  > 2. 仅当 FQDN 的域部分与你的租户中注册的一个域（onmicrosoft.com 除外\*）匹配时，你才可以对 SBC 进行配对。 SBC \*FQDN 名称不支持使用 onmicrosoft.com 域名。 例如，如果您有两个域名：<br/><br/>
  > **contoso**<br/>**** onmicrosoft.com<br/><br/>
  > 对于 SBC 名称，你可以使用名称 sbc.contoso.com。 如果你尝试将 SBC 与名称 SBC 对应，则系统将不会允许你，因为域不属于此租户。<br/>
  > 除了在租户中注册的域，还必须有一个具有该域的用户以及分配的 E3 或 E5 许可证。 如果不是，您将收到以下错误：<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
返回
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
在配对过程中，可以设置其他选项。 但是，在前面的示例中，仅显示所需的最低参数。 
 
下表列出了可用于设置参数的其他参数`New-CsOnlinePstnGateway`

|必填？|名称|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|
|是|FQDN|SBC 的 FQDN 名称 |无|NoneFQDN 名称，限制63个字符|字符串、[适用于计算机、域、网站和 ou 的 Active Directory 中的命名约定](https://support.microsoft.com/help/909264)的允许和不允许的字符列表|
|否|MediaBypass |指示 SBC 的参数支持媒体绕过，并且管理员希望使用它。|无|True<br/>False|Boolean|
|是|SipSignallingPort |用于通过使用传输层安全性（TLS）协议与直接路由服务进行通信的侦听端口。|无|任何端口|0到65535 |
|否|FailoverTimeSeconds |设置为10（默认值）时，在10秒内网关未接听的出站呼叫将被路由到下一个可用的中继;如果没有其他中继，则会自动删除呼叫。 在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。 默认值为10。|10|数字|整形|
|否|ForwardCallHistory |指示是否通过中继转移呼叫历史记录信息。 如果启用，则 Office 365 PSTN 代理将发送两个标头：历史记录信息和引用者。 默认值为**False** （$False）。 |False|True<br/>False|Boolean|
|否|ForwardPAI|指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。 PAI 标头提供了一种验证呼叫者身份的方法。 如果启用，则隐私： ID 标头也会发送。 默认值为**False** （$False）。|False|True<br/>False|Boolean|
|否|SendSIPOptions |定义 SBC 是否将发送 SIP 选项。 如果禁用，将从监视和通知系统中排除 SBC。 强烈建议你启用 SIP 选项。 默认值为**True**。 |True|True<br/>False|Boolean|
|否|MaxConcurrentSessions |由警报系统使用。 如果设置了任何值，则当并发会话的数量为 90% 或高于此值时，警报系统将向租户管理员生成警报。 如果未设置参数，则不会生成警报。 但是，监视系统将每隔24小时报告并发会话的数量。 |Null|Null<br/>1到100000 ||
|否|MediaRelayRoutingLocationOverride |允许手动选择媒体的路径。 直接路由根据 SBC 的公共 IP 为媒体路径分配一个数据中心。 我们始终选择最接近于 SBC 数据中心的数据。 但是，在某些情况下，可以将美国范围的公共 IP 分配给位于欧洲的 SBC。 在这种情况下，我们将使用非最佳媒体路径。 此参数允许手动设置媒体流量的首选区域。 仅当通话记录明确指明 "自动分配媒体路径的数据中心" 不会向 SBC 数据中心分配最接近的数据中心时，我们才建议设置此参数。 |无|ISO 格式的国家代码||
|否|已启用|用于为出站呼叫启用此 SBC。 可用于在其更新或维护期间临时删除 SBC。 |False|True<br/>False|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>验证 SBC 配对 

验证连接： 
- 检查 SBC 是否在成对的 SBCs 的列表中。 
- 验证 SIP 选项。 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>验证 SBC 是否位于成对的 SBCs 的列表中 

对 SBC 进行配对后，通过在远程 PowerShell 会话中运行以下命令验证 SBC 是否存在于成对的 SBCs 列表中：`Get-CSOnlinePSTNGateway`

配对网关应显示在列表中，如下面的示例所示，并验证*启用*的参数是否显示值**True**。 键

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
返回：
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>验证 SIP 选项流 

若要使用传出 SIP 选项验证配对，请使用 SBC 管理界面并确认 SBC 是否收到对其传出选项消息的 200 OK 响应。

当直接路由看到传入选项时，它将向 "传入选项" 消息的 "联系人标题" 字段中配置的 SBC FQDN 开始发送传出 SIP 选项消息。 

若要使用传入 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 是否向来自直接路由的选项消息发送回复，并且它发送的响应代码为 200 OK。

## <a name="enable-users-for-direct-routing-service"></a>为用户启用直接路由服务 

准备好为直接路由服务用户启用用户时，请按照下列步骤操作： 

1. 在 Office 365 中创建用户并分配电话系统许可证。 
2. 确保用户托管在 Skype for Business Online 中。 
3. 配置电话号码并启用企业语音和语音邮件。 
4. 配置语音路由。 将自动验证该路线。

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>在 Office 365 中创建用户并分配许可证 

在 Office 365 中创建新用户有两个选项。 但是，我们建议你的组织选择并使用一个选项来避免路由问题： 

- 在本地 Active Directory 中创建用户并将用户同步到云。 请参阅[将本地目录与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Office 365 管理员门户中创建用户。 请参阅[向 Office 365 单独或批量添加用户-管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的 Skype for Business Online 部署与 Skype for business 2015 或 Lync 2010/2013 本地部署并存，则唯一支持的选项是在本地 Active Directory 中创建用户并将用户与云同步（选项1）。 

所需的许可证： 

- Office 365 企业版 E3 （包括 SfB Plan2、Exchange Plan2 和团队） + 电话系统
- Office 365 企业版 E5 （包括 SfB Plan2、Exchange Plan2、团队和手机系统） 

可选许可证： 

- 通话计划 
- 音频会议 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>确保用户托管在 Skype for Business Online 中 

直接路由要求用户驻留在 Skype for Business Online 中。 你可以通过查看 RegistrarPool 参数来检查此情况。 它需要在 infra.lync.com 域中具有值。

1. 连接到远程 PowerShell。
2. 发出命令： 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>配置电话号码并启用企业语音和语音邮件 

创建用户并分配许可证后，下一步是配置其电话号码和语音邮件。 这可通过一个步骤完成。 

要为语音邮件添加电话号码和启用，请执行以下操作：
 
1. 连接到远程 PowerShell 会话。 
2. 输入命令： 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

例如，若要为用户 "Spencer Low" 添加电话号码，请输入以下内容： 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

使用的电话号码必须配置为完整的 E-164 个国家/地区代码的电话号码。 

  > [!NOTE]
  > 如果用户的电话号码是在本地管理的，请使用本地 Skype for Business Management Shell 或控制面板配置用户的电话号码。 

### <a name="configure-voice-routing"></a>配置语音路由 

Microsoft Phone 系统具有一种路由机制，允许根据以下情况将呼叫发送到特定的 SBC： 

- 名为 "号码模式" 
- 称为 "号码模式 +" 的特定用户进行呼叫
 
SBCs 可以指定为 "活动" 和 "备份"。 这意味着当为此号码模式或数字模式 + 特定用户配置为活动的 SBC 不可用时，呼叫将路由到 backup SBC。
 
呼叫路由由以下元素组成： 
- 语音路由策略-PSTN 使用的容器;可以分配给用户或多个用户 
- PSTN 用法–用于语音路由和 PSTN 使用的容器;可以在不同的语音路由策略中共享 
- 语音路由-用于呼叫与模式匹配的呼叫的数字模式和联机 PSTN 网关集 
- 联机 PSTN 网关-指向 SBC 的指针还存储通过 SBC 发出调用时应用的配置，例如，前 P 声明的身份（PAI）或首选编解码器;可以添加到语音路由 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>创建具有一种 PSTN 使用的语音路由策略 

下图显示了呼叫流中的语音路由策略的两个示例。

**呼叫流1（在左侧）：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，则呼叫将被丢弃。 

**呼叫流程2（右侧）：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果两个 SBC 均不可用，将尝试具有较低优先级的路由（sbc3.contoso.biz 和 sbc4.contoso.biz）。 如果没有 SBCs 可用，将丢弃呼叫。 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在这两个示例中，虽然为语音路由分配了优先级，但路由中的 SBCs 按随机顺序尝试。

  > [!NOTE]
  > 除非用户也有 Microsoft 通话计划许可证，否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。 如果用户有呼叫计划许可证，则会根据 Microsoft 通话计划的政策自动路由呼叫。 

Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由，并且不需要其他呼叫路由配置。

在下图所示的示例中，添加了一个语音路由，用于向所有其他美国和加拿大号码（转到 "号码模式 + 1 XXX XXX xx xx" 呼叫）发送呼叫。

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

对于所有其他呼叫，如果用户同时具有两个许可证（Microsoft Phone System 和 Microsoft 通话计划），则使用自动路由。 如果没有与管理员创建的在线语音路线中的数字模式匹配，请通过 Microsoft 通话计划进行路由。

如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。

  > [!NOTE]
  > 在这种情况下，路由 "其他 + 1" 的优先级值不重要，因为只有一个路由与模式 + 1 XXX XXX xx 相匹配。 如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则呼叫将被丢弃。

下表总结了使用三个语音路由的配置。 在此示例中，所有三个路由都属于同一 PSTN 使用 "美国和加拿大"。

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|仅限美国|"雷德蒙 1"|^\\+ 1 （425\|206）（\d{7}） $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx|
|仅限美国|"雷德蒙 2"|^\\+ 1 （425\|206）（\d{7}） $|ppls-2|sbc3.contoso.biz<br/>sbc4.contoso.biz|已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx|
|仅限美国|"其他 + 1"|^\\+ 1 （\d{10}） $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼叫号码 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间）的路由|
|||||||

所有路线均与 PSTN 使用 "美国和加拿大" 相关联，PSTN 使用与 "仅美国" 的语音路由策略相关联。 在此示例中，语音路由策略分配给用户 Spencer Low。

#### <a name="examples-of-call-routes"></a>呼叫路线示例

在以下示例中，我们将演示如何配置路由、PSTN 使用情况和路由策略，并为用户分配策略。

**步骤1：** 创建 PSTN 使用 "美国和加拿大"。

在 Skype for business 远程 PowerShell 会话中，键入：

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

通过输入以下内容验证是否已创建使用： 
```
Get-CSOnlinePSTNUsage
``` 
这将返回可能被截断的名称的列表：
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
在下面的示例中，你可以查看运行 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`的结果以显示完整名称（未截断）。 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**步骤2：** 在 Skype for Business Online 的 PowerShell 会话中，创建三个路线：雷德蒙1、雷德蒙2和其他 + 1，如上表中所述。 

要创建 "Redmond 1" 路线，请输入：

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

返回：
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
若要创建雷德蒙2路线，请输入：

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要创建其他 + 1 路线，请输入：

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 请确保 NumberPattern 属性中的正则表达式是有效的表达式。 你可以使用此网站对其进行测试：[https://www.regexpal.com](https://www.regexpal.com)

在某些情况下，需要将所有调用路由到同一 SBC;请使用-NumberPattern ". *"

- 将所有呼叫路由到同一 SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

通过使用如下所示的选项运行`Get-CSOnlineVoiceRoute` PowerShell 命令验证是否已正确配置路由： 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
应返回：
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

在此示例中，自动为 "其他 + 1" 路由分配优先级4。 

**步骤3：** 创建语音路由策略 "仅美国"，并将 PSTN 使用 "美国和加拿大" 添加到该策略。

在 Skype for Business Online 的 PowerShell 会话中，键入：

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

此示例中显示了结果：

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**步骤4：** 使用 PowerShell 向用户授予 Spencer 低的语音路由策略。

- 在 Skype for Business Online 的 PowerShell 会话中，键入：

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- 通过输入以下命令验证策略分配：

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
返回：
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>创建具有多个 PSTN 用法的语音路由策略

以前创建的语音路由策略仅允许拨打美国和加拿大的电话号码，除非还为用户分配了 Microsoft 通话计划许可证。

在下面的示例中，您可以创建语音路由策略 "无限制"。 该策略重用在上一个示例中创建的 PSTN 使用 "美国和加拿大"，以及新的 PSTN 使用 "国际"。 

这会将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。 显示的示例将 "仅美国" 策略分配给用户 "Spencer Low"，不限制用户 "John"。

Spencer 低–只允许拨打美国和加拿大号码的电话。 当呼叫雷德蒙数字范围时，必须使用一组特定的 SBC。 除非向用户分配了通话计划许可证，否则不会路由非美国号码。

John 的一对电话-允许拨打任何号码的电话。 当呼叫雷德蒙数字范围时，必须使用一组特定的 SBC。 非 US 数字将通过 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

对于所有其他呼叫，如果用户同时具有两个许可证（Microsoft Phone System 和 Microsoft 通话计划），则使用自动路由。 如果没有与管理员创建的在线语音路线中的数字模式匹配，请通过 Microsoft 通话计划进行路由。

如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表总结了路由策略 "无限制" 的用法标识和语音路由。 

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|仅限美国|"雷德蒙 1"|^\\+ 1 （425\|206）（\d{7}） $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx|
|仅限美国|"雷德蒙 2"|^\\+ 1 （425\|206）（\d{7}） $|ppls-2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx|
|仅限美国|"其他 + 1"|^\\+ 1 （\d{10}） $|3|sbc5.contoso.biz<br/>sbc6> contoso.biz|被呼叫方号码的路由 + 1 XXX XXX xx （除 + 1 425 XXX xx 或 + 1 206 XXX xx）|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何数字模式的路由 |


  > [!NOTE]
  > - 语音路由策略中的 PSTN 用法的顺序非常重要。 使用实例按顺序应用，如果在第一次使用中发现匹配项，则从不计算其他用法。 PSTN 使用 "国际" 必须放置在 PSTN 使用 "仅限美国" 之后。 若要更改 PSTN 用法的顺序，请运行`Set-CSOnlineVoiceRoutingPolicy`命令。 <br/>例如，若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序，请执行以下操作：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。 它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比，不是很重要。

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>用户 John 的 "语音路由策略" 的示例

创建 PSTN 使用 "国际"、语音路由 "国际"、"语音路由策略" 无限制，然后将其分配给用户 "John （John）" 的步骤如下所示。


1. 首先，创建 PSTN 使用 "国际"。 在 Skype for Business Online 中的远程 PowerShell 会话中，输入：

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. 接下来，创建新的语音路线 "国际"。

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   返回：

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. 接下来，创建语音路由策略 "无限制"。 PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   返回的

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. 使用以下命令将语音路由策略分配给用户 "John 的工作"。

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   然后使用以下命令验证作业： 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   返回：

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

结果是，应用到 John 54777 的语音政策不受限制，并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>向用户分配 "仅团队" 模式以确保在 Microsoft 团队中拨打土地

直接路由要求用户仅在 "仅工作组" 模式下，以确保传入呼叫位于团队客户的土地。 若要将用户置于 "仅团队" 模式，请为他们分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例。 如果你的组织使用 Skype for business 服务器或 Skype for business Online，请参阅以下文章了解 Skype 和团队之间的信息互操作性：[与 skype 配合使用团队的组织的迁移和互操作性指南适用于企业](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>配置将呼叫直接发送到语音邮件

直接路由允许您结束呼叫用户并将其直接发送到用户的语音邮件。 如果您想要将呼叫直接发送到语音邮件，请将不透明 = app：语音邮件附加到请求 URI 标题。 例如，"sip： user@yourdomain.com; 不透明 = 应用：语音邮件"。
在这种情况下，团队用户将不会收到呼叫通知，直接将呼叫连接到用户的语音邮件。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)
