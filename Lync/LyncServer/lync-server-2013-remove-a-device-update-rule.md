---
title: Lync Server 2013：删除设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89e932dbbbde0adbd972eb3bfd5c79e9026be0c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536539"
---
# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="6c6e5-102">在 Lync Server 2013 中删除设备更新规则</span><span class="sxs-lookup"><span data-stu-id="6c6e5-102">Remove a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c6e5-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6c6e5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6c6e5-104">删除设备更新规则会将其从设备更新队列中永久删除。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="6c6e5-105">删除规则不同于从部署中的设备或测试设备中卸载更新。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="6c6e5-106">若要从部署中卸载已批准的更新，请 *还原* 设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="6c6e5-107">有关详细信息，请参阅 [在 Lync Server 2013 中还原设备更新规则](lync-server-2013-restore-a-device-update-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="6c6e5-108">若要卸载未通过测试设备批准的更新，请 *重置* 它。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="6c6e5-109">有关详细信息，请参阅 [在 Lync Server 2013 中重置设备更新规则](lync-server-2013-reset-a-device-update-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="6c6e5-110">您可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="6c6e5-111">使用 Lync Server 控制面板删除设备更新规则</span><span class="sxs-lookup"><span data-stu-id="6c6e5-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6c6e5-112">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6c6e5-113">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6c6e5-114">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6c6e5-115">在左侧导航栏中，单击 " **客户端**"，然后单击 " **设备更新** " 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="6c6e5-116">在 " **设备更新** " 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6c6e5-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6c6e5-117">若要删除一个规则，请选择要删除的规则。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="6c6e5-118">若要删除所有规则，请单击 " **编辑** " 菜单，然后单击 " **全选**"。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="6c6e5-119">单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6c6e5-120">使用 Windows PowerShell Cmdlet 删除设备更新规则</span><span class="sxs-lookup"><span data-stu-id="6c6e5-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6c6e5-121">还可以使用 Windows PowerShell 和 **CsDeviceUpdateRule** cmdlet 删除设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="6c6e5-122">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6c6e5-123">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="6c6e5-124">从服务器中删除单个设备更新规则</span><span class="sxs-lookup"><span data-stu-id="6c6e5-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="6c6e5-125">下面的命令从 dc2d9b1222ff9 上的 Web 服务器中删除设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="6c6e5-126">从服务器中删除所有设备更新规则</span><span class="sxs-lookup"><span data-stu-id="6c6e5-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="6c6e5-127">此命令将从 atl-cs-001.litwareinc.com 上的 web 服务器中删除所有设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="6c6e5-128">有关详细信息，请参阅 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6c6e5-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c6e5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c6e5-129">See Also</span></span>


[<span data-ttu-id="6c6e5-130">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="6c6e5-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

