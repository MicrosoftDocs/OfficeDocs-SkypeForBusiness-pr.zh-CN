---
title: 在 Skype for Business Server 2015 中为用户启用企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要： 了解如何使用户能够拨打和接听电话业务服务器 2015年在 Skype 使用企业语音。
ms.openlocfilehash: d187723b347121400bfbce00d238851f2d0651a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="fb765-103">在 Skype for Business Server 2015 中为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="fb765-103">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fb765-104">**摘要：**了解如何使用户能够拨打和接听电话业务服务器 2015年在 Skype 使用企业语音。</span><span class="sxs-lookup"><span data-stu-id="fb765-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fb765-105">企业语音或调用通过工作部署之后，可以使用以下过程来使用户能够通过使用企业语音进行调用：</span><span class="sxs-lookup"><span data-stu-id="fb765-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb765-106">下面的过程中，只有第一个可以执行通过 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="fb765-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="fb765-107">对于剩余的过程中，可用于业务服务器管理外壳只有 Skype。</span><span class="sxs-lookup"><span data-stu-id="fb765-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="fb765-108">企业语音用于启用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fb765-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="fb765-109">（可选）为用户帐户分配特定于用户的语音策略。</span><span class="sxs-lookup"><span data-stu-id="fb765-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="fb765-110">（可选）为用户帐户分配特定于用户的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="fb765-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="fb765-111">以企业语音为启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="fb765-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="fb765-112">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="fb765-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="fb765-113">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="fb765-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fb765-114">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="fb765-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="fb765-115">在“**搜索用户**”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="fb765-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="fb765-116">在表中，单击您想要启用的企业语音的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fb765-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="fb765-117">在“编辑”****菜单上，单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="fb765-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="fb765-118">**编辑业务服务器用户的 Skype**在页上，单击**电话**，中的**企业语音**。</span><span class="sxs-lookup"><span data-stu-id="fb765-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="fb765-119">单击“线路 URI”****，然后键入唯一的规范化电话号码（例如，tel:+14255550200）。</span><span class="sxs-lookup"><span data-stu-id="fb765-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="fb765-120">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="fb765-120">Click **Commit**.</span></span>
    
<span data-ttu-id="fb765-121">要启用用户参与企业语音，为确保语音策略和拨号计划，指定用户是否全局 （默认情况下指定） 或特定于用户的。默认情况下，所有用户都分配一个全局语音策略和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="fb765-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="fb765-122">如果语音策略或拨号计划的站点级别与承载用户帐户的站点相同，则这些站点策略将自动应用于用户。</span><span class="sxs-lookup"><span data-stu-id="fb765-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="fb765-123">要应用的每个用户语音策略或拨号计划与用户，您必须运行**授予 CsVoicePolicy**和**授予 CsDialPlan** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fb765-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="fb765-124">有关详细信息，请参阅本主题中的以下过程。</span><span class="sxs-lookup"><span data-stu-id="fb765-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="fb765-125">语音策略分配</span><span class="sxs-lookup"><span data-stu-id="fb765-125">Voice Policy Assignment</span></span>

<span data-ttu-id="fb765-126">全局和站点级语音策略会自动分配到所有的用户帐户启用的企业语音。</span><span class="sxs-lookup"><span data-stu-id="fb765-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="fb765-127">还可以创建适用于特定的用户或组的语音策略。</span><span class="sxs-lookup"><span data-stu-id="fb765-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="fb765-128">必须将这些每用户策略显式分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="fb765-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="fb765-129">如果您想要使用全局管理员或站点的所有用户都启用了企业语音的语音策略，可以跳过此部分并转到本主题中后面的[拨号计划分配](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)节。</span><span class="sxs-lookup"><span data-stu-id="fb765-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="fb765-130">分配特定于用户的语音策略</span><span class="sxs-lookup"><span data-stu-id="fb765-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="fb765-131">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fb765-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fb765-132">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="fb765-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fb765-133">要将现有用户语音策略分配给用户，请在命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fb765-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="fb765-134">例如：</span><span class="sxs-lookup"><span data-stu-id="fb765-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="fb765-135">在此示例中，显示名称 Bob 凯利向用户分配名称**VoicePolicyJapan**的语音策略。</span><span class="sxs-lookup"><span data-stu-id="fb765-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="fb765-136">拨号计划分配</span><span class="sxs-lookup"><span data-stu-id="fb765-136">Dial Plan Assignment</span></span>
<span data-ttu-id="fb765-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="fb765-137"></span></span>

<span data-ttu-id="fb765-138">完成用户帐户配置为企业语音的用户或用户的拨入会议服务，用户必须分配一个拨号计划。</span><span class="sxs-lookup"><span data-stu-id="fb765-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="fb765-139">如果没有显式分配现有每用户拨号计划，则用户帐户将自动使用全局拨号计划或站点级别拨号计划（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="fb765-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="fb765-140">如果您想要使用全局管理员或站点的所有用户都启用了企业语音的拨号计划，则可以跳过本节。</span><span class="sxs-lookup"><span data-stu-id="fb765-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="fb765-141">分配特定于用户的拨号计划</span><span class="sxs-lookup"><span data-stu-id="fb765-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="fb765-142">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fb765-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fb765-143">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="fb765-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fb765-144">要分配特定于用户的拨号计划，请在命令提示符处运行：</span><span class="sxs-lookup"><span data-stu-id="fb765-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="fb765-145">例如：</span><span class="sxs-lookup"><span data-stu-id="fb765-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="fb765-146">在此示例中，显示名称 Bob 凯利向用户分配用户拨号计划，名为**DialPlanJapan**。</span><span class="sxs-lookup"><span data-stu-id="fb765-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

