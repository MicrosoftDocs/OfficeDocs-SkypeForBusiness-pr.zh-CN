---
title: 在 Skype for Business Server 中规划 PSTN 连接
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 在 Skype for Business Server 企业语音 PSTN 连接。
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813562"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="b6947-103">在 Skype for Business Server 中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="b6947-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="b6947-104">在 Skype for Business Server 企业语音 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="b6947-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="b6947-105">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b6947-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="b6947-106">拨打和接听电话的用户不应了解基础技术：从用户的角度来看，企业语音 基础结构和 PSTN 之间的呼叫应该就像是另一个电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="b6947-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="b6947-107">Skype for Business Server 通过以下选项提供可靠、可扩展的 PSTN 连接：</span><span class="sxs-lookup"><span data-stu-id="b6947-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="b6947-108">到 Internet 电话服务提供商 (ITSP) 的 **SIP 中继**</span><span class="sxs-lookup"><span data-stu-id="b6947-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="b6947-109">到 PSTN 网关的 **直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="b6947-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="b6947-110">到 PBX 的 **直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="b6947-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="b6947-111">根据企业大小、地理范围和现有语音基础结构，企业可能会在不同位置使用一个、两个甚至所有三个选项。</span><span class="sxs-lookup"><span data-stu-id="b6947-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="b6947-112">有关这些选项的详细信息，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="b6947-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b6947-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="b6947-113">In this section</span></span>

- [<span data-ttu-id="b6947-114">Skype for Business Server 中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="b6947-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="b6947-115">Skype for Business Server 中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="b6947-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="b6947-116">Skype for Business Server 中的 M：N 中继</span><span class="sxs-lookup"><span data-stu-id="b6947-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="b6947-117">Skype for Business Server 中的转换规则</span><span class="sxs-lookup"><span data-stu-id="b6947-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="b6947-118">在 Skype for Business Server 中规划出站语音路由</span><span class="sxs-lookup"><span data-stu-id="b6947-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

