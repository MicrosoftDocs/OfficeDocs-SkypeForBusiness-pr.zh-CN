---
title: Lync Server 2013：确保已为拨号计划分配区域
description: Lync Server 2013：确保拨号计划已分配区域。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c055eda221bc03de449631ba38483165a8621773
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563498"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="59c4c-103">确保拨号计划 Lync Server 2013 已分配区域</span><span class="sxs-lookup"><span data-stu-id="59c4c-103">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59c4c-104">_**上次修改的主题：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="59c4c-104">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="59c4c-p101">用于电话拨入式会议的拨号计划需要指定一个“电话拨入式会议区域”\*\*\*\* 来将电话拨入式会议访问号码与相应的拨号计划相关联。设置拨号计划时，指定应用于拨号计划的电话拨入式会议区域。然后，在创建电话拨入式访问号码时，选择将访问号码与相应拨号计划相关联的区域。</span><span class="sxs-lookup"><span data-stu-id="59c4c-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="59c4c-p102">因为为所有拨号计划指定区域非常重要，我们建议您使用此过程验证是否所有拨号计划均有区域。此步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="59c4c-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="59c4c-110">使用 **Get-CsDialPlan** cmdlet 验证是否为所有电话拨入式会议拨号计划设置了区域。</span><span class="sxs-lookup"><span data-stu-id="59c4c-110">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="59c4c-111">如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。</span><span class="sxs-lookup"><span data-stu-id="59c4c-111">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="59c4c-112">您还可以使用 Lync Server 控制面板更新现有拨号计划中的区域。</span><span class="sxs-lookup"><span data-stu-id="59c4c-112">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="59c4c-113">有关使用 Lync Server 控制面板的详细信息，请参阅 [在 Lync server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="59c4c-113">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="59c4c-114">验证拨号计划是否设置了 region 属性</span><span class="sxs-lookup"><span data-stu-id="59c4c-114">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="59c4c-115">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="59c4c-115">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="59c4c-116">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59c4c-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="59c4c-117">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="59c4c-117">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="59c4c-118">例如：</span><span class="sxs-lookup"><span data-stu-id="59c4c-118">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="59c4c-119">在此例中，返回为组织配置的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="59c4c-119">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="59c4c-120">查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。</span><span class="sxs-lookup"><span data-stu-id="59c4c-120">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="59c4c-121">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="59c4c-121">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="59c4c-122">设置拨号计划的 region 属性</span><span class="sxs-lookup"><span data-stu-id="59c4c-122">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="59c4c-123">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="59c4c-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="59c4c-124">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59c4c-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="59c4c-125">对于缺少电话拨入式会议区域的任何拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="59c4c-125">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="59c4c-126">例如：</span><span class="sxs-lookup"><span data-stu-id="59c4c-126">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="59c4c-127">在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。</span><span class="sxs-lookup"><span data-stu-id="59c4c-127">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="59c4c-128">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="59c4c-128">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

