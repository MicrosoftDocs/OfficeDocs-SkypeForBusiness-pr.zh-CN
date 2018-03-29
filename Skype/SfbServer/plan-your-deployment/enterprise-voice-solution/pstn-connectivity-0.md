---
title: 在 Skype for Business Server 2015 中规划 PSTN 连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Skype 在企业语音中的 PSTN 连接业务服务器的计划。
ms.openlocfilehash: 785dd39d4a809283ae53f7eedbe398a6271b7c5b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="bf024-103">在 Skype for Business Server 2015 中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="bf024-103">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bf024-104">Skype 在企业语音中的 PSTN 连接业务服务器的计划。</span><span class="sxs-lookup"><span data-stu-id="bf024-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf024-105">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bf024-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="bf024-106">发出和接收呼叫的用户不应注意基础技术： 企业语音基础结构和 PSTN 之间的调用应从用户的角度来看，似乎只是另一个电话。</span><span class="sxs-lookup"><span data-stu-id="bf024-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="bf024-107">Skype 业务服务器提供可靠、 可扩展的 PSTN 连接通过使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="bf024-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="bf024-108">到 Internet 电话服务提供商 (ITSP) 的 **SIP 中继**</span><span class="sxs-lookup"><span data-stu-id="bf024-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="bf024-109">到 PSTN 网关的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="bf024-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="bf024-110">到 PBX 的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="bf024-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="bf024-p102">根据企业规模、地理范围和现有语音基础结构，企业可能会在不同位置使用一个、两个甚至所有三个选项。有关详细信息，请参阅以下几节。</span><span class="sxs-lookup"><span data-stu-id="bf024-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bf024-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="bf024-113">In this section</span></span>

- [<span data-ttu-id="bf024-114">在业务服务器 2015年的 Skype 的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="bf024-114">SIP trunking in Skype for Business Server 2015</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="bf024-115">直接在 Skype 的业务服务器 2015年的 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="bf024-115">Direct SIP connections in Skype for Business Server 2015</span></span>](direct-sip.md)
    
- [<span data-ttu-id="bf024-116">在业务服务器 2015年的 Skype 的 M:N 干线</span><span class="sxs-lookup"><span data-stu-id="bf024-116">M:N trunk in Skype for Business Server 2015</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="bf024-117">在业务服务器 2015年的 Skype 的转换规则</span><span class="sxs-lookup"><span data-stu-id="bf024-117">Translation rules in Skype for Business Server 2015</span></span>](translation-rules.md)
    
- [<span data-ttu-id="bf024-118">为出站语音路由在 Skype 业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="bf024-118">Plan for outbound voice routing in Skype for Business Server 2015</span></span>](outbound-voice-routing.md)
    

