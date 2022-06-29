---
title: 将会话边框控制器 (SBC) 连接到直接路由
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
ms.openlocfilehash: e33f9538fdf69696e0a87da84dc5aec8e8d304af
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241101"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>将会话边框控制器 (SBC) 连接到直接路由

本文介绍如何配置会话边框控制器 (SBC) 并将其连接到直接路由。  这是配置直接路由的以下步骤的第 1 步：

- **步骤 1.将 SBC 与电话系统连接并验证连接** (本文) 
- 第 2 步 [为用户启用直接路由](direct-routing-enable-users.md)
- 第 3 步 [配置呼叫路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md)

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

可以使用 [Microsoft Teams 管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShell](#using-powershell) 配置 SBC 并将其连接到直接路由。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到 **“语音** > **直接路由**”，然后单击 **“SBC”** 选项卡。

2. 单击“**添加**”。

3. 输入 SBC 的 FQDN。 <br><br>请确保 FQDN 的域名部分与在租户中注册的域匹配，并记住 `*.onmicrosoft.com` SBC FQDN 域名不支持域名。 例如，如果你有两个域名， `contoso.com` 并且 `contoso.onmicrosoft.com`用作 `sbc.contoso.com` SBC 名称。 如果使用子域，请确保此子域也已在租户中注册。 例如，如果要使用 `sbc.service.contoso.com`，则 `service.contoso.com` 需要注册。

4. 根据组织的需求为 SBC 配置以下设置。 有关每个设置的详细信息，请参阅 [SBC 设置](#sbc-settings)。

    ![Microsoft Teams 管理中心中添加 SBC 页面的屏幕截图。](media/direct-routing-add-sbc.png)

5. 完成时单击“**保存**”。

## <a name="using-powershell"></a>使用 PowerShell

若要将 SBC 连接到直接路由，需要：

1. [使用 PowerShell 连接到 Skype for Business Online](#connect-to-skype-for-business-online-by-using-powershell)。

2. [将 SBC 连接到租户](#connect-the-sbc-to-the-tenant)。

3. [验证 SBC 连接](#verify-the-sbc-connection)。

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>使用 PowerShell 连接到 Skype for Business Online

若要将 SBC 与直接路由接口配对，请使用连接到租户的 PowerShell 会话。 若要打开 PowerShell 会话，请按照[“为Windows PowerShell设置计算机](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)”中所述的步骤操作。
 
建立远程 PowerShell 会话后，请验证是否可以看到用于管理 SBC 的命令。 若要验证命令，请在 PowerShell 会话中键入或复制并粘贴以下命令，然后按 Enter： 

```PowerShell
Get-Command *onlinePSTNGateway*
```

该命令返回此处显示的四个函数，用于管理 SBC。

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>将 SBC 连接到租户

若要将 SBC 连接到租户，请使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet。 在 PowerShell 会话中键入以下内容，然后按 Enter：

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. 建议使用可在 SBC 文档中找到的信息在 SBC 中设置最大调用限制。 如果 SBC 处于容量级别，则该限制将触发通知。
  > 2. 仅当 SBC FQDN 的域部分与租户中注册的域之一（.onmicrosoft.com 除外 \*）相匹配时，才能连接 SBC。 SBC FQDN 名称不支持使用 \*.onmicrosoft.com 域名。 例如，如果有两个域名，即 **contoso.com** 和 **contoso.onmicrosoft.com**，则可以对 SBC 名称使用 sbc.contoso.com。 如果尝试使用 sbc.contoso.abc 等名称连接 SBC，系统将不允许使用，因为该域不属于此租户。<br/>
  > 除了在租户中注册的域外，还必须有具有该域的用户以及分配的 E3 或 E5 许可证。 如果没有，则会收到以下错误：<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. 不支持在 SBC 端使用同一 FQDN 映射的多个 IP。

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

验证连接：

- [检查 SBC 是否位于配对 SBC 列表中](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)。
- [验证 SIP 选项](#validate-sip-options)。
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>检查 SBC 是否位于配对 SBC 列表中

连接 SBC 后，使用 [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) cmdlet 验证 SBC 是否存在于配对 SBC 列表中。 在远程 PowerShell 会话中键入以下内容，然后按 Enter：

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

配对网关应显示在列表中，如以下示例所示， **Enabled** 参数应显示 **True** 值。

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

若要使用传出 SIP 选项验证配对，请使用 SBC 管理接口并确认 SBC 收到对其传出 OPTIONS 消息的 200 个确定响应。

当直接路由看到传入选项时，它将开始将传出 SIP 选项消息发送到传入 OPTIONS 消息的“联系人”标头字段中配置的 SBC FQDN。 

若要使用传入的 SIP 选项验证配对，请使用 SBC 管理接口，并查看 SBC 是否发送对直接路由传入的 OPTIONS 消息的答复，以及它发送的响应代码为 200 正常。

## <a name="sbc-settings"></a>SBC 设置

下表列出了可以在 Microsoft Teams 管理中心和使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 为 SBC 设置的选项。

|必填？|Teams 管理中心设置|PowerShell 参数|描述|默认值|可能的值|类型和限制|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|是|**为 SBC 添加 FQDN**|FQDN |无|FQDN 名称，限制 63 个字符|字符串，请参阅 [Active Directory 中针对计算机、域、站点和 OU 的命名约定允许和不允许的](https://support.microsoft.com/help/909264)字符的列表|
|否|**已启用**|已启用|用于启用 SBC 进行出站调用。 在更新 SBC 时或在维护期间，可以使用此功能暂时从服务中删除 SBC。 |False|True<br/>False|Boolean|
|是|**SIP 信号端口**|SipSignalingPort |这是侦听端口，用于使用传输层 (TLS) 协议与直接路由通信。|无|任何端口|0 到 65535 |
|否|**发送 SIP 选项**|SendSIPOptions |定义 SBC 是否会发送 SIP 选项消息。 强烈建议启用此设置。 关闭此设置时，SBC 将从监视和警报系统中排除。|True|True<br/>False|Boolean|
|否|**转发呼叫历史记录**|ForwardCallHistory |指示是否通过中继转发调用历史记录信息。 启用此操作时，Microsoft 365 代理将发送历史记录信息和“引用”标头。 |False|True<br/>False|Boolean|
|否|**转发 P-Asserted-identity (PAI) 标头**|ForwardPAI|指示是否将 PAI 标头与调用一起转发。 PAI 标头提供了一种验证呼叫者身份的方法。 如果启用此设置，也会发送 Privacy：ID 标头。|False|True<br/>False|Boolean|
|否|**并发调用容量**|MaxConcurrentSessions |设置值时，当并发会话数为 90% 或高于此值时，警报系统会通知你。 如果未设置值，则不会生成警报。 但是，监视系统将每 24 小时报告一次并发会话数。 |空|空<br/>1 到 100，000 ||
|否|**故障转移响应代码**|FailoverResponseCodes<br>|如果直接路由在响应传出邀请时收到任何 4xx 或 6xx SIP 错误代码，则默认情况下会将调用视为已完成。 传出意味着从 Teams 客户端到流量流的 PSTN 的呼叫：Teams 客户端 ->直接路由 -> SBC ->电话网络) 。 指定故障转移响应代码时，如果用户的语音路由策略中存在另一个 SBC (，则会强制直接路由在接收指定代码时) 如果 SBC 因网络或其他问题而无法进行调用，则会强制尝试另一个 SBC (。 若要了解详细信息，请参阅 [从会话边界控制器 (SBC) 接收的特定 SIP 代码的故障转移 ](direct-routing-trunk-failover-on-outbound-call.md)。|408, 503, 504||Int|
|否|**故障转移时间 (秒)**|FailoverTimeSeconds |设置值时，网关在设置时未响应的出站调用会路由到下一个可用中继。 如果没有其他中继，则会自动删除调用。 默认值为 10 秒。 在网络和网关响应缓慢的组织中，这可能会导致调用被不必要地丢弃。|10|数字|Int|
|否|**媒体流量的首选国家或地区**|MediaRelayRoutingLocationOverride | 不适用于直接路由。 此参数保留用于通话套餐中的托管运营商 |无|||
|否|**SBC 支持 PIDF/LO 进行紧急呼叫**|PidfloSupported|指定 SBC 是否支持针对紧急呼叫 (PIDF/LO) 的状态信息数据格式位置对象。||||
|否| - |MediaBypass|此设置指示 SBC 是否支持媒体旁路，以及是否要将其用于此 SBC。 |无|True<br/>False|Boolean|

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)

[Teams PowerShell 概览](teams-powershell-overview.md)
