---
title: Lync Server 2013：查看有关设备更新规则的信息
description: Lync Server 2013：查看有关设备更新规则的信息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4aecfd0dd778b576ea4a672e550f9e27d7ca463e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569628"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="d9341-103">在 Lync Server 2013 中查看有关设备更新规则的信息</span><span class="sxs-lookup"><span data-stu-id="d9341-103">View information about Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9341-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d9341-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d9341-105">查看有关已导入的设备更新规则的详细信息，包括更新适用于的设备的类型、模型和品牌;更新的版本和类型;以及更新的区域设置和池。</span><span class="sxs-lookup"><span data-stu-id="d9341-105">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="d9341-106">信息适用于所有导入的设备更新规则：那些待审批的用户、部署 (批准的) 、回调 (还原) 以及已决定不使用 (重置) 。</span><span class="sxs-lookup"><span data-stu-id="d9341-106">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="d9341-107">从 Lync Server 控制面板或 Windows PowerShell 访问此信息。</span><span class="sxs-lookup"><span data-stu-id="d9341-107">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9341-108">有关如何导入、批准、重置、还原和删除规则的详细信息，请参阅 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013 中的设备更新规则中</A>列出的主题。</span><span class="sxs-lookup"><span data-stu-id="d9341-108">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="d9341-109">使用 Lync Server 控制面板查看设备更新规则</span><span class="sxs-lookup"><span data-stu-id="d9341-109">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d9341-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d9341-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9341-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d9341-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9341-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="d9341-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9341-113">在左侧导航栏中，单击 " **客户端**"，然后单击 " **设备更新** " 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="d9341-113">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="d9341-114">" **设备更新** " 页上列出了导入的规则。</span><span class="sxs-lookup"><span data-stu-id="d9341-114">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d9341-115">使用 Windows PowerShell Cmdlet 查看设备更新规则</span><span class="sxs-lookup"><span data-stu-id="d9341-115">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d9341-116">还可以使用 Windows PowerShell 和 **CsDeviceUpdateRule** cmdlet 查看有关您的所有设备更新规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d9341-116">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="d9341-117">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="d9341-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9341-118">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="d9341-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="d9341-119">查看所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="d9341-119">To view all your device update rules</span></span>

  - <span data-ttu-id="d9341-120">以下命令将返回有关配置为在组织中使用的所有设备更新规则的信息：</span><span class="sxs-lookup"><span data-stu-id="d9341-120">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="d9341-121">该命令将针对每个设备更新规则返回类似以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="d9341-121">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="d9341-122">查看特定 web 服务器上的所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="d9341-122">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="d9341-123">若要查看特定计算机上的设备更新规则，请使用筛选器参数后跟服务器标识和通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="d9341-123">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="d9341-124">例如：</span><span class="sxs-lookup"><span data-stu-id="d9341-124">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="d9341-125">有关详细信息，请参阅 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d9341-125">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

