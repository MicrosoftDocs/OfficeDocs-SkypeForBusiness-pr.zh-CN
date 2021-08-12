---
title: Skype for Business Server：创建新的中继配置设置集合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: SIP 中继配置设置定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系。
ms.openlocfilehash: 4e9e6164b7776181b85478c5d420f0bf5e296ac4c02fc23494c5af8808474566
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849937"
---
# <a name="skype-for-business-server-create-a-new-collection-of-trunk-configuration-settings"></a>Skype for Business Server：创建新的中继配置设置集合

SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：
- 是否应对中继启用媒体旁路。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个中继上是否需要安全实时协议 (SRTP) 加密。

在安装Skype for Business Server时，将创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。

使用Skype for Business Server 控制面板创建 SIP 中继配置设置时，可以使用以下选项：

|UI 设置 | PowerShell 参数 | 说明 |
|--|--|--|
|Name|标识|集合的唯一标识符。此属性为只读；您无法更改中继配置设置集合的标识。|
|说明|说明|为管理员提供了存储有关设置的附加信息（例如，中继配置的用途）的方法。|
|支持的最大早期对话数|MaxEarlyDialogs|服务提供商的 PSTN 网关、IP-PBX 或 SBC 可以接收的分叉响应的最大数目，这些响应是针对发送到中介服务器的邀请的。|
|加密支持级别|SRTPMode|指示用于保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量的支持级别。 对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。 媒体配置是使用 [New-CsMediaConfiguration](/powershell/module/skype/New-CsMediaConfiguration) 和 [Set-CsMediaConfiguration](/powershell/module/skype/Set-CsMediaConfiguration) cmdlet 设置的。<br/>允许的值包括：<br/><br/>**必需**：必须使用 SRTP 加密。<br/>**可选**：如果网关支持 SRTP，则使用 SRTP。<br/>**不支持**：不支持 SRTP 加密，因此不会使用。<br/><br/>仅当网关配置为使用传输层安全性 (TLS) 时，才会使用 SRTPMode。如果将网关配置为使用传输控制协议 (TCP)，则 SRTPMode 会在内部设置为“Not Supported”。|
|引用支持|Enable3pccRefer<br/>EnableReferSupport|如果设置为“允许将引用发送到网关”，则指示中继支持接收来自中介服务器的引用请求。<br/>如果设置为“允许使用第三方呼叫控制的引用”，则指示 3pcc 协议可用于允许转接的呼叫绕过宿主网站。3pcc 也称为“第三方协议”，当使用第三方连接一对呼叫者时将会出现（例如，运营商发出从人员 A 到人员 B 的呼叫）。|
|启用媒体旁路|EnableBypass|指示是否为此中继启用媒体旁路。仅当启用了“集中式媒体处理”时才能启用媒体旁路。|
|集中式媒体处理|Topology|指示是否有已知的媒体终结点。（例如，PSTN 网关就是一个已知的媒体端点，其中媒体终端与信号终端具有相同的 IP。）|
|启用 RTP 闭锁|EnableRTPLatching|指示 SIP 中继是否支持 RTP 闭锁。RTP 闭锁是一种通过 NAT（网络地址转换器）设备或防火墙实现 RTP/RTCP 连接的技术。|
|启用呼叫转移历史记录|ForwardCallHistory|指示是否通过中继转移呼叫历史记录信息。|
|启用转移 P-Asserted-Identity 数据|ForwardPAI|指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。PAI 标头提供了一种验证呼叫者身份的方法。|
|启用出站路由故障转移计时器|EnableFastFailoverTimer|指示是否将网关在 10 秒内未应答的出站呼叫路由到下一个可用中继；如果没有任何其他中继，则将自动放弃呼叫。在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。|
|关联的 PSTN 用法|PSTNUsages|分配给中继的 PSTN 用法的集合。|
|要测试的已转换号码|不适用|可用于对中继配置设置执行临时测试的电话号码。|
|关联的转换规则|OutboundTranslationRulesList|应用于出站路由处理的呼叫（路由到 PBX 或 PSTN 目标的呼叫）的电话号码转换规则的集合。|
|被叫号码转换规则|OutboundCallingNumberTranslationRulesList|分配给中继的出站主叫号码转换规则的集合。|
|要测试的电话号码|不适用|可用于对转换规则执行临时测试的电话号码。|
|主叫号码|不适用|可用于对转换规则执行临时测试的电话号码。|
|被叫号码|不适用|指示要测试的电话号码是被呼叫的人员的电话号码。|
||||

> [!Note]
> CsTrunkConfiguration cmdlet Skype for Business Server支持控制面板中未Skype for Business Server属性。 有关详细信息，请参阅 [New-CsTrunkConfiguration](/powershell/module/skype/New-CsTrunkConfiguration) cmdlet 的帮助主题。 

**使用控制面板创建新的中继Skype for Business Server设置**

1. 在"Skype for Business Server控制面板"中，单击"**语音路由**"，然后单击"**中继配置"。**
2. 在“Trunk 配置”选项卡上，单击“新建”，然后单击“站点 Trunk”以创建站点作用域的新设置，或“池 Trunk”创建服务作用域的新设置。
3. 在"选择站点"或"选择服务"对话框中 (出现的对话框将取决于是创建站点范围的设置还是服务范围的设置) ，选择新配置设置的位置，然后单击"确定 **"。** 如果对话框为空，这意味着没有位置创建新设置;例如，如果"选择站点"对话框为空，则意味着所有站点已分配有中继配置站点的集合，并且每个站点 (和每个服务) 只能承载一个此类集合。 在此情况下，您可删除现有集合并创建新的集合，或只修改现有集合。
4. 在“新建 Trunk 配置”对话框中，进行适当的选择，然后单击“确定”。
5. 集合的“状态”属性将更新为“未提交”。若要提交更改和删除集合，请单击“提交”，然后单击“全部提交”。
6. 在“未提交的语音配置设置”对话框中，单击“确定”。
7. 在 **"Skype for Business控制面板**"对话框中，单击"确定 **"。**
