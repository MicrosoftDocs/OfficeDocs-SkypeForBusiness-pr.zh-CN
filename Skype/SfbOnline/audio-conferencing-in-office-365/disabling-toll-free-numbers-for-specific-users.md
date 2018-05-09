---
title: 特定用户的禁用免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制如何组织者可以为他们的会议使用免费电话号码。
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="d9483-103">特定用户的禁用免费电话号码</span><span class="sxs-lookup"><span data-stu-id="d9483-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="d9483-104">如果您的组织具有其 Microsoft 音频会议网桥中免费电话号码，您可以允许或阻止特定的组织者的会议中其使用情况。</span><span class="sxs-lookup"><span data-stu-id="d9483-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="d9483-105">默认情况下，您的组织中的所有用户都启用使用免费电话号码，这意味着，这些号码，如果可用，可用于参与者加入他们的会议。</span><span class="sxs-lookup"><span data-stu-id="d9483-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="d9483-106">如果不为您的组织中的一些用户所需的行为，您可以限制特定用户在其通过免费电话号码启用控件的会议中使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="d9483-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="d9483-107">当给定管理器禁用免费电话号码：</span><span class="sxs-lookup"><span data-stu-id="d9483-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="d9483-108">免费电话号码将不再包括在他或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="d9483-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="d9483-109">免费电话号码将不再列出其中引用的"查找本地号码"页上，或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="d9483-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="d9483-110">参与者将无法加入给定组织者的会议，如果拨组织的任何免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d9483-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="d9483-111">将自动重新安排的组织者的所有会议，并将从其删除免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d9483-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="d9483-112">这将向这些会议的所有参与者重新组织者的电子邮件邀请的所有发送。</span><span class="sxs-lookup"><span data-stu-id="d9483-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="d9483-113">参与者可以继续加入会议的组织者使用收费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d9483-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="d9483-114">特定用户的禁用免费电话号码</span><span class="sxs-lookup"><span data-stu-id="d9483-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="d9483-115">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="d9483-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="d9483-116">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="d9483-116">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="d9483-117">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d9483-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d9483-118">单击**会议网桥**，旁边的菜单，然后单击下拉列表中的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d9483-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="d9483-119">在**会议桥提供程序**窗格中，请关闭**允许使用在组织者要加入此用户的会议的会议桥的免费电话号码**。</span><span class="sxs-lookup"><span data-stu-id="d9483-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="d9483-120">单击**应用。**</span><span class="sxs-lookup"><span data-stu-id="d9483-120">Click **Apply.**</span></span> 

<span data-ttu-id="d9483-121">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="d9483-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d9483-122">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="d9483-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="d9483-123">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d9483-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="d9483-124">清除**允许使用免费电话号码加入此用户的会议**。</span><span class="sxs-lookup"><span data-stu-id="d9483-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="d9483-125">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="d9483-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="d9483-126">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d9483-126">**Using PowerShell**</span></span>  

<span data-ttu-id="d9483-127">您可以使用集 CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数启用或禁用此控件。</span><span class="sxs-lookup"><span data-stu-id="d9483-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="d9483-128">例如：</span><span class="sxs-lookup"><span data-stu-id="d9483-128">For example:</span></span> 

 - <span data-ttu-id="d9483-129">设置 CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="d9483-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
