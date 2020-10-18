---
title: Lync Server 2013：重置设备更新规则
description: Lync Server 2013：重置设备更新规则。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d42b6aee8f4cb3fd93839b4a8575059ba71cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577838"
---
# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="31038-103">在 Lync Server 2013 中重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-103">Reset a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31038-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="31038-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="31038-105">如果您不喜欢更新对测试设备的工作方式，则可以重置设备更新规则，该规则会删除规则的待处理状态，并从测试设备中卸载更新。</span><span class="sxs-lookup"><span data-stu-id="31038-105">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="31038-106">您可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="31038-106">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31038-107">若要卸载已批准的规则 (即) ，请将其还原。</span><span class="sxs-lookup"><span data-stu-id="31038-107">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="31038-108">有关详细信息，请参阅 <A href="lync-server-2013-restore-a-device-update-rule.md">在 Lync Server 2013 中还原设备更新规则</A>。</span><span class="sxs-lookup"><span data-stu-id="31038-108">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="31038-109">使用 Lync Server 控制面板重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-109">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="31038-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="31038-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="31038-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="31038-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="31038-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="31038-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="31038-113">在左侧导航栏中，单击 " **客户端**"，然后单击 " **设备更新** " 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="31038-113">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="31038-114">在 " **设备更新** " 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="31038-114">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="31038-115">若要重置一个规则，请选择要重置的规则。</span><span class="sxs-lookup"><span data-stu-id="31038-115">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="31038-116">若要重置所有规则，请在 " **编辑** " 菜单上单击 " **全选**"。</span><span class="sxs-lookup"><span data-stu-id="31038-116">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="31038-117">若要重置一个品牌的所有规则，请使用 **品牌** 栏菜单。</span><span class="sxs-lookup"><span data-stu-id="31038-117">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="31038-118">单击 " **操作**"，然后单击 " **取消挂起的更新**"。</span><span class="sxs-lookup"><span data-stu-id="31038-118">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="31038-119">如果您确信永远不会要向已取消的设备更新规则 (s) ，则可能需要将其删除。</span><span class="sxs-lookup"><span data-stu-id="31038-119">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="31038-120">有关详细信息，请参阅 <A href="lync-server-2013-remove-a-device-update-rule.md">在 Lync Server 2013 中删除设备更新规则</A>。</span><span class="sxs-lookup"><span data-stu-id="31038-120">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="31038-121">使用 Windows PowerShell Cmdlet 重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-121">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="31038-122">还可以使用 Windows PowerShell 和 **重置 CsDeviceUpdateRule** cmdlet 重置设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="31038-122">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="31038-123">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="31038-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31038-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="31038-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="31038-125">重置服务器上的特定设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-125">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="31038-126">以下命令将在 Web 服务器 dc2d9b1222ff9 上重置设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="31038-126">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="31038-127">重置服务器上的所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-127">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="31038-128">此命令将重置 Web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：</span><span class="sxs-lookup"><span data-stu-id="31038-128">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="31038-129">重置具有特定品牌的所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-129">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="31038-130">在此示例中，将重置组织中与 Microsoft 品牌相同的所有设备更新：</span><span class="sxs-lookup"><span data-stu-id="31038-130">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="31038-131">有关详细信息，请参阅 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="31038-131">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31038-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31038-132">See Also</span></span>


[<span data-ttu-id="31038-133">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="31038-133">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

