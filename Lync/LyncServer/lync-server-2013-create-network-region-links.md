---
title: Lync Server 2013：创建网络区域链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c0f21f599b8afa4f9f31ec16aad82e305c8a08e
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="78c79-102">在 Lync Server 2013 中创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="78c79-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78c79-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="78c79-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="78c79-104">网络内的区域通过物理 WAN 连接进行链接。</span><span class="sxs-lookup"><span data-stu-id="78c79-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="78c79-105">"*网络区域" 链接*在为呼叫许可控制（CAC）配置的两个区域之间创建链接，并设置这些区域之间的音频和视频流量的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="78c79-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="78c79-106">有关使用网络区域链接的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="78c79-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="78c79-107">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="78c79-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="78c79-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="78c79-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="78c79-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="78c79-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="78c79-110">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="78c79-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="78c79-111">示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。</span><span class="sxs-lookup"><span data-stu-id="78c79-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="78c79-112">其中每个区域链接均受 WAN 带宽的约束，如示例中的区域链接带宽信息表中所述：在规划文档的 " [Lync Server 2013" 部分中收集对呼叫许可控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="78c79-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="78c79-113">使用 Lync Server 命令行管理程序创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="78c79-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="78c79-114">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="78c79-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="78c79-115">运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="78c79-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="78c79-116">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="78c79-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="78c79-117">使用 Lync Server "控制面板" 创建网络区域链接</span><span class="sxs-lookup"><span data-stu-id="78c79-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="78c79-118">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="78c79-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="78c79-119">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="78c79-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="78c79-120">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78c79-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="78c79-121">单击“区域链接”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="78c79-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="78c79-122">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78c79-122">Click **New**.</span></span>

5.  <span data-ttu-id="78c79-123">在“新建区域链接”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入网络区域链接的名称。</span><span class="sxs-lookup"><span data-stu-id="78c79-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="78c79-124">单击 "**网络\#区域 1**"，然后在列表中单击要链接到 "网络区域\#2" 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="78c79-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="78c79-125">单击 "**网络\#区域 2**"，然后在列表中单击要链接到 "网络区域\#1" 的网络区域。</span><span class="sxs-lookup"><span data-stu-id="78c79-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="78c79-126">也可以选择单击“带宽策略”\*\*\*\*，然后选择要应用于网络区域链接的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="78c79-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="78c79-127">仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。</span><span class="sxs-lookup"><span data-stu-id="78c79-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="78c79-128">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="78c79-128">Click **Commit**.</span></span>

10. <span data-ttu-id="78c79-129">要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。</span><span class="sxs-lookup"><span data-stu-id="78c79-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
