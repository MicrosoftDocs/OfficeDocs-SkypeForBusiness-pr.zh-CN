---
title: 禁用特定 Skype for Business Online 用户的免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者如何使用他们会议的免费电话号码。
ms.openlocfilehash: 316497b6b4569ffef4419b6ed2ce6994c604d16a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370608"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="f3ba7-103">禁用特定 Skype for Business Online 用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="f3ba7-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="f3ba7-104">有关禁用团队用户免费电话号码的信息，请参阅 [禁用特定的团队用户免费电话号码](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users) 。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="f3ba7-105">如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="f3ba7-p101">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span><span class="sxs-lookup"><span data-stu-id="f3ba7-p101">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="f3ba7-108">当针对某设定组织者禁用免费电话号码时：</span><span class="sxs-lookup"><span data-stu-id="f3ba7-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="f3ba7-109">免费电话号码将不再包含在他或她的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f3ba7-110">免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f3ba7-111">参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="f3ba7-112">将自动重新安排该组织者的所有会议，并将从其删除免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="f3ba7-113">因此将向这些会议的所有参与者重新发送该组织者的所有电子邮件邀请。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="f3ba7-114">参会者可以继续使用收费电话号码参加该组织者的会议。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="f3ba7-115">禁用特定用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="f3ba7-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="f3ba7-116">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="f3ba7-117">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="f3ba7-118">清除**允许使用免费电话号码加入此用户的会议**。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="f3ba7-119">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f3ba7-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="f3ba7-120">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3ba7-120">**Using PowerShell**</span></span>  

<span data-ttu-id="f3ba7-p102">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control. For example:</span><span class="sxs-lookup"><span data-stu-id="f3ba7-p102">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control. For example:</span></span> 

- <span data-ttu-id="f3ba7-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="f3ba7-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
