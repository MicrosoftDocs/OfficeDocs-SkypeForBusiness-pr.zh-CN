---
title: 在 Skype for Business 服务器中创建网络站点间策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 创建网络间策略，这些策略由 Skype for Business 服务器中的 "企业语音呼叫许可控制" 使用。
ms.openlocfilehash: f24d0ad289d9388c45a5dbd9a31aa60e8c41e357
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767915"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="a6d71-103">在 Skype for Business 服务器中创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="a6d71-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="a6d71-104">创建网络间策略，这些策略由 Skype for Business 服务器中的 "企业语音呼叫许可控制" 使用。</span><span class="sxs-lookup"><span data-stu-id="a6d71-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="a6d71-105">网络站点间策略定义其间具有直接 WAN 链路的站点间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="a6d71-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a6d71-106">只有当两个网络站点之间有直接交叉链接时，*才*需要网络间策略。</span><span class="sxs-lookup"><span data-stu-id="a6d71-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="a6d71-p101">在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。这两个站点需要可应用相应带宽策略配置文件的站点间策略。以下示例将应用 20Mb_Link 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a6d71-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="a6d71-110">创建网络站点间策略</span><span class="sxs-lookup"><span data-stu-id="a6d71-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="a6d71-111">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6d71-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a6d71-p102">运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略并为两个具有直接交叉链接的站点应用相应的带宽策略配置文件。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="a6d71-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="a6d71-114">根据需要重复步骤 2，以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="a6d71-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6d71-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6d71-115">See also</span></span>

[<span data-ttu-id="a6d71-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a6d71-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a6d71-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a6d71-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a6d71-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a6d71-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a6d71-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a6d71-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
