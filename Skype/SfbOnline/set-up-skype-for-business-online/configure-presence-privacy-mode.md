---
title: 配置状态隐私模式
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: '了解如何为你的用户设置隐私模式，以便他们能够更好地控制用户查看其可用性的方式。 '
ms.openlocfilehash: f0f9237f701be219a9cbce9a44704cbb582f48d4
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739180"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="b42fd-103">配置状态隐私模式</span><span class="sxs-lookup"><span data-stu-id="b42fd-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b42fd-104">Microsoft 团队管理中心已将 Skype for Business 管理中心替换 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="b42fd-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="b42fd-105">管理 Skype for Business 的所有设置现在均位于团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="b42fd-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="b42fd-106">若要了解详细信息，请参阅 [在 Microsoft 团队管理中心中管理 Skype For business 设置](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="b42fd-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="b42fd-107">Skype for Business Online 状态设置使用户可以更好地控制哪些人可以查看他们的可用、会议或外出。</span><span class="sxs-lookup"><span data-stu-id="b42fd-107">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="b42fd-108">有关 Skype for business 状态和隐私设置的详细信息，请参阅 [在 Skype For Business Online 中配置状态](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="b42fd-108">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="b42fd-109">为组织中的每个人选择默认的联机状态设置</span><span class="sxs-lookup"><span data-stu-id="b42fd-109">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="b42fd-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b42fd-110"><a name="__top"> </a></span></span>

1. <span data-ttu-id="b42fd-111">转到 Skype for Business Online 管理中心 > **组织 > "常规**"。</span><span class="sxs-lookup"><span data-stu-id="b42fd-111">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="b42fd-112">在 " **状态隐私模式**" 下，选择设置，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b42fd-112">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="b42fd-113">**设置**</span><span class="sxs-lookup"><span data-stu-id="b42fd-113">**Setting**</span></span>|<span data-ttu-id="b42fd-114">**谁可以查看用户的状态**</span><span class="sxs-lookup"><span data-stu-id="b42fd-114">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b42fd-115">**自动显示联机状态信息**</span><span class="sxs-lookup"><span data-stu-id="b42fd-115">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="b42fd-116">任何不属于 " **外部** " 或 "已 **阻止** " 隐私组的 Skype for business 用户。</span><span class="sxs-lookup"><span data-stu-id="b42fd-116">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="b42fd-117">**仅向用户的联系人显示状态信息**</span><span class="sxs-lookup"><span data-stu-id="b42fd-117">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="b42fd-118">用户联系人列表中任何不属于 " **外部** " 或 "已 **阻止** " 隐私组的人。</span><span class="sxs-lookup"><span data-stu-id="b42fd-118">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="b42fd-119">单个用户可在 "Skype for Business **选项** " 对话框中更改此设置。</span><span class="sxs-lookup"><span data-stu-id="b42fd-119">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="b42fd-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="b42fd-120">Related topics</span></span>
[<span data-ttu-id="b42fd-121">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b42fd-121">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="b42fd-122">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="b42fd-122">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
