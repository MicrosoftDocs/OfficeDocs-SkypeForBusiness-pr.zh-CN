---
title: 在 Skype for Business Server 中创建网络站点间策略
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 创建网络站点间策略，这些策略企业语音 Skype for Business Server 中的呼叫允许控制。
ms.openlocfilehash: 7c0ca45c691ab1ef70d3660c3d49a08c40bdd40d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093080"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="07476-103">在 Skype for Business Server 中创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="07476-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="07476-104">创建网络站点间策略，这些策略企业语音 Skype for Business Server 中的呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="07476-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="07476-105">网络站点间策略定义在站点之间具有直接 WAN 链路的站点之间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="07476-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="07476-106">只有在两个网络站点之间具有直接交叉链接时，才需要网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="07476-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="07476-107">在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。</span><span class="sxs-lookup"><span data-stu-id="07476-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="07476-108">这两个站点需要应用相应带宽策略配置文件的站点间策略。</span><span class="sxs-lookup"><span data-stu-id="07476-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="07476-109">以下示例将应用 20Mb_Link 配置文件。</span><span class="sxs-lookup"><span data-stu-id="07476-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="07476-110">创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="07476-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="07476-111">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="07476-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="07476-112">运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略，并针对具有直接交叉链接的两个站点应用相应的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="07476-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="07476-113">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="07476-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="07476-114">根据需要重复步骤 2，为具有直接交叉链接的所有网络站点对创建网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="07476-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="07476-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07476-115">See also</span></span>

[<span data-ttu-id="07476-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="07476-116">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="07476-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="07476-117">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="07476-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="07476-118">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="07476-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="07476-119">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)