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
description: SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络（PSTN）网关、IP 公共分支 exchange （PBX）或会话边界控制器（SBC）之间的关系和能力。
ms.openlocfilehash: 8fb180994fdcd8409b0776a2fcaee6316110a36d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992549"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="f50e9-103">在 Skype for Business 服务器中查看中继配置信息</span><span class="sxs-lookup"><span data-stu-id="f50e9-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="f50e9-104">SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络（PSTN）网关、IP 公共分支 exchange （PBX）或会话边界控制器（SBC）之间的关系和能力。</span><span class="sxs-lookup"><span data-stu-id="f50e9-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="f50e9-105">是否在中继上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="f50e9-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="f50e9-106">发送实时传输控制协议（RTCP）数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="f50e9-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="f50e9-107">每个主干上是否需要安全的实时协议（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="f50e9-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f50e9-108">安装 Skype for Business 服务器时，将为你创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="f50e9-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f50e9-109">此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。</span><span class="sxs-lookup"><span data-stu-id="f50e9-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="f50e9-110">**使用 "Skype for Business 服务器" 控制面板查看 SIP 中继配置信息**</span><span class="sxs-lookup"><span data-stu-id="f50e9-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="f50e9-111">在 "Skype for Business 服务器" 控制面板中，单击 "**语音路由**"，然后单击 "**中继配置**"。</span><span class="sxs-lookup"><span data-stu-id="f50e9-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="f50e9-112">在 "**中继配置**" 选项卡上，你将看到所有中继配置设置集合的列表;对于每个集合，你将看到 "**名称**"、"**作用域**"、"**状态**" 和 "**媒体绕过**" 属性的值，以及**PSTN 用法**的数量、**调用编号规则**，以及与集合关联的已**调用编号规则**。</span><span class="sxs-lookup"><span data-stu-id="f50e9-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="f50e9-113">若要查看有关主干配置设置集合的其他详细信息，请单击感兴趣的集合，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="f50e9-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="f50e9-114">请注意，每次只能查看一个主干配置设置集合的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f50e9-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f50e9-115">使用 Windows PowerShell cmdlet 查看 SIP 中继配置信息</span><span class="sxs-lookup"><span data-stu-id="f50e9-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f50e9-116">可以使用 Skype for Business Server PowerShell 和 New-cstrunkconfiguration cmdlet 查看 SIP 中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="f50e9-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="f50e9-117">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从远程会话 Windows PowerShell 运行。</span><span class="sxs-lookup"><span data-stu-id="f50e9-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f50e9-118">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" http://go.microsoft.com/fwlink/p/?linkId=255876。</span><span class="sxs-lookup"><span data-stu-id="f50e9-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="f50e9-119">替换或删除此链接。</span><span class="sxs-lookup"><span data-stu-id="f50e9-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="f50e9-120">**查看 SIP 中继配置信息**</span><span class="sxs-lookup"><span data-stu-id="f50e9-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="f50e9-121">若要查看有关所有 SIP 中继配置设置的信息，请在 Skype for Business Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="f50e9-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="f50e9-122">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="f50e9-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="f50e9-123">有关详细信息，请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f50e9-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



