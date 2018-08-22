---
title: 为特定 Skype 业务联机用户禁用免费电话号码
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
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制如何组织者可以为他们的会议使用免费电话号码。
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490542"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="27c2e-103">为特定 Skype 业务联机用户禁用免费电话号码</span><span class="sxs-lookup"><span data-stu-id="27c2e-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="27c2e-104">有关为团队用户禁用工具免费号码的信息，请参阅[特定的团队用户禁用免费电话号码](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="27c2e-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="27c2e-105">如果您的组织具有其 Microsoft 音频会议网桥中免费电话号码，您可以允许或阻止特定的组织者的会议中其使用情况。</span><span class="sxs-lookup"><span data-stu-id="27c2e-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="27c2e-106">默认情况下，您的组织中的所有用户都启用使用免费电话号码，这意味着，这些号码，如果可用，可用于参与者加入他们的会议。</span><span class="sxs-lookup"><span data-stu-id="27c2e-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="27c2e-107">如果不为您的组织中的一些用户所需的行为，您可以限制特定用户在其通过免费电话号码启用控件的会议中使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="27c2e-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="27c2e-108">当给定管理器禁用免费电话号码：</span><span class="sxs-lookup"><span data-stu-id="27c2e-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="27c2e-109">免费电话号码将不再包括在他或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="27c2e-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="27c2e-110">免费电话号码将不再列出其中引用的"查找本地号码"页上，或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="27c2e-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="27c2e-111">参与者将无法加入给定组织者的会议，如果拨组织的任何免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="27c2e-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="27c2e-112">将自动重新安排的组织者的所有会议，并将从其删除免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="27c2e-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="27c2e-113">这将向这些会议的所有参与者重新组织者的电子邮件邀请的所有发送。</span><span class="sxs-lookup"><span data-stu-id="27c2e-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="27c2e-114">参与者可以继续加入会议的组织者使用收费电话号码。</span><span class="sxs-lookup"><span data-stu-id="27c2e-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="27c2e-115">禁用特定用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="27c2e-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="27c2e-116">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，然后选择用户可用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="27c2e-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="27c2e-117">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="27c2e-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="27c2e-118">清除**允许使用免费电话号码加入此用户的会议**。</span><span class="sxs-lookup"><span data-stu-id="27c2e-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="27c2e-119">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="27c2e-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="27c2e-120">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="27c2e-120">**Using PowerShell**</span></span>  

<span data-ttu-id="27c2e-121">您可以使用集 CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数启用或禁用此控件。</span><span class="sxs-lookup"><span data-stu-id="27c2e-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="27c2e-122">例如：</span><span class="sxs-lookup"><span data-stu-id="27c2e-122">For example:</span></span> 

 - <span data-ttu-id="27c2e-123">设置 CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="27c2e-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
