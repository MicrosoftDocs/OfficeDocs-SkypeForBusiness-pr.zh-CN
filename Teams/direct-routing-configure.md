---
title: 配置直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: 了解如何配置 Microsoft 电话系统直接路由。
ms.openlocfilehash: a26972e16758a00e2afc5d39029cfb1504b974c4
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517260"
---
# <a name="configure-direct-routing"></a>配置直接路由

> [!Tip]
> 观看下面的会话了解好处直接路由、 如何规划，以及如何将其部署：[直接路由中的 Microsoft 团队](https://aka.ms/teams-direct-routing)

如果您未阅读[规划直接路由](direct-routing-plan.md)必备组件并查看其他步骤您需要配置 Microsoft 电话系统网络之前执行。 

本文介绍如何配置 Microsoft 电话系统直接路由。 它详细说明如何配对对直接路由支持会话边界控制器 (SBC) 以及如何配置为使用直接路由连接到公共公用电话交换网 (PSTN) 的 Microsoft 团队用户。 若要完成本文中介绍的步骤操作，管理员需要某些熟悉 PowerShell cmdlet。 有关使用 PowerShell 的详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

我们建议您确认，您的 SBC 已配置为与 SBC 供应商的推荐： 

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Communications 部署文档的功能区](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

您可以配置 Microsoft 电话系统，并使用户能够使用直接路由，然后通过完成以下过程中设置为首选调用客户端的 Microsoft 团队： 

- [配对与 Microsoft 电话系统 SBC 和验证配对](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [为用户启用直接路由服务](#enable-users-for-direct-routing-service)
- [确保 Microsoft 团队是用户的首选呼叫客户端](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>配对到电话系统的直接路由服务 SBC 

让您连接，或配对，直接路由界面 SBC 的三个高级步骤如下： 

- 连接到使用 PowerShell **Skype 业务 online**管理中心 
- 对 SBC 
- 验证配对 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell online 业务连接到 Skype 

您可以使用连接到租户 PowerShell 会话配对直接路由界面 SBC。 若要打开 PowerShell 会话，请按照中[设置您的计算机的 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)列出的步骤。 
 
您建立一个远程 PowerShell 会话后，请验证您可以看到这些命令以管理 SBC。 若要验证命令，键入或复制/粘贴在下面的示例 PowerShell 会话中，按 Enter: 

```
Get-Command *onlinePSTNGateway*
```

您的命令将返回如下所示，将允许您管理 SBC 的四个功能。 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>对到租户 SBC 

若要对到租户 SBC，PowerShell 会话中键入以下命令，并按 Enter: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. 我们强烈建议在 SBC 中, 设置的最大呼叫限制使用可以找到 SBC 文档中的信息。 如果 SBC 处于容量级别限制将触发通知。
  > 2. 如果 FQDN 的域部分与某个除在您的租户中注册的域匹配，可以仅配对 SBC \*。 onmicrosoft.com。 使用\*。 onmicrosoft.com 域名称不支持的 SBC FQDN 名称。 例如，如果您有两个域名：<br/><br/>
  > **contoso**.com<br/>**contoso**。 onmicrosoft.com<br/><br/>
  > SBC 名称，您可以使用名称 sbc.contoso.com。 如果您尝试配对名称 sbc.contoso.abc 与 SBC，系统将不允许您，如此租户不属于域。

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
返回：
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
还有其他选项可在配对的过程中设置。 在上面的示例中，但是，仅的最低要求参数所示。 
 
下表列出了您可以设置参数中使用的其他参数`New-CsOnlinePstnGateway`

|必填？|名称|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|
|是|FQDN|SBC 的 FQDN 名称 |无|NoneFQDN 名称，限制 63 个字符|字符串，在[Active Directory 中的计算机、 域、 站点和 Ou 中的命名约定](https://support.microsoft.com/help/909264)的允许和禁止字符的列表|
|否|MediaBypass |参数留作将来使用。 参数指示的 SBC 支持媒体绕过功能，管理员希望使用它。|无|True<br/>False|Boolean|
|是|SipSignallingPort |用于与直接路由服务通信使用的传输层安全性 (TLS) 协议的侦听端口。|无|任何端口|0 到 65535 |
|否|FailoverTimeSeconds |如果设置为 10 （默认值），在 10 秒内未应答，网关的出站呼叫路由至下一个可用中继;如果不有任何其他的中继，则自动丢弃该呼叫。 在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。 默认值为 10。|10|数字|Int|
|否|ForwardCallHistory |指示是否通过中继转移呼叫历史记录信息。 如果启用，Office 365 PSTN 代理发送两个标头： 历史记录信息和推荐者。 默认值为**False** ($False)。 |False|True<br/>False|Boolean|
|否|ForwardPAI|指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。 PAI 标头提供了一种验证呼叫者身份的方法。 如果启用了隐私： ID 还会发送标头。 默认值为**False** ($False)。|False|True<br/>False|Boolean|
|否|SendSIPOptions |定义如果 SBC 将或将不会发送 SIP 选项。 如果禁用，将从监控和警报系统中排除 SBC。 我们强烈建议您启用 SIP 选项。 默认值为**True**。 |True|True<br/>False|Boolean|
|否|MaxConcurrentSessions |使用警报系统。 90%的并发会话数时警报系统时设置的任何值，将生成向租户管理员警报或高于此值。 如果未设置参数，则不会生成通知。 但是，监视系统将报告并发会话每 24 小时的数。 |Null|Null<br/>1 至 100,000 ||
|否|启用 *|用于启用出站呼叫的此 SBC。 可用于时正在更新或维护期间中临时删除 SBC。 |False|True<br/>False|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>验证 SBC 配对 

验证连接： 
- 检查 SBC 是否在列表中的配对 SBCs。 
- 验证 SIP 选项。 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>验证 SBC 是否在列表中的配对的 Sbc 

对 SBC 后，验证 SBC 存在于列表中的配对 SBCs 通过远程 PowerShell 会话中运行以下命令：`Get-CSOnlinePSTNGateway`

配对的网关应显示在列表中，如下面的示例中所示，并验证参数*启用*显示值**True**。 输入：

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
返回结果：
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

#### <a name="validate-sip-options-flow"></a>验证 SIP Options 流 

若要验证配对使用传出 SIP 选项，请使用 SBC 管理接口，并确认 SBC 接收其传出 OPTIONS 消息的 200 OK 响应。

当直接路由中看到传入的选项时，则它将启动发送消息 SBC fqdn 配置传入的选项消息中的联系人标头字段中的传出 SIP 选项。 

要验证配对使用传入 SIP 选项，请使用 SBC 管理接口，并查看 SBC 发送给直接路由从传入 OPTIONS 消息的答复和发送响应代码是 200 确定。

## <a name="enable-users-for-direct-routing-service"></a>为用户启用直接路由服务 

已准备好启用用户直接路由服务，请按照下列步骤： 

1. Office 365 中创建用户和分配电话系统许可证。 
2. 确保业务 online 用户驻留在 Skype。 
3. 配置的电话号码并启用企业语音和语音邮件。 
4. 配置语音路由。 自动验证路由。

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>在 Office 365 中创建用户和分配许可证 

有两个选项的 Office 365 中创建新用户。 但是，我们建议您的组织选择和使用一个选项以避免路由问题： 

- 内部部署 Active Directory 中创建用户和同步到云用户。 请参阅[Azure Active Directory 集成本地目录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Office 365 管理门户中创建用户。 请参阅[添加用户单独或到 Office 365-批量管理帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果业务 Online 部署您 Skype 共同存在与 Skype 的业务 2015年或 Lync 2010/2013年内部部署，仅受支持的选项是在本地 Active Directory 中创建用户并同步到云 (选项 1) 的用户。 

必需的许可证： 

- Office 365 企业版 E3 （包括 SfB Plan2、 Exchange Plan2 和团队） + 电话系统
- Office 365 企业 E5 （包括 SfB Plan2、 Exchange Plan2、 团队和电话系统） 

可选许可证： 

- 调用计划 
- 音频会议 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>确保业务 online 用户驻留在 Skype 

直接路由，要求用户为业务 Online Skype 托管。 您可以检查这看 RegistrarPool 参数。 它需要 infra.lync.com 域中有一个值。

1. 连接到远程 PowerShell。
2. 发出命令： 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>配置的电话号码和启用企业语音和语音邮件 

您已创建用户和分配许可证后下, 一步是配置他们的电话号码和语音邮件。 进行这种一个步骤。 

若要添加的电话号码，并启用语音邮件：
 
1. 连接到远程 PowerShell 会话。 
2. 输入命令： 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

例如，若要添加的用户"Spencer 低"的电话号码，您可输入下列： 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

使用的电话号码必须配置为完整的 E.164 电话号码与国家/地区代码。 

  > [!NOTE]
  > 如果在本地管理用户的电话号码，使用内部部署 Skype 业务命令行管理程序或控制面板配置用户的电话号码。 

### <a name="configure-voice-routing"></a>配置语音路由 

Microsoft 电话系统具有可以将呼叫发送给基于特定 SBC 路由机制： 

- 呼叫的号码模式 
- 呼叫的号码模式 + 调用的特定用户
 
Sbc 可以被指定为活动状态且备份。 这意味着当配置为此号码模式或号码模式 + 特定用户活动 SBC 不可用，然后呼叫将路由至备份 SBC。
 
呼叫路由组成的以下元素： 
- 语音路由策略 – 容器的 PSTN 用法;可分配给用户或多个用户 
- PSTN 用法 – 语音路由和 PSTN 用法; 容器可以共享在不同的语音路由策略 
- 语音路由 – 号码模式和联机 PSTN 网关，以用于呼叫其中号码匹配模式的设置 
- 联机 PSTN 网关-指向 SBC，还会存储通过 SBC，如转发 P 已断言标识 (PAI) 或首选的编解码器; 发出呼叫时应用的配置可以添加到语音路由 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>使用一个 PSTN 用法创建语音路由策略 

下图显示呼叫流中的语音路由策略的两个示例。

**（左侧） 呼叫流 1:** 如果用户选择调用 +1 425 XXX XX XX 或 +1 206 XXX XX XX，呼叫被路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果既不 sbc1.contoso.biz，也不 sbc2.contoso.biz 都可用，呼叫将被丢弃。 

**（在右侧） 呼叫流 2:** 如果用户选择调用 +1 425 XXX XX XX 或 +1 206 XXX XX XX，呼叫首先路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果既 SBC 可用，具有低优先级路由将尝试 （sbc3.contoso.biz 和 sbc4.contoso.biz）。 如果 SBCs 均不可用，呼叫将被丢弃。 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在这两个示例中，而语音路由分配优先级，在将路由 SBCs 会尝试按随机顺序。

  > [!NOTE]
  > 除非用户也有 Microsoft 调用规划许可证，除 +1 425 XXX XX XX 或 +1 206 XXX XX XX 示例配置中的模式匹配的号码之外的任何号码的呼叫会被丢弃。 如果用户具有调用规划许可证，该呼叫将自动路由根据 Microsoft 调用计划的策略。 

Microsoft 调用规划自动作为最后一个路由适用于使用 Microsoft 调用规划许可证的所有用户，并且不需要其他呼叫路由配置。

在下图中所示的示例中，添加语音路由以将呼叫发送到所有其他美国和加拿大号码 （+ 1 XXX XXX XX XX 转到呼叫的号码模式的呼叫）。

![显示语音路由策略与第三个路由](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

对于所有其他呼叫，如果用户具有两个许可证 （Microsoft 电话系统并规划 Microsoft 调用），则使用自动路由。 如果 nothing 匹配管理员创建联机语音路由，路由通过 Microsoft 调用规划中的号码模式。

如果用户具有仅 Microsoft 电话系统，呼叫将被丢弃因为没有匹配的规则时可用。

  > [!NOTE]
  > 路由"其他 + 1"的优先级值不在这种情况下，重要，因为没有只有一个路由相匹配的模式 + 1 XXX XXX XX XX。 如果用户调用 + 1 324 567 89 89 并且 sbc5.contoso.biz 和 sbc6.contoso.biz 不可用，呼叫将被丢弃。

下表总结了使用三个语音路由配置。 本示例中，所有三个路由是相同的 PSTN 用法"美国和 Canada"的一部分。

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|仅限美国|"Redmond 1"|^\\+ 1 (425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX 拨电话号码|
|仅限美国|"Redmond 2"|^\\+ 1 (425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|备份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX 拨电话号码|
|仅限美国|"其他 + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼叫的号码的路由 （除 +1 425 XXX XX XX 或 +1 206 XXX XX XX） + 1 XXX XXX XX XX|
|||||||

所有路由与 PSTN 用法"美国和加拿大"相关联，PSTN 用法相关联的语音路由策略"仅美国。" 本示例中，语音路由策略分配给用户 Spencer 低。

#### <a name="examples-of-call-routes"></a>呼叫路由的示例

在以下示例中，我们将演示如何配置路由、 PSTN 用法和路由策略，并将策略分配给用户。

**步骤 1:** 创建 PSTN 用法"美国和加拿大"。

在业务远程 PowerShell 会话 Skype，键入：

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

验证通过输入创建的使用情况： 
```
Get-CSOnlinePSTNUsage
``` 
这将返回可能会被截断的名称的列表：
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
在下面的示例中，您可以查看正在运行的结果的 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`显示 （不会被截断） 的完整名称。 
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

**步骤 2:** 在 PowerShell 中的业务联机 Skype 会话中创建三个路由： Redmond 1，2 和其他 + 1，Redmond 上表中所述。 

若要创建"Redmond 1"路由，请输入：

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

返回结果：
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
若要创建 Redmond 2 路由，请输入：

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要创建的其他 + 1 路由，请输入：

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 确保您正则表达式中的 NumberPattern 属性是一个有效的表达式。 您可以测试它使用此网站：[https://www.regexpal.com](https://www.regexpal.com)

在某些情况下没有需要所有将呼叫路由到相同的 SBC;请使用-NumberPattern"。 *"

- 所有将呼叫路由到相同的 SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

验证是否已正确配置路由通过运行`Get-CSOnlineVoiceRoute`PowerShell 命令使用选项，如下所示： 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
应返回其中：
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

在示例中，该路由"其他 + 1"已自动分配优先级 4。 

**步骤 3:**"我们仅"创建语音路由策略和向策略中添加 PSTN 用法"美国和加拿大。"

在 PowerShell 会话中的业务联机 Skype 中，键入：

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

在此示例中显示结果：

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**步骤 4:** 向用户授予 Spencer 低语音路由策略使用 PowerShell。

- 在 PowerShell 会话中的业务联机 Skype 中，键入：

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- 通过输入以下命令来验证策略分配：

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
返回结果：
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>使用多个 PSTN 用法创建语音路由策略

创建语音路由策略以前只允许对在美国和加拿大-电话号码的呼叫除非 Microsoft 调用规划许可证将同时赋给用户。

在下面的示例，您可以创建语音路由策略"没有限制。" 策略重复 PSTN 用法"美国和加拿大"创建在上面的示例，以及新的 PSTN 用法"International。" 

这将路由到的 Sbc sbc2.contoso.biz 和 sbc5.contoso.biz 的所有其他呼叫。 所示的示例将仅美国"Spencer 低，"用户策略和无限制分配给用户"John Woods"。

Spencer 低 – 允许仅对美国和加拿大号码的呼叫。 当调用雷德蒙德号码范围，必须使用 SBC 的特定集。 除非调用规划许可证分配给用户，将不会路由非美国号码。

John Woods – 允许任意数量的呼叫。 当调用雷德蒙德号码范围，必须使用 SBC 的特定集。 将通过 sbc2.contoso.biz 和 sbc5.contoso.biz 路由非美国号码。

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

对于所有其他呼叫，如果用户具有两个许可证 （Microsoft 电话系统并规划 Microsoft 调用），则使用自动路由。 如果 nothing 匹配管理员创建联机语音路由，路由通过 Microsoft 调用规划中的号码模式。

如果用户具有仅 Microsoft 电话系统，呼叫将被丢弃因为没有匹配的规则时可用。

![显示分配给用户 John Woods 的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表总结了路由策略"无限制"使用率标识和语音路由。 

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|仅限美国|"Redmond 1"|^\\+ 1 (425\|206)(\d{7})$|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被叫方号码 +1 425 XXX XX XX 或 +1 206 XXX XX XX 活动路由|
|仅限美国|"Redmond 2"|^\\+ 1 (425\|206)(\d{7})$|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被叫方号码 +1 425 XXX XX XX 或 +1 206 XXX XX XX 备份路由|
|仅限美国|"其他 + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>.contoso.biz|被叫方路由号码 + 1 XXX XXX XX XX （除 +1 425 XXX XX XX 或 +1 206 XXX XX XX）|
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何号码模式的路由 |


  > [!NOTE]
  > - 在语音路由策略中的 PSTN 用法的顺序至关重要。 用法的顺序，应用，如果找到匹配的中第一个用法，然后其他用法从不计算。 PSTN 用法"International"必须放置后 PSTN 用法"我们仅。" 若要更改的 PSTN 用法的顺序，请运行`Set-CSOnlineVoiceRoutingPolicy`命令。 <br/>例如，若要更改的顺序从"美国和加拿大"第一个和"国际"秒到相反的顺序运行：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 自动分配"其他 + 1"和"International"语音路由的优先级。 他们不重要，只要他们具有较低的优先级，比"Redmond 1"和"Redmond 2"。

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>为用户 John Woods 的语音路由策略示例

步骤创建 PSTN 用法"International"语音路由"International，"语音路由策略"无限制"，然后将其分配给用户"John Woods"，如下所示。


1. 首先，创建 PSTN 用法"International。" 在 Skype 业务 online 中的远程 PowerShell 会话，输入：

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. 接下来，创建新的语音路由"International。"

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   返回结果：

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. 接下来，创建语音路由策略"无限制"。 若要保留为"+1 425 XXX XX XX"和"+1 206 XXX XX XX"作为本地号码的呼叫或本地呼叫的特殊处理此语音路由策略中重复使用的 PSTN 用法"Redmond 1"和"Redmond"。

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   其返回

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. 将语音路由策略分配给用户"John Woods"使用以下命令。

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   然后验证工作分配使用的命令： 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   返回结果：

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

应用于 John Woods 呼叫的语音策略是不受限制，并将按照呼叫路由适用于美国、 加拿大和国际呼叫的逻辑，结果。

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a>为用户设置为首选调用客户端的 Microsoft 团队

直接路由仅将呼叫路由到用户与如果他们使用团队客户端。 如果您的组织仅使用团队，"仅工作组"设置模式中升级策略建议。 如果您的组织使用业务 online 业务服务器或 Skype Skype，请参阅以下文章，获取详细信息，然后选择适当的选项：[了解共存和升级的业务和团队的 Skype 旅程](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)。 


## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)
