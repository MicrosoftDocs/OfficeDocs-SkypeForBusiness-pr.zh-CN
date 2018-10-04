---
title: 在 Skype for Business Server 中配置电话拨入式会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要： 阅读本主题可了解如何在 Skype for Business Server 中配置电话拨入式会议。
ms.openlocfilehash: 3c4460761fadd1dee523eb15949da8fc1bf69f14
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372400"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="12217-103">在 Skype for Business Server 中配置电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="12217-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="12217-104">**摘要：** 阅读本主题可了解如何在 Skype for Business Server 中配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="12217-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="12217-105">创建包含会议工作负荷和所选电话拨入式会议的拓扑后，您必须执行额外的步骤配置电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="12217-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="12217-106">阅读本主题中，确保之前您已阅读[规划中的业务服务器的 Skype 电话拨入式会议](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、[会议中的业务服务器 Skype 的硬件和软件要求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)和[部署流程图和清单电话拨入式会议](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)。</span><span class="sxs-lookup"><span data-stu-id="12217-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="12217-107">为了配置电话拨入式会议，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="12217-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="12217-108">Configure dial plans</span><span class="sxs-lookup"><span data-stu-id="12217-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="12217-109">Configure dial-in conferencing regions</span><span class="sxs-lookup"><span data-stu-id="12217-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="12217-110">Configure dial-in access numbers</span><span class="sxs-lookup"><span data-stu-id="12217-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="12217-111">Configure conferencing policies</span><span class="sxs-lookup"><span data-stu-id="12217-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="12217-112">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="12217-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="12217-113">此外，可以执行以下可选任务。</span><span class="sxs-lookup"><span data-stu-id="12217-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="12217-114">有关这些可选任务的详细信息，请参阅[Skype 业务服务器中的电话拨入式会议管理](../../manage/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="12217-115">管理电话拨入式会议的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="12217-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="12217-116">管理 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="12217-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="12217-117">创建会议目录</span><span class="sxs-lookup"><span data-stu-id="12217-117">Create conference directories</span></span>
    
- <span data-ttu-id="12217-118">管理会议加入和离开通知</span><span class="sxs-lookup"><span data-stu-id="12217-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="12217-119">测试电话拨入式会议设置</span><span class="sxs-lookup"><span data-stu-id="12217-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="12217-120">给电话拨入用户发送欢迎邮件</span><span class="sxs-lookup"><span data-stu-id="12217-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="12217-121">配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="12217-121">Configure dial plans</span></span>
<span data-ttu-id="12217-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="12217-122"></span></span>

<span data-ttu-id="12217-123">部署电话拨入式会议时，需要创建或修改用于路由拨入访问电话号码的一个或多个拨号计划。</span><span class="sxs-lookup"><span data-stu-id="12217-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="12217-124">您还必须确保每个拨号计划都包含至少一个规范化规则-电话分机转换为 E.164 格式的完整电话号码的规则。</span><span class="sxs-lookup"><span data-stu-id="12217-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="12217-p104">电话拨入式会议的用户作为通过身份验证的企业用户，输入其个人标识号 (PIN) 和电话号码来加入会议。你需要规范化规则来将分机号转换为完整电话号码，这样用户只要输入电话分机号，就可通过身份验证。</span><span class="sxs-lookup"><span data-stu-id="12217-p104">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="12217-127">若要设置电话拨入式会议的拨号计划：</span><span class="sxs-lookup"><span data-stu-id="12217-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="12217-128">无论是否部署企业语音，都需修改全局拨号计划，以添加电话拨入式会议区域，并确保规范化规则准确转换拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="12217-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="12217-129">有关详细说明，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="12217-130">如果不部署企业语音，请创建电话拨入式会议访问号码的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="12217-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="12217-131">确保其中包含电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="12217-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="12217-132">有关详细说明，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="12217-133">如果已部署企业语音，请根据需要修改企业语音拨号计划以纳入区域，并对拨入访问号码使用相应的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="12217-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="12217-134">还可以创建仅用于拨入访问号码的专用拨号计划。</span><span class="sxs-lookup"><span data-stu-id="12217-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="12217-135">有关详细说明，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="12217-136">有关创建规范化规则的详细信息，请参阅[创建或修改规范化规则中的业务的 Skype](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="12217-137">配置拨入式会议区域</span><span class="sxs-lookup"><span data-stu-id="12217-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="12217-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="12217-138"></span></span>

<span data-ttu-id="12217-p108">创建拨号计划时，要指定适用于该拨号计划的电话拨入式会议区域。电话拨入式会议区域将电话拨入式会议访问号码与相应的拨号计划相关联。创建拨入访问号码时，要选择将访问号码与相应的拨号计划相关联的区域。</span><span class="sxs-lookup"><span data-stu-id="12217-p108">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="12217-142">因为为所有拨号计划指定区域非常重要，我们建议你验证是否所有拨号计划均有会议区域。</span><span class="sxs-lookup"><span data-stu-id="12217-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="12217-143">若要验证是否为所有电话拨入式会议拨号计划设置了区域，请使用 **Get-CsDialPlan** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12217-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="12217-144">如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。</span><span class="sxs-lookup"><span data-stu-id="12217-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="12217-145">您可以使用 Skype 的业务 Server Control Panel 中现有的拨号计划更新该区域。</span><span class="sxs-lookup"><span data-stu-id="12217-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="12217-146">有关使用的业务 Server Control Panel Skype 的详细信息，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="12217-147">验证拨号计划是否设置了 region 属性</span><span class="sxs-lookup"><span data-stu-id="12217-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="12217-148">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="12217-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="12217-149">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="12217-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="12217-150">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="12217-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="12217-151">例如：</span><span class="sxs-lookup"><span data-stu-id="12217-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="12217-152">在此例中，返回为组织配置的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="12217-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="12217-153">查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。</span><span class="sxs-lookup"><span data-stu-id="12217-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="12217-154">有关详细信息，请参阅[Get-csdialplan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="12217-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="12217-155">设置拨号计划的 region 属性</span><span class="sxs-lookup"><span data-stu-id="12217-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="12217-156">以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="12217-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="12217-157">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="12217-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="12217-158">对于缺少电话拨入式会议区域的任何拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="12217-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="12217-159">例如：</span><span class="sxs-lookup"><span data-stu-id="12217-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="12217-160">在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。</span><span class="sxs-lookup"><span data-stu-id="12217-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="12217-161">有关详细信息，请参阅[Set-csdialplan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="12217-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="12217-162">配置拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="12217-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="12217-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="12217-163"></span></span>

<span data-ttu-id="12217-p110">部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打以加入会议的音频部分的电话号码。这些拨入访问号码显示在会议邀请和“电话拨入式会议设置”网页上。</span><span class="sxs-lookup"><span data-stu-id="12217-p110">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="12217-166">创建拨入访问号码前，必须首先规划电话拨入式会议区域，然后配置区域的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="12217-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="12217-167">有关区域的详细信息，请参阅[Plan for Business Server 的 Skype 中电话拨入式会议](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="12217-168">有关详细信息配置拨号计划的电话拨入式会议，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="12217-p112">在 Active Directory 域服务 (AD DS) 完成对一个新拨入访问号码的复制前，无法使用该拨入访问号码。复制可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="12217-p112">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete. Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="12217-171">创建拨入访问号码后，可以修改 Active Directory 联系人对象的显示名，以便用户可以更轻松地识别正确的访问号码。</span><span class="sxs-lookup"><span data-stu-id="12217-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="12217-172">若要修改的显示名称，请使用[Set-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12217-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="12217-173">不应手动修改 Active Directory 对象。</span><span class="sxs-lookup"><span data-stu-id="12217-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="12217-174">创建拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="12217-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="12217-175">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="12217-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="12217-176">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="12217-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="12217-177">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“拨入访问号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12217-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="12217-178">在“拨入访问号码”\*\*\*\* 页上，执行下列某个操作：</span><span class="sxs-lookup"><span data-stu-id="12217-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="12217-179">单击“新建”\*\*\*\* 打开“新建拨入访问号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12217-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="12217-180">单击列表中的一个拨入访问号码，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12217-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="12217-p114">使用搜索字段搜索拨入访问号码列表中某一列的内容时，可能得不到预期结果。此时，可以按照列的关注度对列表进行排序，以识别要查看或更改的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="12217-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="12217-p115">在“显示号码”\*\*\*\* 中，键入公用电话交换网 (PSTN) 电话用户为加入会议而拨打的电话号码。该号码会显示在会议邀请和电话拨入式会议设置网页中。</span><span class="sxs-lookup"><span data-stu-id="12217-p115">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference. This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="12217-185">在“显示名称”\*\*\*\* 中，键入拨入访问号码的说明。</span><span class="sxs-lookup"><span data-stu-id="12217-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="12217-186">这是与业务搜索结果中 Skype 的拨入访问号码相关联的名称。</span><span class="sxs-lookup"><span data-stu-id="12217-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="12217-187">用户呼叫访问号码时，此名称会显示在客户端上。</span><span class="sxs-lookup"><span data-stu-id="12217-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="12217-p117">在“线路 URI”\*\*\*\* 中，使用 TEL URI 格式键入拨入访问号码的 E.164 号码，请在此号码前添加 + 符号，不要添加空格。例如：tel:+14255550200。</span><span class="sxs-lookup"><span data-stu-id="12217-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12217-190">同一线路 URI 不能由其他电话拨入式会议访问号码重复使用。</span><span class="sxs-lookup"><span data-stu-id="12217-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="12217-191">在“SIP URI”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="12217-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="12217-192">在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="12217-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="12217-193">此 SIP URI 是显示在各种的位置，包括但不是限于呼叫通知消息和早期版本的 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="12217-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="12217-p119">同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。创建访问号码之后，将不能修改 SIP URI。更改 SIP URI 的唯一方法是删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="12217-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="12217-197">在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序的域。</span><span class="sxs-lookup"><span data-stu-id="12217-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="12217-198">在“池”\*\*\*\* 中，单击运行支持此拨入访问号码的会议助理实例的池。</span><span class="sxs-lookup"><span data-stu-id="12217-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12217-199">如果您需要更改池创建访问号码后，您必须使用[Move-csapplicationendpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet 或删除并重新创建访问号码。</span><span class="sxs-lookup"><span data-stu-id="12217-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="12217-200">在“主要语言”\*\*\*\* 中，单击针对此拨入访问号码播放提示时使用的语言。</span><span class="sxs-lookup"><span data-stu-id="12217-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="12217-p120">主要语言是会议助理应答呼叫时使用的语言。支持的语言显示在电话拨入式会议设置网页上的每个访问电话号码旁边。</span><span class="sxs-lookup"><span data-stu-id="12217-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="12217-203">（可选）在“辅助语言（最多 4 个）”\*\*\*\* 中，单击“添加”\*\*\*\*，选择一个或多个要为此拨入访问号码的呼叫者提供支持的其他语言，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12217-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="12217-p121">最多可以为每个拨入访问号码选择四种辅助语言。用户通过电话拨入加入会议时，在输入会议 ID 之前可以选择一种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="12217-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="12217-206">若要添加区域的拨入访问号码，在**关联区域**，下单击**添加**，单击一个或多个区域，与拨号计划针对此拨入访问号码，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12217-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="12217-207">要从拨入访问号码中删除某个区域，请在“关联区域”\*\*\*\* 下，单击要删除的区域，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12217-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="12217-208">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="12217-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="12217-209">配置会议策略</span><span class="sxs-lookup"><span data-stu-id="12217-209">Configure conferencing policies</span></span>
<span data-ttu-id="12217-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="12217-210"></span></span>

<span data-ttu-id="12217-p122">会议策略是一种用户帐户设置，用于指定参与者的会议体验。您可以创建具有站点作用域或用户作用域的会议策略。会议策略设置包含会议安排和参与会议的多个方面。一些会议策略设置支持参与者参加电话拨入式会议。当您配置电话拨入式会议时，应该确认已针对组织正确设置了这些字段，并根据需要进行修改。</span><span class="sxs-lookup"><span data-stu-id="12217-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="12217-216">有关配置会议策略的详细信息，请参阅[管理中的业务服务器 Skype 的会议策略](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="12217-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="12217-217">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="12217-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="12217-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="12217-218"></span></span>

<span data-ttu-id="12217-219">拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="12217-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="12217-220">将电话**线路 URI**指定上 Skype Business Server 用户帐户，则需要进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="12217-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="12217-221">本主题中的过程介绍如何为单个用户帐户分配“**线路 URI**”。</span><span class="sxs-lookup"><span data-stu-id="12217-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="12217-222">如果需要为多个用户帐户分配“**线路 URI**”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。</span><span class="sxs-lookup"><span data-stu-id="12217-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="12217-223">有关使用一个示例脚本将**线路 URI**分配给多个用户帐户的详细信息，请参阅[分配给多个用户的线路 Uri](https://go.microsoft.com/fwlink/p/?linkId=196945)。</span><span class="sxs-lookup"><span data-stu-id="12217-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="12217-224">以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="12217-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="12217-225">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="12217-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="12217-226">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12217-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="12217-227">在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击“**添加筛选器**”以指定搜索字段，然后单击“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="12217-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="12217-228">双击用户名打开“**编辑 Skype for Business Server 用户**”对话框。</span><span class="sxs-lookup"><span data-stu-id="12217-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="12217-229">在“**电话**”下的“**线路 URI**”字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。</span><span class="sxs-lookup"><span data-stu-id="12217-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12217-230">仅当将“**电话**”设置为“**仅限 PC 到 PC**”、“**企业语音**”、“**远程呼叫控制**”或“**仅远程呼叫控制**”时，才可以指定“**线路 URI**”。</span><span class="sxs-lookup"><span data-stu-id="12217-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="12217-231">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="12217-231">Click **Commit**.</span></span>
    

