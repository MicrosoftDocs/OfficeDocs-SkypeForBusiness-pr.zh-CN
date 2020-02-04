---
title: Lync Server 2013：确保已为拨号计划分配区域
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="3f4be-102">确保拨号计划 Lync Server 2013 已分配区域</span><span class="sxs-lookup"><span data-stu-id="3f4be-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f4be-103">_**主题上次修改时间：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="3f4be-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="3f4be-104">用于电话拨入式会议的拨号计划需要具有指定的电话拨入式会议**区域**以将电话拨入式会议访问号码与相应的拨号计划关联。</span><span class="sxs-lookup"><span data-stu-id="3f4be-104">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="3f4be-105">创建拨号计划时，要指定适用于该拨号计划的电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="3f4be-105">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="3f4be-106">然后，当您创建拨入访问号码时，您可以选择将访问号码与相应的拨号计划相关联的区域。</span><span class="sxs-lookup"><span data-stu-id="3f4be-106">Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="3f4be-107">由于为所有拨号计划指定区域很重要，因此我们建议使用此过程验证所有拨号计划是否都有区域。</span><span class="sxs-lookup"><span data-stu-id="3f4be-107">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions.</span></span> <span data-ttu-id="3f4be-108">此步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="3f4be-108">This step is optional.</span></span>

<span data-ttu-id="3f4be-109">使用**CsDialPlan** cmdlet 验证是否为所有电话拨入式会议拨号计划设置了区域。</span><span class="sxs-lookup"><span data-stu-id="3f4be-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="3f4be-110">如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。</span><span class="sxs-lookup"><span data-stu-id="3f4be-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="3f4be-111">您也可以使用 Lync Server "控制面板" 更新现有拨号计划中的区域。</span><span class="sxs-lookup"><span data-stu-id="3f4be-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="3f4be-112">有关使用 Lync Server 控制面板的详细信息，请参阅[Lync server 2013 中的 "修改拨号计划](lync-server-2013-modify-a-dial-plan.md)"。</span><span class="sxs-lookup"><span data-stu-id="3f4be-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="3f4be-113">验证拨号计划是否设置了 region 属性</span><span class="sxs-lookup"><span data-stu-id="3f4be-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="3f4be-114">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="3f4be-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="3f4be-115">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="3f4be-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3f4be-116">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="3f4be-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="3f4be-117">例如：</span><span class="sxs-lookup"><span data-stu-id="3f4be-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="3f4be-118">在此例中，返回为组织配置的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3f4be-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="3f4be-119">查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3f4be-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="3f4be-120">有关详细信息，请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="3f4be-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="3f4be-121">设置拨号计划的 region 属性</span><span class="sxs-lookup"><span data-stu-id="3f4be-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="3f4be-122">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="3f4be-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="3f4be-123">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="3f4be-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3f4be-124">对于缺少电话拨入式会议区域的任何拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="3f4be-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="3f4be-125">例如：</span><span class="sxs-lookup"><span data-stu-id="3f4be-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="3f4be-126">在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。</span><span class="sxs-lookup"><span data-stu-id="3f4be-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="3f4be-127">有关详细信息，请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="3f4be-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

