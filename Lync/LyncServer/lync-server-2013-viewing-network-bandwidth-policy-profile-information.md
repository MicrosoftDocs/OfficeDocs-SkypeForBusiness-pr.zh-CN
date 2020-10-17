---
title: Lync Server 2013：查看网络带宽策略配置文件信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08b8b984b1fd0c468f5ca340880ec294bf870e0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518309"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="c16ee-102">在 Lync Server 2013 中查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="c16ee-102">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c16ee-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c16ee-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c16ee-104">作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="c16ee-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="c16ee-105">在 Microsoft Lync Server 2013 中，仅可为音频和视频形式分配带宽限制。</span><span class="sxs-lookup"><span data-stu-id="c16ee-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="c16ee-106">您可以设置总体带宽限制和会话限制。</span><span class="sxs-lookup"><span data-stu-id="c16ee-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="c16ee-107">您可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。</span><span class="sxs-lookup"><span data-stu-id="c16ee-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="c16ee-108">每个带宽策略配置文件都可以与一个或多个网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="c16ee-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="c16ee-109">使用下列过程可查看带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="c16ee-109">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="c16ee-110">若要创建或修改带宽策略配置文件，请参阅 [在 Lync Server 2013 中创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="c16ee-110">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="c16ee-111">查看带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="c16ee-111">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="c16ee-112">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c16ee-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c16ee-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c16ee-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c16ee-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="c16ee-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c16ee-115">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“带宽策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c16ee-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c16ee-116">在 " **带宽策略** " 页上，单击要查看的带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="c16ee-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="c16ee-117">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c16ee-117">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c16ee-118">使用 Windows PowerShell Cmdlet 查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="c16ee-118">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c16ee-119">可以使用 Windows PowerShell 和 Get-CsNetworkBandwidthPolicyProfile cmdlet 查看网络带宽配置文件。</span><span class="sxs-lookup"><span data-stu-id="c16ee-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="c16ee-120">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="c16ee-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c16ee-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="c16ee-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="c16ee-122">查看网络带宽策略配置文件信息</span><span class="sxs-lookup"><span data-stu-id="c16ee-122">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="c16ee-123">若要查看有关所有网络带宽策略配置文件的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="c16ee-123">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="c16ee-124">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="c16ee-124">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="c16ee-125">有关详细信息，请参阅[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c16ee-125">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c16ee-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c16ee-126">See Also</span></span>


[<span data-ttu-id="c16ee-127">在 Lync Server 2013 中创建或修改带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="c16ee-127">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="c16ee-128">在 Lync Server 2013 中删除网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="c16ee-128">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="c16ee-129">在 Lync Server 2013 中配置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="c16ee-129">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

