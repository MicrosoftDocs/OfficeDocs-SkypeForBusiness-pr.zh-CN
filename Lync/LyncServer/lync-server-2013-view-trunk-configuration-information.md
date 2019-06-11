---
title: 'Lync Server 2013: 查看中继配置信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf496382ed33b95e8de9f387a8623fb0984ed28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看中继配置信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 这些设置可执行如下所指定内容的操作：

  - 是否在中继上启用媒体旁路功能。

  - 发送实时传输控制协议 (RTCP) 数据包的条件。

  - 每个主干上是否需要安全的实时协议 (SRTP) 加密。

安装 Microsoft Lync Server 2013 时, 将为你创建一个全局 SIP 中继配置设置集合。 此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 查看 SIP 中继配置信息

1.  在 "Lync Server 控制面板" 中, 单击 "**语音路由**", 然后单击 "**中继配置**"。

2.  在 "**中继配置**" 选项卡上, 你将看到所有中继配置设置集合的列表;对于每个集合, 你将看到 "**名称**"、"**作用域**"、"**状态**" 和 "**媒体绕过**" 属性的值, 以及**PSTN 使用**次数、**呼叫号码规则**和已**命名的号码规则**关联与集合一起提供。 若要查看有关主干配置设置集合的其他详细信息, 请单击感兴趣的集合, 单击 "**编辑**", 然后单击 "**显示详细信息**"。 请注意, 每次只能查看一个主干配置设置集合的详细信息。

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 SIP 中继配置信息

可以使用 Lync Server PowerShell 和 New-cstrunkconfiguration cmdlet 查看 SIP 中继配置设置。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从远程会话 Windows PowerShell 运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>查看 SIP 中继配置信息

  - 若要查看有关所有 SIP 中继配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
        Get-CsTrunkConfiguration
    
    这将返回与以下类似的信息：
    
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

</div>

有关详细信息, 请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

