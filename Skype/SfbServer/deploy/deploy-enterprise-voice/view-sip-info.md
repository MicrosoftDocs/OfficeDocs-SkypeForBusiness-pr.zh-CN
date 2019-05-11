---
title: 查看 Business server Skype 中的单个 SIP 中继的信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 摘要： 了解如何为业务服务器在 Skype 中查看有关 SIP 中继的信息。
ms.openlocfilehash: a7cf290bf245092e08babcaa86c642dd0f0a4265
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892235"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="1581d-103">查看 Business server Skype 中的单个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="1581d-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="1581d-104">**摘要：** 了解如何为业务服务器在 Skype 中查看有关 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="1581d-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="1581d-105">SIP 中继用于通过 IP 电话网络与公共公用电话交换网 (PSTN) 的业务 Server 语音连接 Skype。</span><span class="sxs-lookup"><span data-stu-id="1581d-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1581d-106">在本产品的以前版本中，中继用来将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关仅限于一个中继。</span><span class="sxs-lookup"><span data-stu-id="1581d-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="1581d-107">因此，PSTN 网关和 SIP 中继基本上完全相同。</span><span class="sxs-lookup"><span data-stu-id="1581d-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="1581d-108">对于管理员而言，这意味着他们只需通过查看有关相关联的 PSTN 网关的信息，即可查看有关个别 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="1581d-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="1581d-109">在业务服务器 Skype，但是，多个中继可以现在将分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。</span><span class="sxs-lookup"><span data-stu-id="1581d-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="1581d-110">而这意味着管理员必须使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet，才能查看有关个别 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="1581d-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="1581d-111">查看所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="1581d-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="1581d-112">以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="1581d-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="1581d-113">查看特定 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="1581d-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="1581d-114">此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="1581d-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="1581d-115">查看分配给池的所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="1581d-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="1581d-116">在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="1581d-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
