---
title: 在 Skype for Business Server 中创建会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 摘要：了解如何在 Skype for Business Server 中创建会议策略。
ms.openlocfilehash: 81fcaa15c7b12b499c833ac012ef6d999da683ad
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119521"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="c680b-103">在 Skype for Business Server 中创建会议策略</span><span class="sxs-lookup"><span data-stu-id="c680b-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="c680b-104">**摘要：** 了解如何在 Skype for Business Server 中创建会议策略。</span><span class="sxs-lookup"><span data-stu-id="c680b-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="c680b-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序创建会议策略。</span><span class="sxs-lookup"><span data-stu-id="c680b-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c680b-106">使用 Skype for Business Server 控制面板创建会议策略</span><span class="sxs-lookup"><span data-stu-id="c680b-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c680b-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c680b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c680b-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="c680b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c680b-109">在左侧导航栏中，单击 **"会议"，** 然后单击"**会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="c680b-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="c680b-110">单击“新建”，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="c680b-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c680b-p101">要创建用户级别的策略，请单击“用户策略”。在“新建会议策略”中的“名称”字段，键入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c680b-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="c680b-p102">要创建站点级别的策略，请单击“站点策略”。在“选择站点”搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="c680b-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="c680b-116">站点名称将成为会议策略名称;不能更改。</span><span class="sxs-lookup"><span data-stu-id="c680b-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="c680b-117">在“说明”中，键入策略的说明。</span><span class="sxs-lookup"><span data-stu-id="c680b-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="c680b-p103">在“组织者策略”下的“最大会议大小”中，键入允许参加一次会议的最大用户数。默认情况下，最大会议大小为 250。</span><span class="sxs-lookup"><span data-stu-id="c680b-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="c680b-120">要阻止用户邀请匿名用户参加会议，请清除 **“允许参与者邀请匿名用户”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="c680b-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="c680b-121">匿名用户是在你的组织的 Active Directory 域服务中没有凭据，因此未经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="c680b-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="c680b-122">默认情况下，用户可以邀请匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="c680b-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="c680b-123">在 **“录制”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c680b-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="c680b-p105">要阻止参与者录制会议，请单击 **“无”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c680b-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="c680b-126">要允许参与者录制会议，请单击 **“启用录制”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="c680b-p106">要允许外部参与者录制会议，请选中 **“允许联盟参与者和匿名参与者录制”** 复选框。默认为阻止外部参与者录制会议。</span><span class="sxs-lookup"><span data-stu-id="c680b-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="c680b-129">在 **“音频/视频”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c680b-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="c680b-130">要阻止使用音频和视频，请单击 **“无”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="c680b-131">要允许使用音频但不允许使用视频，请单击 **“启用 IP 音频”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="c680b-p107">要允许使用音频和视频，请单击 **“启用 IP 音频/视频”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c680b-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="c680b-134">如果在 **“音频/视频”** 中选择允许使用音频，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c680b-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="c680b-p108">要阻止用户通过电话拨入加入会议，请清除 **“启用 PSTN 电话拨入式会议”** 复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。</span><span class="sxs-lookup"><span data-stu-id="c680b-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="c680b-p109">如果您允许用户通过电话拨入加入会议并允许未经身份验证的（匿名）用户通过拨出式电话加入会议，请选中 **“允许匿名参与者拨出”** 复选框。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。默认情况下，匿名用户无法通过拨出式电话加入会议。</span><span class="sxs-lookup"><span data-stu-id="c680b-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="c680b-140">如果你选择允许使用音频 **/** 视频中的视频，请检查 **允许多个视频流**。</span><span class="sxs-lookup"><span data-stu-id="c680b-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="c680b-141">在 **“数据协作”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c680b-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="c680b-142">要阻止数据协作，请单击 **“无”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="c680b-p110">要允许数据协作，请单击 **“启用数据协作”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c680b-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="c680b-145">如果在 **“数据协作”** 中选择允许数据协作，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c680b-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="c680b-p111">要阻止外部下载，请清除 **“允许联盟参与者和匿名参与者下载内容”** 复选框。默认情况下，外部用户可以下载内容。</span><span class="sxs-lookup"><span data-stu-id="c680b-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="c680b-p112">要阻止文件传输，请清除 **“允许参与者传输文件”** 复选框。默认情况下，用户可以传输文件。</span><span class="sxs-lookup"><span data-stu-id="c680b-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="c680b-150">要阻止使用批注，请清除 **“启用批注”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="c680b-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="c680b-151">若要在共享的 PowerPoint 演示文稿中使用批注，请清除"**启用 PowerPoint 批注"。**</span><span class="sxs-lookup"><span data-stu-id="c680b-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="c680b-152">默认情况下，允许使用批注。</span><span class="sxs-lookup"><span data-stu-id="c680b-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="c680b-p114">要阻止使用投票，请清除 **“启用投票”** 复选框。默认情况下，允许使用投票。</span><span class="sxs-lookup"><span data-stu-id="c680b-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="c680b-155">在 **“应用程序共享”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c680b-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="c680b-156">要阻止使用应用程序共享，请单击 **“禁用应用程序共享”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="c680b-p115">要允许使用应用程序共享，请单击 **“启用应用程序共享”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c680b-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="c680b-159">如果在 **“应用程序共享”** 中选择允许应用程序共享，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c680b-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="c680b-p116">要阻止会议参与者控制应用程序共享，请清除 **“允许参与者获得控制权”** 复选框。默认情况下，参与者可以控制应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="c680b-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="c680b-p117">如果选择允许会议参与者控制应用程序共享，请选中 **“允许联盟参与者和匿名参与者获得控制权”** 复选框以允许外部用户控制应用程序共享。默认情况下，外部用户不能控制应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="c680b-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="c680b-164">在 **“参与者策略”** 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c680b-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="c680b-165">要同时阻止应用程序共享和桌面共享，请单击 **“禁用应用程序共享和桌面共享”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="c680b-166">要允许应用程序共享但不允许桌面共享，请单击 **“启用应用程序共享”**。</span><span class="sxs-lookup"><span data-stu-id="c680b-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="c680b-p118">要同时允许应用程序共享和桌面共享，请单击 **“启用应用程序共享和桌面共享”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c680b-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="c680b-p119">要阻止对等文件传输，请清除 **“启用对等文件传输”** 复选框。默认情况下，允许对等文件传输。</span><span class="sxs-lookup"><span data-stu-id="c680b-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="c680b-p120">要允许对等录制，请选中“启用对等录制”复选框。默认情况下，不允许对等录制。</span><span class="sxs-lookup"><span data-stu-id="c680b-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="c680b-p121">要允许参与者加入多个视频流，请选中“允许参与者加入多个视频流”复选框，默认情况下，允许多个视频流。</span><span class="sxs-lookup"><span data-stu-id="c680b-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="c680b-175">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="c680b-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c680b-176">使用 Skype for Business Server 命令行管理程序创建会议策略</span><span class="sxs-lookup"><span data-stu-id="c680b-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c680b-177">若要创建会议策略，请使用 **New-CsConferencingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c680b-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c680b-178">以下示例创建 Identity 为 SalesConferencingPolicy 的新会议策略。</span><span class="sxs-lookup"><span data-stu-id="c680b-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="c680b-179">此策略将使用会议策略的所有默认值，但 MaxMeetingSize 除外。</span><span class="sxs-lookup"><span data-stu-id="c680b-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="c680b-180">本示例中，会议的最大大小将设置为 50，而不是默认值 250：</span><span class="sxs-lookup"><span data-stu-id="c680b-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="c680b-181">有关详细信息，包括完整的语法说明和参数列表，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c680b-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
