---
title: 将会话边界控制器 (SBC) 连接到直接路由
ms.reviewer: fillipse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 SBC 并将其连接到 Teams 电话系统直接路由。
ms.openlocfilehash: b34762b9df84839b17be6693b9ed782b5029525a
ms.sourcegitcommit: 2f9a83a1bae8cbee5a0d65464bd47f6735b2d206
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2022
ms.locfileid: "69025164"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>将会话边界控制器 (SBC) 连接到直接路由

本文介绍如何配置会话边界控制器 (SBC) 并将其连接到直接路由。  这是配置直接路由的以下步骤中的步骤 1：

- **步骤 1.将 SBC 与电话系统连接并验证 (** 本文) 
- 第 2 步 [为用户启用直接路由](direct-routing-enable-users.md)
- 第 3 步 [配置呼叫路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md)

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

可以使用 [Microsoft Teams 管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShell](#using-powershell) 配置 SBC 并将其连接到直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到 **“语音** > **直接路由**”，然后单击“ **SBC** ”选项卡。

2. 单击“**添加**”。

3. 输入 SBC 的 FQDN。 <br><br>请确保 FQDN 的域名部分与租户中注册的域匹配，并记住 `*.onmicrosoft.com` SBC FQDN 域名不支持该域名。 例如，如果有两个域名 `contoso.com` 和 `contoso.onmicrosoft.com`，请使用 `sbc.contoso.com` 作为 SBC 名称。 如果使用子域，请确保此子域也在租户中注册。 例如，如果要使用 `sbc.service.contoso.com`， `service.contoso.com` 则需要注册 。

4. 根据组织的需要为 SBC 配置以下设置。 有关其中每个设置的详细信息，请参阅 [SBC 设置](#sbc-settings)。

    ![Microsoft Teams 管理中心中“添加 SBC”页面的屏幕截图。](media/direct-routing-add-sbc.png)

5. 完成时单击“**保存**”。

## <a name="using-powershell"></a>使用 PowerShell

若要将 SBC 连接到直接路由，需要：

1. [使用 PowerShell 连接到 Skype for Business Online](#connect-to-skype-for-business-online-by-using-powershell)。

2. [将 SBC 连接到租户](#connect-the-sbc-to-the-tenant)。

3. [验证 SBC 连接](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 连接到 Skype for Business Online

若要将 SBC 与直接路由接口配对，请使用连接到租户的 PowerShell 会话。 若要打开 PowerShell 会话，请按照[为Windows PowerShell设置计算机](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中所述的步骤进行操作。
 
建立远程 PowerShell 会话后，验证是否可以看到用于管理 SBC 的命令。 若要验证命令，请在 PowerShell 会话中键入或复制并粘贴以下命令，然后按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

命令返回此处所示的四个函数，用于管理 SBC。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>将 SBC 连接到租户

若要将 SBC 连接到租户，请使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet。 在 PowerShell 会话中，键入以下内容，然后按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 建议使用 SBC 文档中的信息在 SBC 中设置最大调用限制。 如果 SBC 处于容量级别，则限制将触发通知。
  > 2. 仅当其 FQDN 的域部分与租户中注册的某个域（.onmicrosoft.com 除外 \*）匹配时，才能连接 SBC。 SBC FQDN 名称不支持使用 \*.onmicrosoft.com 域名。 例如，如果有两个域名 **contoso.com** 和 **contoso.onmicrosoft.com**，则可以将 sbc.contoso.com 用于 SBC 名称。 如果尝试使用 sbc.contoso.abc 等名称连接 SBC，系统将不允许你，因为域不归此租户所有。<br/>
  > 除了在租户中注册的域外，还必须有一个用户具有该域和分配的 E3 或 E5 许可证。 否则，将收到以下错误：<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. 不支持在 SBC 端使用同一 FQDN 映射的多个 IP。
  > 4. 为了为客户提供一流的加密，Microsoft 将强制使用直接路由 SIP 接口的 TLS1.2。
  > 若要避免任何服务影响，请确保 SBC 配置为支持 TLS1.2，并且可以使用以下密码套件之一进行连接：TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384即 ECDHE-RSA-AES256-GCM-SHA384 TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256即 ECDHE-RSA-AES128-GCM-SHA256 TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384即 ECDHE-RSA-AES256-SHA384 TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256即 ECDHE-RSA-AES128-SHA256
  > 5. SIP OPTIONS ping 不能每 60 秒超过一个事务的频率，并且对于每个终结点的每个配置的中继，不能超过每 180 秒一个事务的频率。

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
> 此示例仅显示所需的最小参数。 在连接过程中，可以使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 设置其他参数。 若要了解详细信息，请参阅 [SBC 设置](#sbc-settings)。
 
### <a name="verify-the-sbc-connection"></a>验证 SBC 连接

若要验证连接，请执行以下操作：

- [检查 SBC 是否位于配对 SBC 列表中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [验证 SIP 选项](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>检查 SBC 是否在配对 SBC 列表中

连接 SBC 后，使用 [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) cmdlet 验证 SBC 是否存在于配对 SBC 列表中。 在远程 PowerShell 会话中键入以下内容，然后按 Enter：

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

配对的网关应如以下示例所示显示在列表中， **Enabled** 参数应显示值为 **True**。

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

若要使用传出 SIP 选项验证配对，请使用 SBC 管理接口并确认 SBC 收到对其传出 OPTIONS 消息的 200 个正常响应。

当直接路由看到传入选项时，它将开始将传出 SIP 选项消息发送到在传入 OPTIONS 消息的“联系人标头”字段中配置的 SBC FQDN。 

若要使用传入 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 是否对来自直接路由的 OPTIONS 消息发送答复，并且它发送的响应代码是否为 200 正常。

## <a name="sbc-settings"></a>SBC 设置

下表列出了可以在 Microsoft Teams 管理中心和使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 为 SBC 设置的选项。

|必填？|Teams 管理中心设置|PowerShell 参数|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**为 SBC 添加 FQDN**|FQDN |无|FQDN 名称，限制为 63 个字符|字符串，请参阅 [Active Directory 中计算机、域、站点和 OU 的命名约定](https://support.microsoft.com/help/909264)中允许和不允许的字符列表|
|否|**已启用**|已启用|使用 为出站呼叫打开 SBC。 在服务更新或维护期间，可以使用它暂时从服务中删除 SBC。 |False|True<br/>False|Boolean|
|是|**SIP 信令端口**|SipSignalingPort |这是用于使用传输层 (TLS) 协议与直接路由通信的侦听端口。|无|任何端口|0 到 65535 |
|否|**发送 SIP 选项**|SendSIPOptions |定义 SBC 是否发送 SIP 选项消息。 强烈建议启用此设置。 当此设置处于关闭状态时，SBC 将从监视和警报系统中排除。|True|True<br/>False|Boolean|
|否|**转发呼叫历史记录**|ForwardCallHistory |指示是否通过中继转发呼叫历史记录信息。 启用此功能后，Microsoft 365 代理会发送历史记录信息和 Referred-by 标头。 |False|True<br/>False|Boolean|
|否|**转发 P-Asserted-identity (PAI) 标头**|ForwardPAI|指示是否将 PAI 标头与调用一起转发。 PAI 标头提供了一种验证呼叫者身份的方法。 如果此设置处于打开，则还会发送 Privacy：ID 标头。|False|True<br/>False|Boolean|
|否|**并发呼叫容量**|MaxConcurrentSessions |设置值时，当并发会话数超过此值 90% 或更高时，警报系统将通知你。 如果未设置值，则不会生成警报。 但是，监视系统将每 24 小时报告一次并发会话数。 |空|空<br/>1 到 100，000 ||
|否|**故障转移响应代码**|FailoverResponseCodes<br>|如果直接路由收到任何 4xx 或 6xx SIP 错误代码以响应传出邀请，则默认情况下，该呼叫被视为已完成。 传出表示从 Teams 客户端到 PSTN 的呼叫，其中包含流量流：Teams 客户端 -> 直接路由 -> SBC ->电话网络) 。 指定故障转移响应代码时，如果 SBC 因网络或其他问题而无法进行呼叫，则如果用户) 的语音路由策略中存在另一个 SBC，则强制直接路由尝试另一个 SBC (。 若要了解详细信息，请参阅 [从会话边界控制器 (SBC) 接收的特定 SIP 代码的故障转移 ](direct-routing-trunk-failover-on-outbound-call.md)。|408, 503, 504||Int|
|否|**故障转移时间 (秒)**|FailoverTimeSeconds |设置值时，网关在设置的时间内未应答的出站调用将路由到下一个可用中继。 如果没有其他中继，则会自动删除呼叫。 默认值为 10 秒。 在网络和网关响应缓慢的组织中，这可能会导致不必要地丢弃呼叫。|10|数字|Int|
|否|**媒体流量的首选国家或地区**|MediaRelayRoutingLocationOverride | 不适用于直接路由。 此参数保留用于通话套餐中的托管运营商 |无|||
|否|**SBC 支持 PIDF/LO 进行紧急呼叫**|PidfloSupported|指定 SBC 是否支持状态信息数据格式位置对象 (PIDF/LO) 进行紧急呼叫。||||
|否| - |MediaBypass|此设置指示 SBC 是否支持媒体旁路，以及是否要将它用于此 SBC。 |无|True<br/>False|Boolean|

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)

[Teams PowerShell 概览](teams-powershell-overview.md)
