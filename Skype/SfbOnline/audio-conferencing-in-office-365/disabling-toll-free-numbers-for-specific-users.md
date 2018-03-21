---
title: "禁用对特定用户的免费电话号码"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "管理员可以控制如何组织者可以使用免费电话号码，为他们的会议。"
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="2fb41-103">禁用对特定用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="2fb41-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="2fb41-104">如果您的组织在其 Microsoft 音频会议桥有免费电话号码，您可以允许或阻止特定组织的会议中它们的用法。</span><span class="sxs-lookup"><span data-stu-id="2fb41-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="2fb41-105">默认情况下，您的组织中的所有用户使用免费电话号码，意味着这些数字，如果可用，可以使用由参与者参加他们的会议都启用。</span><span class="sxs-lookup"><span data-stu-id="2fb41-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="2fb41-106">如果这不是您组织中的某些用户所需的行为，可以从免费电话的号码启用控件通过其会议中使用这些数字来限制特定用户。</span><span class="sxs-lookup"><span data-stu-id="2fb41-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="2fb41-107">当给定组织禁用免费电话号码：</span><span class="sxs-lookup"><span data-stu-id="2fb41-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="2fb41-108">免费电话号码将不再包含在他或她的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="2fb41-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2fb41-109">免费电话号码将不再列出中他引用了"查找本地号码"页面上，或者她会议邀请。</span><span class="sxs-lookup"><span data-stu-id="2fb41-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="2fb41-110">参与者不能加入给定组织者的会议，如果他们拨组织任何免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="2fb41-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="2fb41-111">将自动重新安排所有会议的组织者，和免费电话号码将它们从中删除。</span><span class="sxs-lookup"><span data-stu-id="2fb41-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="2fb41-112">这将重新组织者的电子邮件邀请的所有发送给这些会议的所有参与者。</span><span class="sxs-lookup"><span data-stu-id="2fb41-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="2fb41-113">参与者可以继续参加会议的组织者使用免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="2fb41-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a><span data-ttu-id="2fb41-114">禁用对特定用户使用 Skype 业务管理中心的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="2fb41-114">Disabling toll-free numbers for specific users using the Skype for Business admin center</span></span> 
 1. <span data-ttu-id="2fb41-115">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2fb41-115">Go to the **Office 365 admin center** > **Skype for Business**.</span></span> 
 2. <span data-ttu-id="2fb41-116">在有关业务管理中心在左侧的导航中，Skype 转到**音频会议** > **用户**，然后选择可用的用户列表中用户。</span><span class="sxs-lookup"><span data-stu-id="2fb41-116">In the Skype for Business admin center, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 
 3. <span data-ttu-id="2fb41-117">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2fb41-117">In the Action pane, click **Edit**.</span></span> 
 4. <span data-ttu-id="2fb41-118">选中或清除**允许使用免费电话号码加入此用户的会议**。</span><span class="sxs-lookup"><span data-stu-id="2fb41-118">Check or clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 5. <span data-ttu-id="2fb41-119">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2fb41-119">Click **Save**.</span></span> 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a><span data-ttu-id="2fb41-120">禁用对特定用户使用 PowerShell 的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="2fb41-120">Disabling toll-free numbers for specific users using PowerShell</span></span>  

<span data-ttu-id="2fb41-121">可以使用一组 CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数来启用或禁用此控件。</span><span class="sxs-lookup"><span data-stu-id="2fb41-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="2fb41-122">例如：</span><span class="sxs-lookup"><span data-stu-id="2fb41-122">For example:</span></span> 

 - <span data-ttu-id="2fb41-123">一组 CsOnlineDialInConferencingUser user@contoso.com-AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="2fb41-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
