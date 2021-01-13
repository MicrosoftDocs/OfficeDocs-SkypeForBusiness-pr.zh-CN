---
title: 在 Skype for Business Server 中配置电话拨入式会议
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中配置电话拨入式会议。
ms.openlocfilehash: 92c282c87576e3d46353dabd8235521fe0097c11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820722"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="0eb48-103">在 Skype for Business Server 中配置电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="0eb48-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="0eb48-104">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="0eb48-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="0eb48-105">创建包含会议工作负荷和所选电话拨入式会议拓扑后，必须执行其他步骤来配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="0eb48-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="0eb48-106">在阅读本主题之前，请确保已阅读 Plan [for dial-in conferencing in Skype for Business Server、](../../plan-your-deployment/conferencing/dial-in-conferencing.md) [Hardware and software requirements for conferencing in Skype for Business Server，](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)and the Deployment [flowchart and checklist for dial-in conferencing.](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)</span><span class="sxs-lookup"><span data-stu-id="0eb48-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="0eb48-107">若要配置电话拨入式会议，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0eb48-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="0eb48-108">配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="0eb48-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="0eb48-109">配置电话拨入式会议区域</span><span class="sxs-lookup"><span data-stu-id="0eb48-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="0eb48-110">配置拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="0eb48-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="0eb48-111">配置会议策略</span><span class="sxs-lookup"><span data-stu-id="0eb48-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="0eb48-112">为用户帐户分配线路 URI</span><span class="sxs-lookup"><span data-stu-id="0eb48-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="0eb48-113">此外，您可以执行以下可选任务。</span><span class="sxs-lookup"><span data-stu-id="0eb48-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="0eb48-114">有关这些可选任务详细信息，请参阅在 [Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md)中管理电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="0eb48-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="0eb48-115">管理电话拨入式会议 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="0eb48-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="0eb48-116">管理 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="0eb48-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="0eb48-117">创建会议目录</span><span class="sxs-lookup"><span data-stu-id="0eb48-117">Create conference directories</span></span>
    
- <span data-ttu-id="0eb48-118">管理会议加入和离开通知</span><span class="sxs-lookup"><span data-stu-id="0eb48-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="0eb48-119">测试电话拨入式会议设置</span><span class="sxs-lookup"><span data-stu-id="0eb48-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="0eb48-120">向拨入用户发送欢迎邮件</span><span class="sxs-lookup"><span data-stu-id="0eb48-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="0eb48-121">配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="0eb48-121">Configure dial plans</span></span>
<span data-ttu-id="0eb48-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb48-122"><a name="BKMK_ConfigureDialPlans"> </a></span></span>

<span data-ttu-id="0eb48-123">部署电话拨入式会议时，需要创建或修改一个或多个用于路由拨入访问电话号码的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="0eb48-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="0eb48-124">您还必须确保每个拨号计划至少包含一个规范化规则，即将电话分机号转换为 E.164 格式的完整电话号码的规则。</span><span class="sxs-lookup"><span data-stu-id="0eb48-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="0eb48-125">电话拨入式会议的用户通过输入其个人标识号 (PIN) 及其电话号码，可以作为经过身份验证的企业用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="0eb48-125">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="0eb48-126">需要使用规范化规则将分机号转换为完整的电话号码，以便在用户只输入电话分机号时可以对其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0eb48-126">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="0eb48-127">设置电话拨入式会议拨号计划：</span><span class="sxs-lookup"><span data-stu-id="0eb48-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="0eb48-128">无论你是否部署企业语音，修改全局拨号计划以添加电话拨入式会议区域，并确保规范化规则准确转换拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="0eb48-129">有关详细说明，请参阅 [在 Skype for Business Server 中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="0eb48-130">如果未部署企业语音，请为电话拨入式会议访问号码创建拨号计划。</span><span class="sxs-lookup"><span data-stu-id="0eb48-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="0eb48-131">确保其中包含电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="0eb48-132">有关详细说明，请参阅 [在 Skype for Business Server 中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="0eb48-133">如果已部署企业语音，请根据需要企业语音拨号计划，以包含区域，并使用适当的规范化规则处理拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="0eb48-134">还可以创建仅用于拨入访问号码的专用拨号计划。</span><span class="sxs-lookup"><span data-stu-id="0eb48-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="0eb48-135">有关详细说明，请参阅 [在 Skype for Business Server 中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="0eb48-136">有关创建规范化规则的详细信息，请参阅在 Skype for Business 中创建或修改 [规范化规则](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="0eb48-137">配置电话拨入式会议区域</span><span class="sxs-lookup"><span data-stu-id="0eb48-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="0eb48-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb48-138"><a name="BKMK_ConfigureDialInRegions"> </a></span></span>

<span data-ttu-id="0eb48-139">设置拨号计划时，指定应用于拨号计划的电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-139">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="0eb48-140">电话拨入式会议区域将电话拨入式会议访问号码与相应的拨号计划关联。</span><span class="sxs-lookup"><span data-stu-id="0eb48-140">The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="0eb48-141">在创建拨入访问号码时，选择将该访问号码与相应拨号计划关联的区域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-141">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="0eb48-142">由于指定所有拨号计划的区域非常重要，因此我们建议您验证所有拨号计划是否都有会议区域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="0eb48-143">若要验证是否针对所有电话拨入式会议拨号计划设置了区域，请使用 **Get-CsDialPlan** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0eb48-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="0eb48-144">如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="0eb48-145">您还可以使用 Skype for Business Server 控制面板更新现有拨号计划中的区域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="0eb48-146">有关使用 Skype for Business Server 控制面板的详细信息，请参阅在 Skype for Business Server 中创建 [或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="0eb48-147">验证拨号计划是否设置了 region 属性</span><span class="sxs-lookup"><span data-stu-id="0eb48-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="0eb48-148">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="0eb48-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="0eb48-149">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0eb48-150">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="0eb48-150">Run the following at the command prompt:</span></span>
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="0eb48-151">例如：</span><span class="sxs-lookup"><span data-stu-id="0eb48-151">For example:</span></span>
    
   ```powershell
   Get-CsDialPlan
   ```

   <span data-ttu-id="0eb48-152">在此例中，返回为组织配置的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="0eb48-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="0eb48-153">查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。</span><span class="sxs-lookup"><span data-stu-id="0eb48-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="0eb48-154">有关详细信息，请参阅 [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="0eb48-155">设置拨号计划的 region 属性</span><span class="sxs-lookup"><span data-stu-id="0eb48-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="0eb48-156">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="0eb48-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="0eb48-157">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0eb48-158">对于缺少电话拨入式会议区域的任何拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="0eb48-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="0eb48-159">例如：</span><span class="sxs-lookup"><span data-stu-id="0eb48-159">For example:</span></span>
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="0eb48-160">在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。</span><span class="sxs-lookup"><span data-stu-id="0eb48-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="0eb48-161">有关详细信息，请参阅 [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="0eb48-162">配置拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="0eb48-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="0eb48-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb48-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span></span>

<span data-ttu-id="0eb48-164">部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打的电话号码，以加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="0eb48-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="0eb48-165">这些拨入访问号码显示在会议邀请和电话拨入式会议设置网页中。</span><span class="sxs-lookup"><span data-stu-id="0eb48-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="0eb48-166">必须先规划电话拨入式会议区域，然后使用这些区域配置拨号计划，然后才能创建拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="0eb48-167">有关区域的详细信息，请参阅在 Skype for Business Server 中规划电话拨入 [式会议](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="0eb48-168">有关为电话拨入式会议配置拨号计划的详细信息，请参阅在 Skype for Business Server 中创建 [或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb48-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0eb48-169">在 Active Directory 域服务 (AD DS) 完成该访问号码的复制之前，不能使用新的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-169">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete.</span></span> <span data-ttu-id="0eb48-170">复制可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="0eb48-170">Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0eb48-171">创建拨入访问号码后，您可以修改 Active Directory 显示名称对象的联系人号码，以便用户可以更轻松地识别正确的访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="0eb48-172">若要修改显示名称，请使用 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0eb48-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="0eb48-173">不应手动修改 Active Directory 对象。</span><span class="sxs-lookup"><span data-stu-id="0eb48-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="0eb48-174">创建拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="0eb48-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="0eb48-175">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0eb48-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0eb48-176">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="0eb48-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0eb48-177">在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。</span><span class="sxs-lookup"><span data-stu-id="0eb48-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="0eb48-178">在 **"拨入访问号码** "页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0eb48-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="0eb48-179">单击 **"新建**"打开 **"新建拨入访问号码"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="0eb48-180">单击列表中的某个拨入访问号码，再单击"编辑"，然后单击"**显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0eb48-181">使用搜索字段搜索拨入访问号码列表中的列的内容可能不会获得预期的结果。</span><span class="sxs-lookup"><span data-stu-id="0eb48-181">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="0eb48-182">相反，按感兴趣的列对列表进行排序，以标识要查看或更改的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-182">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="0eb48-183">在 **"显示** 号码"中，键入公用电话交换网 (PSTN) 电话用户拨打以加入会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-183">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> <span data-ttu-id="0eb48-184">此号码显示在会议邀请和电话拨入式会议设置网页中。</span><span class="sxs-lookup"><span data-stu-id="0eb48-184">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="0eb48-185">在 **"显示** 名称"中，键入拨入访问号码的说明。</span><span class="sxs-lookup"><span data-stu-id="0eb48-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="0eb48-186">这是与 Skype for Business 搜索结果中的拨入访问号码相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="0eb48-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="0eb48-187">当用户呼叫访问号码时，此名称将显示在客户端中。</span><span class="sxs-lookup"><span data-stu-id="0eb48-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="0eb48-188">在 **线路 URI** 中，键入 TEL URI 格式的拨入访问号码的 E.164 号码，包括号码前的 + 符号和不包括空格。</span><span class="sxs-lookup"><span data-stu-id="0eb48-188">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="0eb48-189">例如，tel：+14255550200。</span><span class="sxs-lookup"><span data-stu-id="0eb48-189">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0eb48-190">同一线路 URI 不能由另一个电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="0eb48-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="0eb48-191">在 **SIP URI** 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0eb48-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="0eb48-192">在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="0eb48-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="0eb48-193">此 SIP URI 显示在各种位置，包括但不限于呼叫通知消息和以前版本的 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="0eb48-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0eb48-194">同一 SIP URI 不能由另一个电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="0eb48-194">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="0eb48-195">创建访问号码后，不能修改 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="0eb48-195">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="0eb48-196">更改 SIP URI 的唯一方法就是删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-196">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="0eb48-197">在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序的域。</span><span class="sxs-lookup"><span data-stu-id="0eb48-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="0eb48-198">在 **池中**，单击运行支持此拨入访问号码的会议助理实例的池。</span><span class="sxs-lookup"><span data-stu-id="0eb48-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0eb48-199">如果在创建访问号码后需要更改池，则必须使用 [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet 或删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="0eb48-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="0eb48-200">在 **主要语言** 中，单击为此拨入访问号码播放提示的语言。</span><span class="sxs-lookup"><span data-stu-id="0eb48-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="0eb48-201">主要语言是会议助理用于应答呼叫的语言。</span><span class="sxs-lookup"><span data-stu-id="0eb48-201">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="0eb48-202">支持的语言与"电话拨入式会议设置"网页上的每个访问电话号码一起显示。</span><span class="sxs-lookup"><span data-stu-id="0eb48-202">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="0eb48-203"> (可选) 在辅助语言 **中 (最多四个) ，** 单击"添加"，选择要为此拨入访问号码的呼叫者支持的一种或多种语言，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="0eb48-204">您可以为每个拨入访问号码选择最多四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="0eb48-204">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="0eb48-205">用户在拨入会议时，可以在输入会议 ID 之前选择辅助语言。</span><span class="sxs-lookup"><span data-stu-id="0eb48-205">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="0eb48-206">若要为拨入访问号码添加区域，请在"关联区域"下，单击"添加"，单击与此拨入访问号码的拨号计划关联的一个或多个区域，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="0eb48-207">若要从拨入访问号码中删除某个区域，请在"关联区域"下，单击要删除的区域，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="0eb48-208">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="0eb48-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="0eb48-209">配置会议策略</span><span class="sxs-lookup"><span data-stu-id="0eb48-209">Configure conferencing policies</span></span>
<span data-ttu-id="0eb48-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb48-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span></span>

<span data-ttu-id="0eb48-p122">会议策略是一种用户帐户设置，用于指定参与者的会议体验。您可以创建具有站点作用域或用户作用域的会议策略。会议策略设置包含会议安排和参与会议的多个方面。一些会议策略设置支持参与者参加电话拨入式会议。当您配置电话拨入式会议时，应该确认已针对组织正确设置了这些字段，并根据需要进行修改。</span><span class="sxs-lookup"><span data-stu-id="0eb48-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="0eb48-216">有关配置会议策略的信息，请参阅"在 Skype for Business Server 中管理会议[策略"。](../../manage/conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0eb48-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="0eb48-217">为用户帐户分配线路 URI</span><span class="sxs-lookup"><span data-stu-id="0eb48-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="0eb48-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="0eb48-218"><a name="BKMK_AssignaLineURI"> </a></span></span>

<span data-ttu-id="0eb48-219">拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="0eb48-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="0eb48-220">身份验证需要 Skype for Business Server 用户帐户上指定的电话线路 **URI。**</span><span class="sxs-lookup"><span data-stu-id="0eb48-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="0eb48-221">本主题中的过程介绍如何为单个用户帐户分配“线路 URI”。</span><span class="sxs-lookup"><span data-stu-id="0eb48-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="0eb48-222">如果需要为多个用户帐户分配“线路 URI”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。</span><span class="sxs-lookup"><span data-stu-id="0eb48-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="0eb48-223">有关使用示例脚本将线路 **URI** 分配给多个用户帐户的详细信息，请参阅"将线路 [URI 分配给多个用户"。](https://go.microsoft.com/fwlink/p/?linkId=196945)</span><span class="sxs-lookup"><span data-stu-id="0eb48-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="0eb48-224">以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="0eb48-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="0eb48-225">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="0eb48-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0eb48-226">在左侧导航栏中，单击 **“用户”**。</span><span class="sxs-lookup"><span data-stu-id="0eb48-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0eb48-227">在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击 **“添加筛选器”** 以指定搜索字段，然后单击 **“查找”**。</span><span class="sxs-lookup"><span data-stu-id="0eb48-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="0eb48-228">双击用户名以打开"编辑 Skype **for Business Server 用户** "对话框。</span><span class="sxs-lookup"><span data-stu-id="0eb48-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="0eb48-229">在 **“电话”** 下的 **“线路 URI”** 字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。</span><span class="sxs-lookup"><span data-stu-id="0eb48-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0eb48-230">只有当电话服务设置为仅 PC到 PC、企业语音、远程呼叫控制或远程呼叫控制时 **，你** 才能指定线路 **URI。** </span><span class="sxs-lookup"><span data-stu-id="0eb48-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="0eb48-231">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="0eb48-231">Click **Commit**.</span></span>
    

