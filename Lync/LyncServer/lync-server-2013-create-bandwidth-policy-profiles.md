---
title: Lync Server 2013：创建带宽策略配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69aa99d94843c6daa1483911325d45ede0a39f4a
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="30906-102">在 Lync Server 2013 中创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="30906-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30906-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="30906-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="30906-p101">“带宽策略”\*\* 定义对实时音频和视频内容的带宽使用量的限制。带宽策略应用于“带宽策略配置文件”\*\*，后者可以应用于多个网络站点以进行呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="30906-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="30906-106">有关应在 CAC 部署中设置哪些带宽限制的指南，请参阅计划文档中的在[Lync Server 2013 中定义呼叫许可控制的要求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="30906-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="30906-107">有关使用带宽策略和策略配置文件的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="30906-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="30906-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="30906-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="30906-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="30906-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="30906-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="30906-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="30906-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="30906-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="30906-112">以下过程中创建的示例策略会为音频总流量、各个音频会话、视频总流量和各个视频会话设置限制。</span><span class="sxs-lookup"><span data-stu-id="30906-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="30906-113">例如，5Mb\_链接带宽策略配置文件设置以下限制：</span><span class="sxs-lookup"><span data-stu-id="30906-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="30906-114">音频限制：2,000 kbps</span><span class="sxs-lookup"><span data-stu-id="30906-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="30906-115">音频会话限制：200 kbps</span><span class="sxs-lookup"><span data-stu-id="30906-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="30906-116">视频限制：1,400 kbps</span><span class="sxs-lookup"><span data-stu-id="30906-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="30906-117">视频会话限制：700 kbps</span><span class="sxs-lookup"><span data-stu-id="30906-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="30906-p103">最小音频会话限制值为 40 kbps。最小视频会话限制值为 100 kbps。</span><span class="sxs-lookup"><span data-stu-id="30906-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="30906-120">使用命令行管理程序创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="30906-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="30906-121">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="30906-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="30906-122">对于要创建的每个带宽策略配置文件，请运行 New-CsNetworkBandwidthPolicyProfile cmdlet。</span><span class="sxs-lookup"><span data-stu-id="30906-122">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="30906-123">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="30906-123">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="30906-124">使用 Lync Server "控制面板" 创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="30906-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="30906-125">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="30906-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30906-126">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="30906-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="30906-127">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30906-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="30906-128">单击“策略配置文件”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="30906-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="30906-129">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="30906-129">Click **New**.</span></span>

5.  <span data-ttu-id="30906-130">在“新建策略配置文件”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入带宽策略配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="30906-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="30906-131">单击“音频限制”\*\*\*\*，然后键入允许的所有音频会话组合的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="30906-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="30906-132">单击“音频会话限制”\*\*\*\*，然后键入允许的每个单独音频会话的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="30906-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="30906-133">单击“视频限制”\*\*\*\*，然后键入允许的所有视频会话组合的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="30906-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="30906-134">单击“视频会话限制”\*\*\*\*，然后键入允许的每个单独视频会话的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="30906-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="30906-135">（可选）单击“说明”\*\*\*\*，然后键入其他信息来说明该带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="30906-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="30906-136">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="30906-136">Click **Commit**.</span></span>

12. <span data-ttu-id="30906-137">要完成为拓扑创建带宽策略配置文件，请为其他带宽策略配置文件的设置重复步骤 4 至步骤 11。</span><span class="sxs-lookup"><span data-stu-id="30906-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

