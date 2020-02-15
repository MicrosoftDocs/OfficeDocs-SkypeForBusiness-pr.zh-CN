---
title: Lync Server 2013：重置设备更新规则
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
ms.openlocfilehash: c1079236ceab3fda42b1920675761f272333d264
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="239aa-102">在 Lync Server 2013 中重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="239aa-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="239aa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="239aa-104">如果您不喜欢更新对测试设备的工作方式，则可以重置设备更新规则，该规则会删除规则的待处理状态，并从测试设备中卸载更新。</span><span class="sxs-lookup"><span data-stu-id="239aa-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="239aa-105">您可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="239aa-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="239aa-106">若要卸载已批准的规则（即，已向后滚动），请将其还原。</span><span class="sxs-lookup"><span data-stu-id="239aa-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="239aa-107">有关详细信息，请参阅<A href="lync-server-2013-restore-a-device-update-rule.md">在 Lync Server 2013 中还原设备更新规则</A>。</span><span class="sxs-lookup"><span data-stu-id="239aa-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="239aa-108">使用 Lync Server 控制面板重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="239aa-109">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="239aa-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="239aa-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="239aa-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="239aa-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="239aa-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="239aa-112">在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="239aa-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="239aa-113">在 "**设备更新**" 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="239aa-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="239aa-114">若要重置一个规则，请选择要重置的规则。</span><span class="sxs-lookup"><span data-stu-id="239aa-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="239aa-115">若要重置所有规则，请在 "**编辑**" 菜单上单击 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="239aa-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="239aa-116">若要重置一个品牌的所有规则，请使用**品牌**栏菜单。</span><span class="sxs-lookup"><span data-stu-id="239aa-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="239aa-117">单击 "**操作**"，然后单击 "**取消挂起的更新**"。</span><span class="sxs-lookup"><span data-stu-id="239aa-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="239aa-118">如果你确信不会再推出已取消的设备更新规则，则可能需要将其删除。</span><span class="sxs-lookup"><span data-stu-id="239aa-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="239aa-119">有关详细信息，请参阅<A href="lync-server-2013-remove-a-device-update-rule.md">在 Lync Server 2013 中删除设备更新规则</A>。</span><span class="sxs-lookup"><span data-stu-id="239aa-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="239aa-120">使用 Windows PowerShell Cmdlet 重置设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="239aa-121">还可以使用 Windows PowerShell 和**重置 CsDeviceUpdateRule** cmdlet 重置设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="239aa-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="239aa-122">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="239aa-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="239aa-123">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="239aa-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="239aa-124">重置服务器上的特定设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="239aa-125">以下命令将在 Web 服务器 dc2d9b1222ff9 上重置设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="239aa-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="239aa-126">重置服务器上的所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="239aa-127">此命令将重置 Web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：</span><span class="sxs-lookup"><span data-stu-id="239aa-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="239aa-128">重置具有特定品牌的所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="239aa-129">在此示例中，将重置组织中与 Microsoft 品牌相同的所有设备更新：</span><span class="sxs-lookup"><span data-stu-id="239aa-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="239aa-130">有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="239aa-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="239aa-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="239aa-131">See Also</span></span>


[<span data-ttu-id="239aa-132">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="239aa-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

