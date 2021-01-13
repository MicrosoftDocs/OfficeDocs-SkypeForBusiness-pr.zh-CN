---
title: 在 Skype for Business Server 中查看中继配置信息
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
description: SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826162"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="cd1cf-103">在 Skype for Business Server 中查看中继配置信息</span><span class="sxs-lookup"><span data-stu-id="cd1cf-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="cd1cf-104">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="cd1cf-105">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="cd1cf-106">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="cd1cf-107">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="cd1cf-108">安装 Skype for Business Server 时，将创建 SIP 中继配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="cd1cf-109">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="cd1cf-110">**使用 Skype for Business Server 控制面板查看 SIP 中继配置信息**</span><span class="sxs-lookup"><span data-stu-id="cd1cf-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="cd1cf-111">在 Skype for Business Server 控制面板中，单击 **"语音路由**"，然后单击 **"中继配置"。**</span><span class="sxs-lookup"><span data-stu-id="cd1cf-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="cd1cf-112">在 **"中继配置**"选项卡上，你将看到所有中继配置设置集合的列表;对于每个集合，你将看到名称、范围、状态和媒体旁路属性的值，以及与集合关联的 **PSTN** 用法、呼叫号码规则和被叫号码规则的数量。 </span><span class="sxs-lookup"><span data-stu-id="cd1cf-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="cd1cf-113">要查看有关中继配置设置集合的其他详细信息，请单击有兴趣的集合，单击“编辑”，再单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="cd1cf-114">请注意，一次仅可查看中继配置设置的一个集合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cd1cf-115">使用 cmdlet 查看 SIP 中继Windows PowerShell信息</span><span class="sxs-lookup"><span data-stu-id="cd1cf-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cd1cf-116">可以使用 Skype for Business Server PowerShell 和 Get-CsTrunkConfiguration cmdlet 查看 SIP 中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="cd1cf-117">此 cmdlet 可以从 Skype for Business Server 命令行管理程序或远程会话命令行管理程序Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="cd1cf-118">有关使用远程 Windows PowerShell 连接到 Skype for Business Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章"快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。 https://go.microsoft.com/fwlink/p/?linkId=255876</span><span class="sxs-lookup"><span data-stu-id="cd1cf-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="cd1cf-119">替换或删除此链接。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="cd1cf-120">**查看 SIP 中继配置信息**</span><span class="sxs-lookup"><span data-stu-id="cd1cf-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="cd1cf-121">若要查看有关所有 SIP 中继配置设置的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="cd1cf-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="cd1cf-122">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="cd1cf-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="cd1cf-123">有关详细信息，请参阅 [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cd1cf-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



