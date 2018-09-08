---
title: 规划业务服务器中 Skype 的 PSTN 连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 规划 Business Server Skype 中的企业语音中的 PSTN 连接。
ms.openlocfilehash: 0c84cc1c683f55ab003164f845071c071c620adc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881823"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="77708-103">规划业务服务器中 Skype 的 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="77708-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="77708-104">规划 Business Server Skype 中的企业语音中的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="77708-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="77708-105">企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="77708-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="77708-106">发起和接收呼叫的用户应不必了解底层技术： 从用户的角度来看，企业语音基础结构与 PSTN 之间的呼叫应该就像是另一个电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="77708-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="77708-107">Skype 业务服务器通过以下选项提供可靠且可扩展的 PSTN 连接：</span><span class="sxs-lookup"><span data-stu-id="77708-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="77708-108">到 Internet 电话服务提供商 (ITSP) 的 **SIP 中继**</span><span class="sxs-lookup"><span data-stu-id="77708-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="77708-109">到 PSTN 网关的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="77708-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="77708-110">到 PBX 的**直接 SIP 连接**</span><span class="sxs-lookup"><span data-stu-id="77708-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="77708-p102">根据企业规模、地理范围和现有语音基础结构，企业可能会在不同位置使用一个、两个甚至所有三个选项。有关详细信息，请参阅以下几节。</span><span class="sxs-lookup"><span data-stu-id="77708-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="77708-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="77708-113">In this section</span></span>

- [<span data-ttu-id="77708-114">Skype 业务服务器中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="77708-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="77708-115">Skype 中的业务服务器的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="77708-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="77708-116">Skype 业务服务器中的 M:N 中继</span><span class="sxs-lookup"><span data-stu-id="77708-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="77708-117">Skype 业务服务器中的转换规则</span><span class="sxs-lookup"><span data-stu-id="77708-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="77708-118">规划出站语音路由中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="77708-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

