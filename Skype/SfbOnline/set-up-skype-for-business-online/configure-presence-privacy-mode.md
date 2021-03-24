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
description: '了解如何为用户设置隐私模式，以便他们可以更好地控制用户查看其可用性的方式。 '
ms.openlocfilehash: 0b708c86d2693228ad7a613755a181fff5b3743d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093466"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="3a660-103">配置状态隐私模式</span><span class="sxs-lookup"><span data-stu-id="3a660-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a660-104">Microsoft Teams 管理中心已取代 Skype for Business 管理中心 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="3a660-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="3a660-105">管理 Skype for Business 的所有设置现在都位于 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="3a660-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="3a660-106">必须分配全局管理员或 Skype for Business 管理员 [的 Azure AD](/azure/active-directory/roles/permissions-reference) 管理员角色，才能在 Teams 管理中心管理 Skype for Business 功能。</span><span class="sxs-lookup"><span data-stu-id="3a660-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="3a660-107">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="3a660-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="3a660-108">Skype for Business Online 状态设置使用户可以更加控制谁可以看到他们是否在线、正在参加会议还是外出。</span><span class="sxs-lookup"><span data-stu-id="3a660-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="3a660-109">有关 Skype for Business 状态和隐私设置的详细信息，请参阅 [在 Skype for Business Online 中配置状态](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="3a660-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="3a660-110">为组织中的每个人选择默认联机状态设置</span><span class="sxs-lookup"><span data-stu-id="3a660-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="3a660-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3a660-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="3a660-112">转到 Skype for Business Online 管理中心 **>">常规"。**</span><span class="sxs-lookup"><span data-stu-id="3a660-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="3a660-113">在 **"状态隐私模式**"下，选择设置，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="3a660-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="3a660-114">**设置**</span><span class="sxs-lookup"><span data-stu-id="3a660-114">**Setting**</span></span>|<span data-ttu-id="3a660-115">**可以查看用户状态的用户**</span><span class="sxs-lookup"><span data-stu-id="3a660-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a660-116">**自动显示联机状态信息**</span><span class="sxs-lookup"><span data-stu-id="3a660-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="3a660-117">不属于外部或阻止隐私 **组** 的任何 Skype for Business用户。</span><span class="sxs-lookup"><span data-stu-id="3a660-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="3a660-118">**仅向用户的联系人显示状态信息**</span><span class="sxs-lookup"><span data-stu-id="3a660-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="3a660-119">用户联系人列表中不属于"外部"或"阻止 **"隐私组的\*\*\*\*任何人。**</span><span class="sxs-lookup"><span data-stu-id="3a660-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="3a660-120">单个用户可以在"Skype for Business 选项"对话框中 **更改** 此设置。</span><span class="sxs-lookup"><span data-stu-id="3a660-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="3a660-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="3a660-121">Related topics</span></span>
[<span data-ttu-id="3a660-122">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a660-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3a660-123">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="3a660-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
