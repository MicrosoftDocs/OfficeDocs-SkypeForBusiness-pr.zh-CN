---
title: Lync Server 2013：批准设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb464d0845f70012bdd8e70365c8a7993de6b4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="fecd6-102">在 Lync Server 2013 中批准设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fecd6-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fecd6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fecd6-104">导入设备更新规则后，它将安装在测试设备上。</span><span class="sxs-lookup"><span data-stu-id="fecd6-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="fecd6-105">如果你的测试成功，并且希望将更新部署到你的组织，请使用 Lync Server 控制面板或 Windows PowerShell 批准它。</span><span class="sxs-lookup"><span data-stu-id="fecd6-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="fecd6-106">使用 Lync Server "控制面板" 批准设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fecd6-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fecd6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fecd6-108">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fecd6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fecd6-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fecd6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fecd6-110">在 "**设备更新**" 页面上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fecd6-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="fecd6-111">若要批准一个规则，请选择该规则。</span><span class="sxs-lookup"><span data-stu-id="fecd6-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="fecd6-112">若要批准所有规则，请单击 "**编辑**"，然后单击 "**全选**"。</span><span class="sxs-lookup"><span data-stu-id="fecd6-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="fecd6-113">单击 "**操作**"，然后单击 "**批准**"。</span><span class="sxs-lookup"><span data-stu-id="fecd6-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fecd6-114">使用 Windows PowerShell Cmdlet 批准设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fecd6-115">还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 批准设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="fecd6-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="fecd6-116">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="fecd6-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fecd6-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="fecd6-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="fecd6-118">批准单个设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="fecd6-119">以下命令批准在 Web 服务器 dc2d9b1222ff9 上找到的 device update 规则 d5ce3c10-2588-420a-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="fecd6-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="fecd6-120">批准多个设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="fecd6-121">此命令批准 Microsoft 品牌设备的所有设备更新规则：</span><span class="sxs-lookup"><span data-stu-id="fecd6-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="fecd6-122">有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fecd6-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fecd6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fecd6-123">See Also</span></span>


[<span data-ttu-id="fecd6-124">在 Lync Server 2013 中导入设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="fecd6-125">在 Lync Server 2013 中还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="fecd6-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

