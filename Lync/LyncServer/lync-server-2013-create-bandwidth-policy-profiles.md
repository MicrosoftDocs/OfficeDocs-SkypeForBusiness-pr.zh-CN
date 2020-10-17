---
title: Lync Server 2013：创建带宽策略配置文件
description: Lync Server 2013：创建带宽策略配置文件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9646657c84806bff8caef3352774cdc5ddeab862
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562328"
---
# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="47a75-103">在 Lync Server 2013 中创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="47a75-103">Create bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a75-104">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="47a75-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="47a75-p101">**“带宽策略”定义对实时音频和视频内容的带宽使用量的限制。带宽策略应用于**“带宽策略配置文件”，后者可以应用于多个网络站点以进行呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="47a75-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="47a75-107">有关应在 CAC 部署中设置的带宽限制的准则，请参阅规划文档中的在 [Lync Server 2013 中定义呼叫允许控制的要求](lync-server-2013-defining-your-requirements-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="47a75-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="47a75-108">有关使用带宽策略和策略配置文件的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="47a75-108">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="47a75-109">新 CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="47a75-109">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="47a75-110">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="47a75-110">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="47a75-111">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="47a75-111">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="47a75-112">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="47a75-112">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="47a75-113">以下过程中创建的示例策略会为音频总流量、各个音频会话、视频总流量和各个视频会话设置限制。</span><span class="sxs-lookup"><span data-stu-id="47a75-113">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="47a75-114">例如，5Mb \_ 链路带宽策略配置文件将设置以下限制：</span><span class="sxs-lookup"><span data-stu-id="47a75-114">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="47a75-115">音频限制：2,000 kbps</span><span class="sxs-lookup"><span data-stu-id="47a75-115">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="47a75-116">音频会话限制：200 kbps</span><span class="sxs-lookup"><span data-stu-id="47a75-116">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="47a75-117">视频限制：1,400 kbps</span><span class="sxs-lookup"><span data-stu-id="47a75-117">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="47a75-118">视频会话限制：700 kbps</span><span class="sxs-lookup"><span data-stu-id="47a75-118">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="47a75-p103">最小音频会话限制值为 40 kbps。最小视频会话限制值为 100 kbps。</span><span class="sxs-lookup"><span data-stu-id="47a75-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="47a75-121">使用命令行管理程序创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="47a75-121">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="47a75-122">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47a75-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="47a75-p104">对于要创建的每个带宽策略配置文件，请运行 New-CsNetworkBandwidthPolicyProfile cmdlet。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="47a75-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
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

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="47a75-125">使用 Lync Server 控制面板创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="47a75-125">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="47a75-126">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="47a75-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="47a75-127">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="47a75-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="47a75-128">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47a75-128">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="47a75-129">单击“策略配置文件”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="47a75-129">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="47a75-130">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47a75-130">Click **New**.</span></span>

5.  <span data-ttu-id="47a75-131">在“新建策略配置文件”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入带宽策略配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="47a75-131">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="47a75-132">单击“音频限制”\*\*\*\*，然后键入允许的所有音频会话组合的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="47a75-132">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="47a75-133">单击“音频会话限制”\*\*\*\*，然后键入允许的每个单独音频会话的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="47a75-133">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="47a75-134">单击“视频限制”\*\*\*\*，然后键入允许的所有视频会话组合的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="47a75-134">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="47a75-135">单击“视频会话限制”\*\*\*\*，然后键入允许的每个单独视频会话的最大 kbps 数。</span><span class="sxs-lookup"><span data-stu-id="47a75-135">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="47a75-136">（可选）单击“说明”\*\*\*\*，然后键入其他信息来说明该带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="47a75-136">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="47a75-137">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47a75-137">Click **Commit**.</span></span>

12. <span data-ttu-id="47a75-138">要完成为拓扑创建带宽策略配置文件，请为其他带宽策略配置文件的设置重复步骤 4 至步骤 11。</span><span class="sxs-lookup"><span data-stu-id="47a75-138">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

