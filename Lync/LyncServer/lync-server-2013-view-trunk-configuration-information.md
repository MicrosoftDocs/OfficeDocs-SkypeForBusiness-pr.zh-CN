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

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="0c5fe-102">在 Lync Server 2013 中查看中继配置信息</span><span class="sxs-lookup"><span data-stu-id="0c5fe-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c5fe-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0c5fe-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0c5fe-104">SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="0c5fe-105">这些设置可执行如下所指定内容的操作：</span><span class="sxs-lookup"><span data-stu-id="0c5fe-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="0c5fe-106">是否在中继上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="0c5fe-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="0c5fe-108">每个主干上是否需要安全的实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="0c5fe-109">安装 Microsoft Lync Server 2013 时, 将为你创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="0c5fe-110">此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="0c5fe-111">使用 Lync Server "控制面板" 查看 SIP 中继配置信息</span><span class="sxs-lookup"><span data-stu-id="0c5fe-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0c5fe-112">在 "Lync Server 控制面板" 中, 单击 "**语音路由**", 然后单击 "**中继配置**"。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="0c5fe-113">在 "**中继配置**" 选项卡上, 你将看到所有中继配置设置集合的列表;对于每个集合, 你将看到 "**名称**"、"**作用域**"、"**状态**" 和 "**媒体绕过**" 属性的值, 以及**PSTN 使用**次数、**呼叫号码规则**和已**命名的号码规则**关联与集合一起提供。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="0c5fe-114">若要查看有关主干配置设置集合的其他详细信息, 请单击感兴趣的集合, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="0c5fe-115">请注意, 每次只能查看一个主干配置设置集合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c5fe-116">使用 Windows PowerShell Cmdlet 查看 SIP 中继配置信息</span><span class="sxs-lookup"><span data-stu-id="0c5fe-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0c5fe-117">可以使用 Lync Server PowerShell 和 New-cstrunkconfiguration cmdlet 查看 SIP 中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="0c5fe-118">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从远程会话 Windows PowerShell 运行。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="0c5fe-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="0c5fe-120">查看 SIP 中继配置信息</span><span class="sxs-lookup"><span data-stu-id="0c5fe-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="0c5fe-121">若要查看有关所有 SIP 中继配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="0c5fe-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="0c5fe-122">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="0c5fe-122">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="0c5fe-123">有关详细信息, 请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0c5fe-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

