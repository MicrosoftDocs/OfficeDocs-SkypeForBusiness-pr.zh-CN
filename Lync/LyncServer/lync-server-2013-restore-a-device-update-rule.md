---
title: Lync Server 2013：还原设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ca4874e7ec0ae462be7360ad62e18cfbdcf018
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="1ea0e-102">在 Lync Server 2013 中还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="1ea0e-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea0e-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1ea0e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1ea0e-104">若要从部署中的设备中卸载设备更新规则，请将其还原。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="1ea0e-105">还原设备更新规则的同时会卸载更新并重新安装该规则的早期版本。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="1ea0e-106">您可以使用 Lync Server 控制面板或 Windows PowerShell 还原设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="1ea0e-107">使用 Lync Server 控制面板还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="1ea0e-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1ea0e-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1ea0e-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ea0e-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ea0e-111">在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="1ea0e-112">在 "**设备更新**" 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1ea0e-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1ea0e-113">若要还原一个规则，请选择该规则。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="1ea0e-114">若要还原所有规则，请单击 "**编辑**"，然后单击 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="1ea0e-115">单击 "**操作**" 菜单，然后单击 "**还原**"。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1ea0e-116">使用 Windows PowerShell Cmdlet 还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="1ea0e-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1ea0e-117">还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 还原设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="1ea0e-118">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ea0e-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="1ea0e-120">在服务器上还原单个设备更新规则</span><span class="sxs-lookup"><span data-stu-id="1ea0e-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="1ea0e-121">以下命令将在 Web 服务器 dc2d9b1222ff9 上还原设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="1ea0e-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="1ea0e-122">还原服务器上的所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="1ea0e-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="1ea0e-123">此命令将还原 web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：</span><span class="sxs-lookup"><span data-stu-id="1ea0e-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="1ea0e-124">有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1ea0e-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

