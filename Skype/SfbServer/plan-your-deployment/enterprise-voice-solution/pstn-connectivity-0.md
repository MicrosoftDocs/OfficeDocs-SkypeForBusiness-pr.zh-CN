---
title: 在 Skype for Business 服务器中规划 PSTN 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 Skype for business 服务器的企业语音中规划 PSTN 连接。
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802542"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="d7a5c-103">在 Skype for Business 服务器中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="d7a5c-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="d7a5c-104">在 Skype for business 服务器的企业语音中规划 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="d7a5c-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="d7a5c-105">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7a5c-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="d7a5c-106">发出和接收呼叫的用户不应知道基础技术：从用户的角度看，企业语音基础结构和 PSTN 之间的通话似乎只是另一次电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7a5c-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="d7a5c-107">Skype for business 服务器通过使用以下选项提供可靠、可扩展的 PSTN 连接：</span><span class="sxs-lookup"><span data-stu-id="d7a5c-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="d7a5c-108">到 Internet 电话服务提供商 (ITSP) 的 **SIP 中继**</span><span class="sxs-lookup"><span data-stu-id="d7a5c-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="d7a5c-109">到 PSTN 网关的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="d7a5c-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="d7a5c-110">到 PBX 的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="d7a5c-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="d7a5c-p102">根据企业规模、地理范围和现有语音基础结构，企业可能会在不同位置使用一个、两个甚至所有三个选项。有关详细信息，请参阅以下几节。</span><span class="sxs-lookup"><span data-stu-id="d7a5c-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d7a5c-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="d7a5c-113">In this section</span></span>

- [<span data-ttu-id="d7a5c-114">Skype for Business 服务器中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="d7a5c-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="d7a5c-115">Skype for Business 服务器中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="d7a5c-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="d7a5c-116">Skype for Business 服务器中的 M:N 主干</span><span class="sxs-lookup"><span data-stu-id="d7a5c-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="d7a5c-117">Skype for Business 服务器中的翻译规则</span><span class="sxs-lookup"><span data-stu-id="d7a5c-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="d7a5c-118">Skype for business 服务器中的出站语音路由计划</span><span class="sxs-lookup"><span data-stu-id="d7a5c-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

