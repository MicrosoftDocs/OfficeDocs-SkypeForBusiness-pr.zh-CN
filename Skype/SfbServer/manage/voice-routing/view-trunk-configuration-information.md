---
title: 在 Skype for Business 服务器中查看中继配置信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274868"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>在 Skype for Business 服务器中查看中继配置信息

SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。

- 是否在中继上启用媒体旁路功能。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个主干上是否需要安全的实时协议 (SRTP) 加密。

安装 Skype for Business 服务器时, 将为你创建一个全局 SIP 中继配置设置集合。 此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。

**使用 "Skype for Business 服务器" 控制面板查看 SIP 中继配置信息**

1. 在 "Skype for Business 服务器" 控制面板中, 单击 "**语音路由**", 然后单击 "**中继配置**"。
2. 在 "**中继配置**" 选项卡上, 你将看到所有中继配置设置集合的列表;对于每个集合, 你将看到 "**名称**"、"**作用域**"、"**状态**" 和 "**媒体绕过**" 属性的值, 以及**PSTN 使用**次数、**呼叫号码规则**和已**命名的号码规则**关联与集合一起提供。 若要查看有关主干配置设置集合的其他详细信息, 请单击感兴趣的集合, 单击 "**编辑**", 然后单击 "**显示详细信息**"。 请注意, 每次只能查看一个主干配置设置集合的详细信息。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看 SIP 中继配置信息

可以使用 Skype for Business Server PowerShell 和 New-cstrunkconfiguration cmdlet 查看 SIP 中继配置设置。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从远程会话 Windows PowerShell 运行。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" http://go.microsoft.com/fwlink/p/?linkId=255876。 替换或删除此链接。


**查看 SIP 中继配置信息**

若要查看有关所有 SIP 中继配置设置的信息, 请在 Skype for Business Server 命令行管理程序中键入以下命令, 然后按 ENTER:

`Get-CsTrunkConfiguration`

这将返回与以下类似的信息：

```
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
有关详细信息, 请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。



