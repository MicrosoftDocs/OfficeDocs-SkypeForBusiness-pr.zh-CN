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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者如何使用他们会议的免费电话号码。
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238507"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="c658a-103">禁用特定 Skype for Business Online 用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="c658a-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> <span data-ttu-id="c658a-104">有关禁用团队用户免费电话号码的信息，请参阅 [禁用特定的团队用户免费电话号码](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users) 。</span><span class="sxs-lookup"><span data-stu-id="c658a-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="c658a-105">如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="c658a-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="c658a-106">默认方式，组织中的所有用户均启用免费电话号码，这意味着，这些号码，如果可用，参会者可使用它们参加会议。</span><span class="sxs-lookup"><span data-stu-id="c658a-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="c658a-107">如果不希望组织中的某些用户可以这样参会，可以通过免费电话号码启用控件限制特定用户在其会议中使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="c658a-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="c658a-108">当针对某设定组织者禁用免费电话号码时：</span><span class="sxs-lookup"><span data-stu-id="c658a-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="c658a-109">免费电话号码将不再包含在他或她的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="c658a-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c658a-110">免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。</span><span class="sxs-lookup"><span data-stu-id="c658a-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c658a-111">参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。</span><span class="sxs-lookup"><span data-stu-id="c658a-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="c658a-112">将自动重新安排该组织者的所有会议，并将从其删除免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="c658a-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="c658a-113">因此将向这些会议的所有参与者重新发送该组织者的所有电子邮件邀请。</span><span class="sxs-lookup"><span data-stu-id="c658a-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="c658a-114">参会者可以继续使用收费电话号码参加该组织者的会议。</span><span class="sxs-lookup"><span data-stu-id="c658a-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="c658a-115">禁用特定用户的免费电话号码</span><span class="sxs-lookup"><span data-stu-id="c658a-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="c658a-116">从 **Microsoft Teams管理中心**：</span><span class="sxs-lookup"><span data-stu-id="c658a-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="c658a-117">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="c658a-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c658a-118">在 **音频会议** 旁边，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="c658a-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="c658a-119">将 **"在此用户的会议请求中包括** 免费号码"设置为"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="c658a-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="c658a-120">单击" **保存"。**</span><span class="sxs-lookup"><span data-stu-id="c658a-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="c658a-121">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c658a-121">**Using PowerShell**</span></span>  

<span data-ttu-id="c658a-122">可以使用 Set-CsOnlineDialInConferencingUser cmdlet 的 AllowTollFreeDialIn 参数启用或禁用此控件。</span><span class="sxs-lookup"><span data-stu-id="c658a-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="c658a-123">例如：</span><span class="sxs-lookup"><span data-stu-id="c658a-123">For example:</span></span> 

- <span data-ttu-id="c658a-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="c658a-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
