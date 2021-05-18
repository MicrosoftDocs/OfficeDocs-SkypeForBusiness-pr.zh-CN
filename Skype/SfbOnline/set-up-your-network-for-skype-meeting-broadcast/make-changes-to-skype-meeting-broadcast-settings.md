---
title: 对组织的Skype 会议广播设置进行更改
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
description: 您可以启用Skype 会议直播，并更改这些会议的设置和策略。
ms.openlocfilehash: fae53601c858bf67db57352e18dbc9799243f996
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238644"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="fd9fd-103">对组织的Skype 会议广播设置进行更改</span><span class="sxs-lookup"><span data-stu-id="fd9fd-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="fd9fd-104">Microsoft Teams管理中心已Skype for Business旧版门户 (管理) 。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="fd9fd-105">现在，管理Skype for Business的所有设置都位于Teams中心。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="fd9fd-106">必须分配全局管理员或 Skype for Business 管理员的[Azure AD](/azure/active-directory/roles/permissions-reference)管理员角色Skype for Business管理中心Teams功能。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="fd9fd-107">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="fd9fd-108">您可以启用Skype 会议直播，并更改这些会议的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="fd9fd-109">**启用Skype 会议广播** 启用Skype 会议广播。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="fd9fd-110">启用"Skype 会议广播"后，需要为"广播"设置[Skype 会议网络](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="fd9fd-111">如果要为企业外部人员举办网络研讨会和其他直播，请执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="fd9fd-112">**为Skype 会议启用实时广播预览版功能** 客户Skype for Business计划可让你提前访问新产品和功能。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="fd9fd-113">这样，组织可以先快速了解即将推出的功能，以及测试自己环境中新功能的机会，在向公众发布产品内部版本之前提供反馈。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="fd9fd-114">Skype for Business预览</span><span class="sxs-lookup"><span data-stu-id="fd9fd-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="fd9fd-115">**允许组织者安排匿名会议** 这允许组织者创建直播活动，允许组织外部的任何人加入，而无需登录。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="fd9fd-116">**允许录制直播会议** 这样，演示者或组织者就能够录制任何会议。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="fd9fd-117">**与会者的支持人员支持 URL** 输入一个链接，供会议直播与会者在连接或参加直播会议时需要帮助使用。</span><span class="sxs-lookup"><span data-stu-id="fd9fd-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fd9fd-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="fd9fd-118">Related topics</span></span>

[<span data-ttu-id="fd9fd-119">设置 Skype 会议直播网络</span><span class="sxs-lookup"><span data-stu-id="fd9fd-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
