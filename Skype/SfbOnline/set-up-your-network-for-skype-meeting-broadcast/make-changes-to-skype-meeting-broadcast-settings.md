---
title: 更改组织的 Skype 会议直播设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- SMB
- ms.lync.lac.BroadcastMeetings
description: 你可以启用 Skype 会议直播，并更改这些会议的设置和策略。
ms.openlocfilehash: 75b1894f486d6448662c459b0d77d4f5d3057a2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106548"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="1964a-103">更改组织的 Skype 会议直播设置</span><span class="sxs-lookup"><span data-stu-id="1964a-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1964a-104">Microsoft Teams 管理中心已取代 Skype for Business 管理中心 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="1964a-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="1964a-105">管理 Skype for Business 的所有设置现在都位于 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="1964a-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="1964a-106">必须分配全局管理员或 Skype for Business 管理员 [的 Azure AD](/azure/active-directory/roles/permissions-reference) 管理员角色，才能在 Teams 管理中心管理 Skype for Business 功能。</span><span class="sxs-lookup"><span data-stu-id="1964a-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="1964a-107">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="1964a-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="1964a-108">你可以启用 Skype 会议直播，并更改这些会议的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="1964a-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="1964a-109">**启用 Skype 会议直播** 启用 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="1964a-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="1964a-110">启用 Skype 会议直播后，你需要为 Skype 会议直播 [设置你的网络](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="1964a-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="1964a-111">如果要为企业外部人员举办网络研讨会和其他直播，请执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="1964a-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="1964a-112">**为组织启用 Skype 会议直播预览版功能** Skype for Business 客户计划可让你提前访问新产品和功能。</span><span class="sxs-lookup"><span data-stu-id="1964a-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="1964a-113">这样，组织可以先快速了解即将推出的功能，以及测试自己环境中新功能的机会，在向公众发布产品内部版本之前提供反馈。</span><span class="sxs-lookup"><span data-stu-id="1964a-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="1964a-114">Skype for Business 预览版</span><span class="sxs-lookup"><span data-stu-id="1964a-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="1964a-115">**允许组织者安排匿名会议** 这允许组织者创建直播活动，允许组织外部的任何人加入，而无需登录。</span><span class="sxs-lookup"><span data-stu-id="1964a-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="1964a-116">**允许录制直播会议** 这样，演示者或组织者就能够录制任何会议。</span><span class="sxs-lookup"><span data-stu-id="1964a-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="1964a-117">**与会者的支持人员支持 URL** 输入一个链接，供会议直播与会者在连接或参加直播会议时需要帮助使用。</span><span class="sxs-lookup"><span data-stu-id="1964a-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="1964a-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="1964a-118">Related topics</span></span>

[<span data-ttu-id="1964a-119">设置 Skype 会议直播网络</span><span class="sxs-lookup"><span data-stu-id="1964a-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
