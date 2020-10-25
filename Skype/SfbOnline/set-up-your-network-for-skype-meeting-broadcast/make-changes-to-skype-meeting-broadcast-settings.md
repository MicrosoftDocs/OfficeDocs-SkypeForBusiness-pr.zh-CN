---
title: 对您的组织的 Skype 会议直播设置进行更改
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
description: 您可以启用 Skype 会议直播，并对这些会议的设置和策略进行更改。
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753407"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="8344c-103">对您的组织的 Skype 会议直播设置进行更改</span><span class="sxs-lookup"><span data-stu-id="8344c-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8344c-104">Microsoft 团队管理中心已将 Skype for Business 管理中心替换 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="8344c-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="8344c-105">管理 Skype for Business 的所有设置现在均位于团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="8344c-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="8344c-106">你必须分配有全局管理员或 Skype for Business 管理员的 [AZURE AD 管理员角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能在团队管理中心中管理 Skype for business 功能。</span><span class="sxs-lookup"><span data-stu-id="8344c-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="8344c-107">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="8344c-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="8344c-108">您可以启用 Skype 会议直播，并对这些会议的设置和策略进行更改。</span><span class="sxs-lookup"><span data-stu-id="8344c-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="8344c-109">**启用 Skype 会议直播** 启用 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="8344c-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="8344c-110">启用 Skype 会议直播后，您需要为 [Skype 会议直播设置您的网络](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="8344c-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="8344c-111">如果要为您的企业外部的人员保留网络研讨会和其他广播，请执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="8344c-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="8344c-112">**为我的组织启用 Skype 会议直播预览功能** Skype for Business 客户计划使您能够及早访问新产品和功能。</span><span class="sxs-lookup"><span data-stu-id="8344c-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="8344c-113">这让你的组织 sneak 了解即将推出的内容，以及在我们将产品内部版本发布到公众之前提供反馈的机会。</span><span class="sxs-lookup"><span data-stu-id="8344c-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="8344c-114">Skype for business 预览版</span><span class="sxs-lookup"><span data-stu-id="8344c-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="8344c-115">**允许组织者安排匿名会议** 这允许组织者创建允许组织外部的任何人无需登录即可加入的广播事件。</span><span class="sxs-lookup"><span data-stu-id="8344c-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="8344c-116">**允许录制广播会议** 这将允许演示者或组织者记录任何会议。</span><span class="sxs-lookup"><span data-stu-id="8344c-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="8344c-117">**面向与会者的帮助台支持 URL** 输入会议直播与会者在连接或参加广播会议需要帮助时使用的链接。</span><span class="sxs-lookup"><span data-stu-id="8344c-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="8344c-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="8344c-118">Related topics</span></span>

[<span data-ttu-id="8344c-119">设置 Skype 会议直播网络</span><span class="sxs-lookup"><span data-stu-id="8344c-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
