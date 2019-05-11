---
title: 创建带宽策略配置文件中 Skype 业务服务器
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 创建或修改带宽策略，使用 Skype 中的企业语音呼叫允许控制业务服务器。
ms.openlocfilehash: 2ffb7699593c6c7790e37f57e7cce6d1779f0c16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892991"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="ec31e-103">创建带宽策略配置文件中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="ec31e-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="ec31e-104">创建或修改带宽策略，使用 Skype 中的企业语音呼叫允许控制业务服务器。</span><span class="sxs-lookup"><span data-stu-id="ec31e-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ec31e-105">“带宽策略”定义对实时音频和视频内容的带宽使用量的限制。</span><span class="sxs-lookup"><span data-stu-id="ec31e-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="ec31e-106">带宽策略是应用的 tobandwidth 策略配置文件，它们可以应用于的呼叫允许控制的多个网络站点。</span><span class="sxs-lookup"><span data-stu-id="ec31e-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="ec31e-107">有关哪些带宽限制的准则应 CAC 部署中设置，请参阅[Plan for Business Server 的 Skype 中的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ec31e-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="ec31e-p102">以下过程中创建的示例策略会为音频总流量、各个音频会话、视频总流量和各个视频会话设置限制。例如，5Mb_Link 带宽策略配置文件将设置以下限制：</span><span class="sxs-lookup"><span data-stu-id="ec31e-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="ec31e-110">音频限制：2,000 kbps</span><span class="sxs-lookup"><span data-stu-id="ec31e-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="ec31e-111">音频会话限制：200 kbps</span><span class="sxs-lookup"><span data-stu-id="ec31e-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="ec31e-112">视频限制：1,400 kbps</span><span class="sxs-lookup"><span data-stu-id="ec31e-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="ec31e-113">视频会话限制：700 kbps</span><span class="sxs-lookup"><span data-stu-id="ec31e-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="ec31e-p103">最小音频会话限制值为 40 kbps。最小视频会话限制值为 100 kbps。</span><span class="sxs-lookup"><span data-stu-id="ec31e-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ec31e-116">使用 Skype 业务 Server 命令行管理程序创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="ec31e-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ec31e-117">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec31e-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ec31e-118">对于要创建的每个带宽策略配置文件，请运行 New-CsNetworkBandwidthPolicyProfile cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ec31e-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="ec31e-119">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="ec31e-119">For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ec31e-120">使用 Skype 业务 Server 控制面板创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="ec31e-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ec31e-121">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="ec31e-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ec31e-122">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec31e-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ec31e-123">单击“策略配置文件”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ec31e-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="ec31e-124">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ec31e-124">Click **New**.</span></span>
    
5. <span data-ttu-id="ec31e-125">在“新建策略配置文件”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入带宽策略配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ec31e-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="ec31e-126">单击“音频限制”\*\*\*\*，然后键入允许的所有音频会话组合的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="ec31e-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="ec31e-127">单击“音频会话限制”\*\*\*\*，然后键入允许的每个单独音频会话的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="ec31e-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="ec31e-128">单击“视频限制”\*\*\*\*，然后键入允许的所有视频会话组合的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="ec31e-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="ec31e-129">单击“视频会话限制”\*\*\*\*，然后键入允许的每个单独视频会话的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="ec31e-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="ec31e-130">（可选）单击“说明”\*\*\*\*，然后键入其他信息来说明该带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="ec31e-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="ec31e-131">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="ec31e-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="ec31e-132">要完成为拓扑创建带宽策略配置文件，请为其他带宽策略配置文件的设置重复步骤 4 至步骤 11。</span><span class="sxs-lookup"><span data-stu-id="ec31e-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ec31e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec31e-133">See also</span></span>

[<span data-ttu-id="ec31e-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ec31e-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ec31e-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ec31e-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ec31e-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ec31e-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ec31e-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ec31e-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
