---
title: Lync Server 2013：配置网络站点链接
description: Lync Server 2013：配置网络站点链接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68b4ecce15b8f3ba5a5717c73a8f97f8a0633b58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572928"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="f1851-103">在 Lync Server 2013 中配置网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f1851-103">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1851-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f1851-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f1851-105">在呼叫允许控制 (CAC) 配置中，可以创建定义直接链接的站点之间的带宽限制的网络站点间策略。</span><span class="sxs-lookup"><span data-stu-id="f1851-105">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="f1851-106">当两个网络站点共享一条直接链接时，可定义这两个站点之间的音频和视频连接的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f1851-106">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="f1851-107">您不能使用 Lync Server 控制面板配置网络站点策略，这只能通过使用 Lync Server 命令行管理程序中的 cmdlet 来实现。</span><span class="sxs-lookup"><span data-stu-id="f1851-107">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="f1851-108">您可以从 Lync Server 命令行管理程序中创建、修改和删除网络站点链接 (也称为网络站点间策略) 。</span><span class="sxs-lookup"><span data-stu-id="f1851-108">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="f1851-109">创建网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f1851-109">To create a network site link</span></span>

1.  <span data-ttu-id="f1851-110">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="f1851-110">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f1851-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f1851-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1851-112">在命令提示符处，键入以下命令，取代有效的配置值：</span><span class="sxs-lookup"><span data-stu-id="f1851-112">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="f1851-113">本示例创建一个名为里诺的新网络站点链接 \_ ，用于设置里诺和新的网络站点之间的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="f1851-113">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="f1851-114">运行此命令之前，必须已存在网络站点和带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="f1851-114">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="f1851-115">有关参数的详细说明，请参阅 Lync Server 命令行管理程序文档中的 [new-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="f1851-115">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="f1851-116">要检索可应用于网络站点链接的带宽策略配置文件列表，请调用 **Get-CsNetworkBandwidthPolicyProfile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f1851-116">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="f1851-117">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。</span><span class="sxs-lookup"><span data-stu-id="f1851-117">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="f1851-118">修改网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f1851-118">To modify a network site link</span></span>

1.  <span data-ttu-id="f1851-119">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="f1851-119">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f1851-120">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f1851-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1851-121">使用 **Set-CsNetworkInterSitePolicy** cmdlet 修改给定网络站点链接的属性。</span><span class="sxs-lookup"><span data-stu-id="f1851-121">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="f1851-122">可以修改连接站点中的任一个（或两个），也可以修改与链接关联的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="f1851-122">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="f1851-123">下面的示例展示了如何修改名为里诺的站点链接的带宽策略配置文件 \_ ：</span><span class="sxs-lookup"><span data-stu-id="f1851-123">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="f1851-124">有关参数的详细说明，请参阅 Lync Server 命令行管理程序文档中的 [new-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="f1851-124">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="f1851-125">删除网络站点链接</span><span class="sxs-lookup"><span data-stu-id="f1851-125">To delete a network site link</span></span>

1.  <span data-ttu-id="f1851-126">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="f1851-126">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f1851-127">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f1851-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1851-128">使用 **Remove-CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。</span><span class="sxs-lookup"><span data-stu-id="f1851-128">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="f1851-129">下面的示例删除了里诺的 " \_ 上海 network site" 链接：</span><span class="sxs-lookup"><span data-stu-id="f1851-129">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="f1851-130">有关参数的详细说明，请参阅 Lync Server 命令行管理程序文档中的 [new-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="f1851-130">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1851-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1851-131">See Also</span></span>


[<span data-ttu-id="f1851-132">Lync Server 2013 中的呼叫允许控制 cmdlet</span><span class="sxs-lookup"><span data-stu-id="f1851-132">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="f1851-133">新 New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="f1851-133">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f1851-134">New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="f1851-134">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f1851-135">New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="f1851-135">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f1851-136">New-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="f1851-136">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f1851-137">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f1851-137">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

