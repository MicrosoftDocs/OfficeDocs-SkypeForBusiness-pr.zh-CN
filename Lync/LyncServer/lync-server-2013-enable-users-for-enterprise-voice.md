---
title: Lync Server 2013：为用户启用企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d954fcd121bff2dbc77f390b5cdad1116bb7e7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="22f32-102">在 Lync Server 2013 中为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="22f32-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f32-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="22f32-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="22f32-104">为一个或多个中介服务器安装文件后，配置出站呼叫路由，并选择性地部署一个或多个高级企业语音功能，您可以使用以下过程使用户能够通过使用企业语音进行呼叫：</span><span class="sxs-lookup"><span data-stu-id="22f32-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22f32-105">在以下过程中，只有第一种方法可以使用 Lync Server 控制面板执行。</span><span class="sxs-lookup"><span data-stu-id="22f32-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="22f32-106">对于其余的过程，只能使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="22f32-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="22f32-107">为用户帐户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="22f32-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="22f32-108">（可选）为用户帐户分配特定于用户的语音策略。</span><span class="sxs-lookup"><span data-stu-id="22f32-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="22f32-109">（可选）为用户帐户分配特定于用户的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="22f32-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="22f32-110">为用户帐户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="22f32-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="22f32-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="22f32-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22f32-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="22f32-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22f32-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="22f32-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22f32-114">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="22f32-115">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="22f32-116">在表中，单击要为企业语音启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22f32-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="22f32-117">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="22f32-118">在“编辑 Lync Server 用户”\*\*\*\* 页的“电话”\*\*\*\* 下，单击“企业语音”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="22f32-119">单击“线路 URI”\*\*\*\*，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。</span><span class="sxs-lookup"><span data-stu-id="22f32-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="22f32-120">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-120">Click **Commit**.</span></span>

<span data-ttu-id="22f32-121">若要为用户启用企业语音，请确保为用户分配了语音策略和拨号计划，无论是全局的（默认分配的）还是特定于用户的。</span><span class="sxs-lookup"><span data-stu-id="22f32-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="22f32-122">默认情况下，会为所有用户分配一个全局语音策略和一个拨号计划。</span><span class="sxs-lookup"><span data-stu-id="22f32-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="22f32-123">如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。</span><span class="sxs-lookup"><span data-stu-id="22f32-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="22f32-124">要对用户应用每用户语音策略或拨号计划，您必须运行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="22f32-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="22f32-125">有关详细信息，请参阅[Lync Server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序文档。</span><span class="sxs-lookup"><span data-stu-id="22f32-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="22f32-126">语音策略分配</span><span class="sxs-lookup"><span data-stu-id="22f32-126">Voice Policy Assignment</span></span>

<span data-ttu-id="22f32-127">全局和网站级语音策略将自动分配给为企业语音启用的所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="22f32-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="22f32-128">还可以创建适用于特定的用户或组的语音策略。</span><span class="sxs-lookup"><span data-stu-id="22f32-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="22f32-129">必须将这些每用户策略显式分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="22f32-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="22f32-130">如果要对已启用企业语音的所有用户使用全局或站点语音策略，则可以跳过此部分并继续本主题后面的 "拨号计划分配" 部分。</span><span class="sxs-lookup"><span data-stu-id="22f32-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="22f32-131">分配特定于用户的语音策略</span><span class="sxs-lookup"><span data-stu-id="22f32-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="22f32-132">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="22f32-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22f32-133">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="22f32-134">要将现有用户语音策略分配给用户，请在命令提示符处运行：</span><span class="sxs-lookup"><span data-stu-id="22f32-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="22f32-135">例如：</span><span class="sxs-lookup"><span data-stu-id="22f32-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="22f32-136">在此示例中，显示名称为 Bob 凯利的用户被分配了名称为**VoicePolicyJapan**的语音策略。</span><span class="sxs-lookup"><span data-stu-id="22f32-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="22f32-137">有关分配特定于用户的语音策略或运行 Set-csvoicepolicy cmdlet 的详细信息，请参阅[Lync Server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)**程序**文档。</span><span class="sxs-lookup"><span data-stu-id="22f32-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="22f32-138">拨号计划分配</span><span class="sxs-lookup"><span data-stu-id="22f32-138">Dial Plan Assignment</span></span>

<span data-ttu-id="22f32-139">要完成企业语音用户或电话拨入式会议用户的用户帐户配置，必须为用户分配拨号计划。</span><span class="sxs-lookup"><span data-stu-id="22f32-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="22f32-140">如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="22f32-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="22f32-141">如果要对已启用企业语音的所有用户使用全局或站点拨号计划，则可以跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="22f32-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="22f32-142">分配拨号计划</span><span class="sxs-lookup"><span data-stu-id="22f32-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="22f32-143">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="22f32-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22f32-144">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22f32-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="22f32-145">要分配特定于用户的拨号计划，请在命令提示符处运行：</span><span class="sxs-lookup"><span data-stu-id="22f32-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="22f32-146">例如：</span><span class="sxs-lookup"><span data-stu-id="22f32-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="22f32-147">在此示例中，显示名称为小明凯利的用户被分配了名称为**DialPlanJapan**的用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="22f32-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="22f32-148">有关分配用户拨号计划或运行 Grant-csdialplan cmdlet 的详细信息，请参阅[Lync Server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)**程序**文档。</span><span class="sxs-lookup"><span data-stu-id="22f32-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22f32-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22f32-149">See Also</span></span>


[<span data-ttu-id="22f32-150">在 Lync Server 2013 中禁用用户的企业语音</span><span class="sxs-lookup"><span data-stu-id="22f32-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

