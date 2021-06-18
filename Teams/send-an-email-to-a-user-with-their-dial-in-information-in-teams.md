---
title: 向用户发送音频会议信息
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 了解如何向用户发送包含其音频会议信息的电子邮件，Microsoft Teams。
ms.openlocfilehash: 13c566884c5bc3e8d5de873696541c4b88fcb271
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004194"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="5ef08-103">在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5ef08-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="5ef08-104">有时Microsoft Teams用户可能需要你向用户发送其音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="5ef08-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="5ef08-105">为此，可以单击用户属性下的 **"** 通过电子邮件发送会议信息"。</span><span class="sxs-lookup"><span data-stu-id="5ef08-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="5ef08-106">当你发送此电子邮件时，它将包含所有音频会议信息，包括：</span><span class="sxs-lookup"><span data-stu-id="5ef08-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="5ef08-107">用户的会议电话或拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="5ef08-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="5ef08-108">用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="5ef08-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="5ef08-109">下面是发送的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="5ef08-109">Here is an example of the email that is sent:</span></span>
  
![电话拨入式会议电子邮件的示例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="5ef08-111">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5ef08-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="5ef08-113">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="5ef08-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="5ef08-114">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="5ef08-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5ef08-115">在页面的顶部，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="5ef08-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5ef08-116">在 **"音频会议"下**，单击 **"通过电子邮件发送会议信息"。**</span><span class="sxs-lookup"><span data-stu-id="5ef08-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="5ef08-117">此电子邮件的其他须知事项。</span><span class="sxs-lookup"><span data-stu-id="5ef08-117">What else should you know about this email?</span></span>

- <span data-ttu-id="5ef08-118">启用音频会议后，会向贵组织的用户发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="5ef08-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="5ef08-119">向其分配 **音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="5ef08-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="5ef08-120">手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="5ef08-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="5ef08-121">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="5ef08-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="5ef08-122">从 **中删除音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="5ef08-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="5ef08-123">当用户的音频会议提供商从 Microsoft 更改为其他提供商或"无 **"时**。</span><span class="sxs-lookup"><span data-stu-id="5ef08-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="5ef08-124">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="5ef08-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5ef08-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ef08-125">Related topics</span></span>

[<span data-ttu-id="5ef08-126">尝试或购买音频会议Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="5ef08-126">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
