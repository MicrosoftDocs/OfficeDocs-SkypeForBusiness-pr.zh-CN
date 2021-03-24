---
title: 查看有关 Skype for Business Server 中单个 SIP 中继的信息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 摘要：了解如何在 Skype for Business Server 中查看有关 SIP 中继的信息。
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103228"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="4ae9f-103">查看有关 Skype for Business Server 中单个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4ae9f-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="4ae9f-104">**摘要：** 了解如何在 Skype for Business Server 中查看有关 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="4ae9f-105">SIP 中继用于将 Skype for Business Server Voice over IP 电话网络与公用电话交换网 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4ae9f-106">在该产品的以前版本中，中继用于将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关限制为一个中继。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="4ae9f-107">因此，PSTN 网关和 SIP 中继基本相同。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="4ae9f-108">对于管理员，这意味着他们只需查看有关关联的 PSTN 网关的信息，就可以查看有关单个 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="4ae9f-109">但是，在 Skype for Business Server 中，现在可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不再相同。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="4ae9f-110">反过来，这意味着管理员必须使用新的 [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet 才能查看有关单个 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="4ae9f-110">In turn, that means that administrators must use the new [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="4ae9f-111">查看所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4ae9f-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="4ae9f-112">以下命令返回有关组织使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="4ae9f-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="4ae9f-113">查看特定 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4ae9f-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="4ae9f-114">此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="4ae9f-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="4ae9f-115">查看分配给池的所有 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="4ae9f-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="4ae9f-116">此示例返回分配给池池的所有 SIP 中继 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="4ae9f-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```