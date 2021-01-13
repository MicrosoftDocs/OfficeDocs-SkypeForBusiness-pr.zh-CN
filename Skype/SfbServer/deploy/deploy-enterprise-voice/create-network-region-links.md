---
title: 在 Skype for Business Server 中创建网络区域链接
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 创建或修改网络区域链接，这些链接企业语音 Skype for Business Server 中的呼叫允许控制。
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822462"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="b1bed-103">在 Skype for Business Server 中创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="b1bed-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="b1bed-104">创建或修改网络区域链接，这些链接企业语音 Skype for Business Server 中的呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="b1bed-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="b1bed-105">网络内的区域通过物理 WAN 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="b1bed-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="b1bed-106">网络区域链接在为呼叫允许控制 (CAC) 配置的两个区域之间创建一个链接，并设置这些区域之间的音频和视频流量的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="b1bed-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="b1bed-107">示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="b1bed-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="b1bed-108">每个区域链接都受 WAN 带宽限制，如示例：收集 Skype for Business Server 中的呼叫允许控制要求的区域链接 [带宽信息表中所述](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1bed-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b1bed-109">使用 Skype for Business Server 命令行管理程序创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="b1bed-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b1bed-110">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="b1bed-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b1bed-111">运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="b1bed-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="b1bed-112">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="b1bed-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b1bed-113">使用 Skype for Business Server 控制面板创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="b1bed-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b1bed-114">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b1bed-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b1bed-115">在左侧导航栏中，单击“网络配置”。</span><span class="sxs-lookup"><span data-stu-id="b1bed-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b1bed-116">单击“区域链接”导航按钮。</span><span class="sxs-lookup"><span data-stu-id="b1bed-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="b1bed-117">单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="b1bed-117">Click **New**.</span></span>
    
5. <span data-ttu-id="b1bed-118">在“新建区域链接”页上，单击“名称”，然后键入网络区域链接的名称。</span><span class="sxs-lookup"><span data-stu-id="b1bed-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="b1bed-119">单击“网络区域 #1”，然后在列表中单击要链接到“网络区域 #2”的网络区域。</span><span class="sxs-lookup"><span data-stu-id="b1bed-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="b1bed-120">单击“网络区域 #2”，然后在列表中单击要链接到“网络区域 #1”的网络区域。</span><span class="sxs-lookup"><span data-stu-id="b1bed-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="b1bed-121">也可以选择单击“带宽策略”，然后选择要应用于网络区域链接的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="b1bed-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b1bed-122">仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。</span><span class="sxs-lookup"><span data-stu-id="b1bed-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="b1bed-123">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b1bed-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="b1bed-124">要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。</span><span class="sxs-lookup"><span data-stu-id="b1bed-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b1bed-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1bed-125">See also</span></span>

[<span data-ttu-id="b1bed-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b1bed-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b1bed-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b1bed-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b1bed-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b1bed-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b1bed-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b1bed-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
