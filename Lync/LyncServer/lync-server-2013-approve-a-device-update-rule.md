---
title: Lync Server 2013：批准设备更新规则
description: Lync Server 2013：批准设备更新规则。
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
ms.openlocfilehash: 127d16dad6329e952b9033db07ac2f4a4fe9112c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550718"
---
# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="117f7-103">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-103">Approve a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="117f7-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="117f7-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="117f7-105">导入设备更新规则后，会将其安装在测试设备上。</span><span class="sxs-lookup"><span data-stu-id="117f7-105">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="117f7-106">如果测试成功，并且想要向您的组织推出更新，请使用 Lync Server 控制面板或 Windows PowerShell 批准它。</span><span class="sxs-lookup"><span data-stu-id="117f7-106">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="117f7-107">使用 Lync Server 控制面板批准设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-107">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="117f7-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="117f7-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="117f7-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="117f7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="117f7-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="117f7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="117f7-111">在 " **设备更新** " 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="117f7-111">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="117f7-112">若要批准一个规则，请选择该规则。</span><span class="sxs-lookup"><span data-stu-id="117f7-112">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="117f7-113">若要批准所有规则，请单击 " **编辑**"，然后单击 " **全选**"。</span><span class="sxs-lookup"><span data-stu-id="117f7-113">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="117f7-114">单击 " **操作**"，然后单击 " **批准**"。</span><span class="sxs-lookup"><span data-stu-id="117f7-114">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="117f7-115">使用 Windows PowerShell Cmdlet 批准设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-115">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="117f7-116">还可以使用 Windows PowerShell 和 **CsDeviceUpdateRule** cmdlet 批准设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="117f7-116">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="117f7-117">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="117f7-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="117f7-118">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="117f7-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="117f7-119">批准单个设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-119">To approve a single device update rule</span></span>

  - <span data-ttu-id="117f7-120">以下命令批准在 Web 服务器 dc2d9b1222ff9 上找到的设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="117f7-120">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="117f7-121">批准多个设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-121">To approve multiple device update rules</span></span>

  - <span data-ttu-id="117f7-122">此命令批准适用于 Microsoft 品牌的设备的所有设备更新规则：</span><span class="sxs-lookup"><span data-stu-id="117f7-122">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="117f7-123">有关详细信息，请参阅 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="117f7-123">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="117f7-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="117f7-124">See Also</span></span>


[<span data-ttu-id="117f7-125">在 Lync Server 2013 中导入设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-125">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="117f7-126">在 Lync Server 2013 中还原设备更新规则</span><span class="sxs-lookup"><span data-stu-id="117f7-126">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

