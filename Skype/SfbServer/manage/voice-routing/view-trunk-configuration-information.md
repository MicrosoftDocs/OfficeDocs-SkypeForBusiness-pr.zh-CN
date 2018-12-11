---
title: 查看中 Skype 业务服务器的中继配置信息
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。
ms.openlocfilehash: 9d4890cd70256c6f063653a29d5d41f6e5a301cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222714"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>查看中 Skype 业务服务器的中继配置信息

SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。

- 是否在中继上启用媒体旁路功能。
- 在其下发送实时传输控制协议 (RTCP) 数据包的条件。
- 是否每个中继上是否需要安全实时协议 (SRTP) 加密。

在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。

**使用 Skype 业务 Server 控制面板查看 SIP 中继配置信息**

1. 在业务 Server 控制面板的 Skype，单击**语音路由**，，然后单击**Trunk 配置**。
2. 在**Trunk 配置**选项卡中，您将看到所有中继配置设置集合; 的列表对于每个集合，您将看到**名称**、**范围**、**状态**和**媒体绕过**属性值，以及**PSTN 用法**、**呼叫号码规则**，和**调用号码规则**关联的数目使用集合。 要查看有关的中继配置设置集合的其他详细信息，请单击感兴趣的集合，单击**编辑**，然后单击**显示详细信息**。 请注意，您可以查看一个集合的中继配置设置一次仅的详细的信息。

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 查看 SIP 中继配置信息

SIP 中继配置设置可以查看使用的业务 Server PowerShell 和 Get-cstrunkconfiguration cmdlet Skype。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅 Lync Server Windows PowerShell 博客文章"快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell" http://go.microsoft.com/fwlink/p/?linkId=255876。 替换或删除此链接。


**若要查看 SIP 中继配置信息**

若要查看有关所有 SIP 中继配置设置的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:

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
有关详细信息，请参阅[Get-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。



