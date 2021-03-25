---
title: 将会话边界控制器 (SBC) 直接路由
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
description: 了解如何配置 SBC 并连接到电话系统直接路由。
ms.openlocfilehash: 697f426b9c9dc3215d653520658282fab1787001
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122246"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>将会话边界控制器 (SBC) 直接路由

本文介绍如何配置 SBC (边界控制器) 连接到电话系统直接路由。  这是配置直接路由的以下步骤的步骤 1：

- **步骤 1.将 SBC 与电话系统连接并验证** (本文) 
- 第 2 步 [为用户启用直接路由](direct-routing-enable-users.md)
- 第 3 步 [配置呼叫路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md)

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

可以使用 Microsoft [Teams 管理中心或](#using-the-microsoft-teams-admin-center) [PowerShell](#using-powershell) 配置 SBC 并连接到直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到 **"语音**  >  **直接路由"，** 然后单击 **"SDC"** 选项卡。
2. 单击“**添加**”。
3. 输入 SBC 的 FQDN。 <br><br>请确保 FQDN 的域名部分与在租户中注册的域匹配，并且请记住 `*.onmicrosoft.com` ，SBC FQDN 域名不支持该域名。 例如，如果有两个域名和 `contoso.com` `contoso.onmicrosoft.com` ，请使用 作为 `sbc.contoso.com` SBC 名称。 如果使用子域，请确保此子域也在租户中注册。 例如，如果要使用 `sbc.service.contoso.com` ，需要 `service.contoso.com` 注册 。
4. 根据组织的需求为 SBC 配置以下设置。 有关这些设置的详细信息，请参阅 [SBC 设置](#sbc-settings)。

    ![Microsoft Teams 管理中心中添加 SBC 页面的屏幕截图](media/direct-routing-add-sbc.png)

5. 完成时单击“**保存**”。

## <a name="using-powershell"></a>使用 PowerShell

若要将 SBC 连接到直接路由，需要：

1. [使用 PowerShell 连接到 Skype for Business Online。](#connect-to-skype-for-business-online-by-using-powershell)
2. [将 SBC 连接到租户](#connect-the-sbc-to-the-tenant)。
3. [验证 SBC 连接](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 连接到 Skype for Business Online

可以使用连接到租户的 PowerShell 会话将 SBC 与直接路由接口配对。 若要打开 PowerShell 会话，请执行为计算机设置[Windows PowerShell。](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
建立远程 PowerShell 会话后，请验证是否可以看到用于管理 SBC 的命令。 若要验证命令，请在 PowerShell 会话中键入或复制并粘贴以下命令，然后按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

该命令返回此处所示的四个函数，用于管理 SBC。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>将 SBC 连接到租户

使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 将 SBC 连接到租户。 在 PowerShell 会话中，键入以下内容，然后按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 建议使用 SBC 文档中的信息在 SBC 中设置最大调用限制。 如果 SBC 在容量级别，则限制将触发通知。
  > 2. 只有在 SBC 的 FQDN 域部分与租户中注册的域之一匹配时，才能连接 SBC，但 \* .onmicrosoft.com。 SBC \* FQDN 名称不支持使用 .onmicrosoft.com 域名。 例如，如果有两个域名 **（contoso**.com 和 **contoso**.onmicrosoft.com，可以使用 sbc.contoso.com 作为 SBC 名称。 如果尝试使用 sbc.contoso.abc 等名称连接 SBC，系统不会允许你，因为域不是此租户所有的。<br/>
  > 除了在租户中注册的域外，必须存在具有该域的用户以及分配的 E3 或 E5 许可证。 如果没有，将收到以下错误：<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

下面是一个示例：

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

这将返回：

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
> 此示例只显示所需的最小参数。 在连接过程中，可以使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 设置其他参数。 有关详细信息，请参阅 [SBC 设置](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>验证 SBC 连接

验证连接：

- [检查 SBC 是否位于配对的 SBC 列表中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [验证 SIP 选项](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>检查 SBC 是否位于配对的 SBC 列表中

连接 SBC 后，使用 [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) cmdlet 验证 SBC 是否存在于配对的 SBC 列表中。 在远程 PowerShell 会话中键入以下内容，然后按 Enter：

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

配对网关应显示在列表中，如以下示例所示，Enabled 参数应显示值为 **True。** 

这将返回：

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

若要使用传出 SIP 选项验证配对，请使用 SBC 管理接口，并确认 SBC 接收了对传出 OPTIONS 消息的 200 OK 响应。

当直接路由看到传入选项时，它将开始将传出 SIP 选项消息发送到传入 OPTIONS 消息的"联系人标头"字段中配置的 SBC FQDN。 

若要使用传入的 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 向来自直接路由的 OPTIONS 消息发送回复，并且它发送的响应代码为 200 正常。

## <a name="sbc-settings"></a>SBC 设置

下表列出了可以在 Microsoft Teams 管理中心使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 为 SBC 设置的选项。

|必填？|Microsoft Teams 管理中心设置|PowerShell 参数|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**为 SBC 添加 FQDN**|FQDN |无|FQDN 名称，限制为 63 个字符|字符串，请参阅[Active Directory](https://support.microsoft.com/help/909264)中计算机、域、站点和 OUS 的命名约定中允许和禁止的字符列表|
|否|**已启用**|已启用|使用 为出站调用启用 SBC。 可以使用此功能在 SBC 更新期间或维护期间暂时将其从服务中删除。 |False|True<br/>False|Boolean|
|是|**SIP 信号端口**|SipSignalingPort |这是一个侦听端口，用于通过 TLS 协议使用传输层 (直接) 路由。|无|任何端口|0 到 65535 |
|否|**发送 SIP 选项**|SendSIPOptions |定义 SBC 是否发送 SIP 选项消息。 强烈建议启用此设置。 当此设置关闭时，SBC 将排除在监视和警报系统中。|True|True<br/>False|Boolean|
|否|**转发呼叫历史记录**|ForwardCallHistory |指示是否通过中继转发呼叫历史记录信息。 打开此选项时，Microsoft 365 或 Office 365 代理将发送 History-info 和 Referred-by 标头。 |False|True<br/>False|Boolean|
|否|**将 P-Asserted-identity (PAI) 标头**|ForwardPAI|指示 PAI 标头是否随调用一起转发。 PAI 标头提供了一种验证呼叫者身份的方法。 如果启用此设置，则还会发送 Privacy：ID 标头。|False|True<br/>False|Boolean|
|否|**并发调用容量**|MaxConcurrentSessions |设置值时，当并发会话数为 90% 或高于此值时，警报系统将通知你。 如果未设置值，不会生成警报。 但是，监视系统将每 24 小时报告一次并发会话数。 |Null|Null<br/>1 到 100，000 ||
|否|**故障转移响应代码**|FailoverResponseCodes<br>|如果直接路由收到任何 4xx 或 6xx SIP 错误代码以响应传出邀请，则默认情况下，呼叫被视为已完成。 传出是指使用流量流从 Teams 客户端呼叫 PSTN：Teams 客户端 -> 直接路由 -> SBC -> 电话) 。 指定故障转移响应代码时，如果 SBC 由于网络或其他问题而无法进行呼叫，则当用户) 的语音路由策略中存在另一个 SBC 时，这会强制直接路由尝试另一个 SBC (。 有关详细信息，请参阅从会话边界控制器或[SBC (接收的特定 SIP) 。 ](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|否|**故障转移时间 (秒)**|FailoverTimeSeconds |设置值时，网关在您设置的时间内未应答的出站调用将路由到下一个可用的中继。 如果没有其他中继，则会自动丢弃呼叫。 默认值为 10 秒。 在网络和网关响应速度缓慢的组织中，这可能会导致不必要的呼叫被丢弃。|10|数字|Int|
|否|**媒体流量的首选国家/地区**|MediaRelayRoutingLocationOverride |使用 手动设置媒体流量的首选国家/地区。 建议仅在调用日志明确指示媒体路径的数据中心默认分配不使用离 SBC 数据中心最近的路径时，才设置此选项。 默认情况下，直接路由基于 SBC 的公共 IP 地址分配数据中心，并始终选择最靠近 SBC 数据中心的路径。 但是，在某些情况下，默认路径可能不是最佳路径。 此参数允许手动设置媒体流量的首选区域。 |无|ISO 格式的国家/地区代码||
|否|**SBC 支持对紧急呼叫使用 PIDF/LO**|PidfloSupported|指定 SBC 是否支持紧急呼叫的 PIDF/LO (状态信息数据格式) 对象。||||
|否| - |MediaBypass|此设置指示 SBC 是否支持媒体旁路，以及是否要将媒体旁路用于此 SBC。 |无|True<br/>False|Boolean|

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)

[Teams PowerShell 概览](teams-powershell-overview.md)