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
description: 了解如何配置 SBC 并将其连接到手机系统直接路由。
ms.openlocfilehash: fbcc1d79a4875ba835fc77ea24f6356ded3da894
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159030"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>将会话边界控制器（SBC）连接到直接路由

本文介绍如何配置会话边界控制器（SBC），并将其连接到 "手机系统直接路由"。  下面是配置直接路由的步骤1：

- **步骤1。将 SBC 与电话系统连接并验证连接**（本文）
- 第 2 步 [为用户启用直接路由](direct-routing-enable-users.md)
- 第 3 步 [配置呼叫路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 

有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。

你可以使用[Microsoft 团队管理中心](#using-the-microsoft-teams-admin-center)或[PowerShell](#using-powershell)配置 SBC 并将其连接到直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到 "**语音** > **直接路由**"，然后单击 " **SBCs** " 选项卡。
2. 单击“添加”****。
3. 输入 SBC 的 FQDN。 <br><br>请确保 FQDN 的域名部分与你的租户中注册的域相匹配，请记住，SBC FQDN 域名不`*.onmicrosoft.com`支持该域名。 例如，如果你有两个域名， `contoso.com`并且`contoso.on.microsoft.com`将`sbc.contoso.com`用作 SBC 名称。
4. 根据组织的需求配置 SBC 的以下设置。 有关这些设置的详细信息，请参阅[SBC 设置](#sbc-settings)。

    ![Microsoft 团队管理中心中 "添加 SBC" 页面的屏幕截图](media/direct-routing-add-sbc.png)

5. 完成时单击“**保存**”。

## <a name="using-powershell"></a>使用 PowerShell

要将 SBC 连接到直接路由，您需要：

1. [使用 PowerShell 连接到 Skype for Business Online](#connect-to-skype-for-business-online-by-using-powershell)。
2. [将 SBC 连接到租户](#connect-the-sbc-to-the-tenant)。
3. [验证 SBC 连接](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 连接到 Skype for business Online

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

### <a name="connect-the-sbc-to-the-tenant"></a>将 SBC 连接到租户

使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) CMDLET 将 SBC 连接到租户。 在 PowerShell 会话中，键入以下内容，然后按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 我们建议使用 SBC 文档中可以找到的信息，在 SBC 中设置最大通话限制。 如果 SBC 处于容量级别，则该限制将触发通知。
  > 2. 仅当 FQDN 的域部分与租户中注册的一个域（onmicrosoft.com 除外\*）匹配时，才能连接 SBC。 SBC \*FQDN 名称不支持使用 onmicrosoft.com 域名。 例如，如果你有两个域名、 **contoso****和 onmicrosoft.com**，则可以使用 sbc for sbc 名称。 如果你尝试使用名称（如 sbc）连接 SBC，则系统将不会允许你，因为域不属于此租户。<br/>
  > 除了在租户中注册的域，还必须有一个用户使用该域和分配的 E3 或 E5 许可证。 如果不是，您将收到以下错误：<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

下面是一个示例：

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

返回：

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

> [!NOTE]
> 此示例仅显示所需的最低参数。 在连接过程中，你可以用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet 设置其他参数。 若要了解详细信息，请参阅[SBC 设置](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>验证 SBC 连接

若要验证连接，请执行以下操作：

- [检查 SBC 是否在成对的 SBCs 的列表中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [验证 SIP 选项](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>检查 SBC 是否位于成对的 SBCs 的列表中

连接 SBC 后，请使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) CMDLET 验证 sbc 是否存在于成对的 SBCs 列表中。 在远程 PowerShell 会话中键入以下内容，然后按 Enter：

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

#### <a name="validate-sip-options"></a>验证 SIP 选项

若要使用传出 SIP 选项验证配对，请使用 SBC 管理界面并确认 SBC 是否收到对其传出选项消息的 200 OK 响应。

当直接路由看到传入选项时，它将向 "传入选项" 消息的 "联系人标题" 字段中配置的 SBC FQDN 开始发送传出 SIP 选项消息。 

若要使用传入 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 是否向来自直接路由的选项消息发送回复，并且它发送的响应代码为 200 OK。

## <a name="sbc-settings"></a>SBC 设置

下表列出了可在 Microsoft 团队管理中心和使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet 设置的 SBC 选项。

|必填？|Microsoft 团队管理中心设置|PowerShell 参数|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**为 SBC 添加 FQDN**|FQDN |无|FQDN 名称，限制63个字符|字符串，请参阅[适用于计算机、域、网站和 ou 的 Active Directory 中的命名约定](https://support.microsoft.com/help/909264)的允许和不允许的字符列表|
|否|**已启用**|已启用|用于为出站呼叫启用 SBC。 你可以使用此功能在更新或维护期间将 SBC 从服务中临时删除。 |False|True<br/>False|Boolean|
|是|**SIP 信号端口**|SipSignalingPort |这是用于通过使用传输层（TLS）协议与直接路由进行通信的侦听端口。|无|任何端口|0到65535 |
|否|**发送 SIP 选项**|SendSIPOptions |定义 SBC 是否将发送 SIP 选项消息。 强烈建议您启用此设置。 当此设置关闭时，将从监视和警报系统中排除 SBC。|True|True<br/>False|Boolean|
|否|**转接呼叫历史记录**|ForwardCallHistory |指示是否通过主干转发通话历史记录信息。 启用此操作时，Office 365 代理将发送历史记录信息和引用者标头。 |False|True<br/>False|Boolean|
|否|**前进 P-声明标识（PAI）标题**|ForwardPAI|指示 PAI 标头是否与呼叫一起转发。 PAI 标头提供了一种验证呼叫者身份的方法。 如果此设置为 "打开"，则还会发送 "隐私： ID" 标头。|False|True<br/>False|Boolean|
|否|**并发通话容量**|MaxConcurrentSessions |当您设置值时，当并发会话的数量为90% 或高于此值时，警报系统将通知您。 如果不设置值，则不会生成警报。 但是，监视系统将每隔24小时报告一次并发会话的数量。 |Null|Null<br/>1到100000 ||
|否|**故障转移响应代码**|FailoverResponseCodes<br>|如果直接路由接收到任何用于响应传出邀请的4xx 或 6xx SIP 错误代码，则默认情况下该呼叫视为已完成。 "传出" 指通过流量流从团队客户端到 PSTN 的呼叫：团队客户端-> 直接路由-> SBC-> 电话网络）。 当你指定故障转移响应代码时，这会强制直接路由尝试使用另一个 SBC （如果用户的语音路由策略中存在另一个 SBC），当 SBC 由于网络或其他问题而无法进行呼叫时，收到指定的代码。 若要了解详细信息，请参阅[从会话边界控制器（SBC）处收到的特定 SIP 代码的故障转移](direct-routing-trunk-failover-on-outbound-call.md)。|408、503、504||整形|
|否|**故障转移时间（秒）**|FailoverTimeSeconds |当您设置值时，您设置的时间内网关未接听的出站呼叫将被路由到下一个可用的干线。 如果没有其他中继，将自动删除呼叫。 默认值为10秒。 在具有较慢网络和网关响应的组织中，这可能会导致不必要地丢弃呼叫。|10|数字|整形|
|否|**媒体流量的首选国家或地区**|MediaRelayRoutingLocationOverride |用于手动设置媒体流量的首选国家或地区。 我们建议你仅在通话记录明确指明媒体路径的数据中心的默认分配不使用与 SBC 数据中心最接近的路径时，才设置此设置。 默认情况下，直接路由根据 SBC 的公共 IP 地址分配数据中心，并始终选择最接近于 SBC 数据中心的路径。 但是，在某些情况下，默认路径可能不是最佳路径。 此参数允许你手动设置媒体流量的首选区域。 |无|ISO 格式的国家代码||
|否|**SBC 支持用于紧急呼叫的 PIDF/LO**|PidfloSupported|指定 SBC 是否支持用于紧急呼叫的状态信息数据格式位置对象（PIDF/LO）。||||
|否|**尝试查找用户时拨打电话**|GenerateRingingWhileLocatingUser|设置是否向呼叫者播放音频信号，以指示团队正在建立呼叫的过程。 此设置仅适用于非媒体绕过模式下的直接路由。 有时，从 PSTN 到团队客户端的入站呼叫的时间可能比预期的要长。 发生这种情况时，呼叫者可能听不到任何声音，团队客户不会听到任何信号，并且呼叫可能被某些电信提供商取消。 此设置有助于避免在这些情况下可能出现的意外 silences。|True|True<br/>False|Boolean|
|否| - |MediaBypass|此设置指示 SBC 是否支持媒体旁路以及是否要为此 SBC 使用它。 |无|True<br/>False|Boolean|

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)

[Teams PowerShell 概览](teams-powershell-overview.md)
