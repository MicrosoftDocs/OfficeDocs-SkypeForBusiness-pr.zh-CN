---
title: 在服务器中查看中继Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。
ms.openlocfilehash: b7623765f8d1341066fd127e82c89ab1fa14c79c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843825"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>在服务器中查看中继Skype for Business Server

SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。

- 是否应对中继启用媒体旁路。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个中继上是否需要安全实时协议 (SRTP) 加密。

在安装Skype for Business Server时，将创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。

**使用控制面板查看 SIP 中继Skype for Business Server信息**

1. 在"Skype for Business Server控制面板"中，单击"**语音路由**"，然后单击"**中继配置"。**
2. 在 **"Trunk 配置**"选项卡上，你将看到所有中继配置设置集合的列表;对于每个集合，你将看到名称、范围、**状态** 和媒体旁路属性的值，以及与集合关联的 **PSTN** 用法、呼叫号码规则和被叫号码规则的数量。  要查看有关中继配置设置集合的其他详细信息，请单击有兴趣的集合，单击“编辑”，再单击“显示详细信息”。 请注意，一次仅可查看中继配置设置的一个集合的详细信息。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看 SIP 中继Windows PowerShell信息

SIP 中继配置设置可通过使用 Skype for Business Server PowerShell 和 Get-CsTrunkConfiguration cmdlet 进行查看。 可以从命令行管理程序或远程会话Skype for Business Server cmdlet 运行Windows PowerShell。 有关使用远程 Windows PowerShell 连接到 Skype for Business Server 的详细信息，请参阅 位于 的 Lync Server Windows PowerShell 博客文章"快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。 https://go.microsoft.com/fwlink/p/?linkId=255876 替换或删除此链接。


**查看 SIP 中继配置信息**

若要查看有关所有 SIP 中继配置设置的信息，请在命令行管理程序中键入Skype for Business Server命令，然后按 Enter：

```powershell
Get-CsTrunkConfiguration
```

这将返回与以下类似的信息：

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
有关详细信息，请参阅 [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。