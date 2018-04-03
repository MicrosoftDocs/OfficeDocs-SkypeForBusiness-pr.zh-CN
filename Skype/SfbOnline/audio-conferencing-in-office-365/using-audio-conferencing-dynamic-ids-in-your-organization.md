---
title: 在您的组织中使用音频会议动态 Id
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 正在更新音频会议服务以提供每个 Skype 业务和 Microsoft 小组会议与其他会议 Id。 动态的会议 Id 通过静态的会议 Id，是一项显著改进，因为它们提供了：
ms.openlocfilehash: 418e6f486b8108791930c7843bfed8bdc56e83ef
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="1fa54-104">在您的组织中使用音频会议动态 Id</span><span class="sxs-lookup"><span data-stu-id="1fa54-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="1fa54-105">正在更新音频会议服务以提供每个 Skype 业务和 Microsoft 小组会议与其他会议 Id。</span><span class="sxs-lookup"><span data-stu-id="1fa54-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="1fa54-106">动态的会议 Id 通过静态的会议 Id，是一项显著改进，因为它们提供了：</span><span class="sxs-lookup"><span data-stu-id="1fa54-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="1fa54-107">**增强的安全性**会议 Id 是唯一的每个 Skype 业务或 Microsoft 小组会议，预定会议时，将生成。</span><span class="sxs-lookup"><span data-stu-id="1fa54-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="1fa54-108">**提供了更好的背靠背和侧对侧会议体验** 系统会为一个组织者安排的每场会议提供特定的拨入信息，当多个会议的时间彼此邻近时，这些信息可防止一个会议的电话参与者与其他会议的参与者混淆在一起。</span><span class="sxs-lookup"><span data-stu-id="1fa54-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="1fa54-109">**可以无缝过渡** 为组织启用动态会议 ID 后，组织中具有静态会议 ID 的所有已安排会议将继续有效。</span><span class="sxs-lookup"><span data-stu-id="1fa54-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="1fa54-110">动态的 Id 才可用于为启用的用户 * * 音频会议 * * 和 microsoft 设置为其音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="1fa54-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="1fa54-111">为您的用户，可以[为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md) 。</span><span class="sxs-lookup"><span data-stu-id="1fa54-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="1fa54-112">我的组织中的用户将看到哪些更改？</span><span class="sxs-lookup"><span data-stu-id="1fa54-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="1fa54-113">为您的组织启用了动态会议 Id 之后，任何新的业务或 Microsoft 小组会议，Skype 所计划的启用音频会议将有会议 Id，将从不同组织中的用户他们以前的静态的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="1fa54-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="1fa54-114">他们非常静态的组织者需要提醒用户加入他们他们现在需要在会议邀请中使用新的会议 ID，才能参加它的会议之前的会议 Id。</span><span class="sxs-lookup"><span data-stu-id="1fa54-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa54-115">计划由具有静态会议 Id 的用户组织启用的 Id 将继续具有静态的会议 Id，因此他们将继续安排会议，而不影响动态会议之前的会议。</span><span class="sxs-lookup"><span data-stu-id="1fa54-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="1fa54-116">这些示例演示两个 Skype 按同一个用户的业务会议的新体验，但是现在都为两个不同的会话 Id:</span><span class="sxs-lookup"><span data-stu-id="1fa54-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="1fa54-117">**会议 1** 已安排在上午 9 点到上午 10 点，且会议 ID 为 93907123：</span><span class="sxs-lookup"><span data-stu-id="1fa54-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="1fa54-119">**会议 2** 已由同一个用户安排在上午 10 点到上午 11 点，且会议 ID 为 16353789：</span><span class="sxs-lookup"><span data-stu-id="1fa54-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="1fa54-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="1fa54-121">Related topics</span></span>

- [<span data-ttu-id="1fa54-122">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1fa54-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="1fa54-123">Skype for Business 和 Microsoft Teams 外接程序许可</span><span class="sxs-lookup"><span data-stu-id="1fa54-123">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
