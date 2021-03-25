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
description: 了解如何在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 8cc0e549d502a2c7a8d8052ebe496a82e36b6648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117200"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="07518-103">在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="07518-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="07518-104">有时，Microsoft Teams 用户可能需要你向用户发送其音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="07518-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="07518-105">为此，可以单击用户属性下的 **"** 通过电子邮件发送会议信息"。</span><span class="sxs-lookup"><span data-stu-id="07518-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="07518-106">当你发送此电子邮件时，它将包含所有音频会议信息，包括：</span><span class="sxs-lookup"><span data-stu-id="07518-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="07518-107">用户的会议电话或拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="07518-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="07518-108">用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="07518-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="07518-109">下面是发送的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="07518-109">Here is an example of the email that is sent:</span></span>
  
![电话拨入式会议电子邮件的示例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="07518-111">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="07518-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="07518-113">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="07518-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="07518-114">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="07518-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="07518-115">在页面的顶部，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="07518-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="07518-116">在 **"音频会议"下**，单击 **"通过电子邮件发送会议信息"。**</span><span class="sxs-lookup"><span data-stu-id="07518-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="07518-117">此电子邮件的其他须知事项。</span><span class="sxs-lookup"><span data-stu-id="07518-117">What else should you know about this email?</span></span>

- <span data-ttu-id="07518-118">启用音频会议后，会向贵组织的用户发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="07518-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="07518-119">向其分配 **音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="07518-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="07518-120">手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="07518-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="07518-121">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="07518-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="07518-122">从 **中删除音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="07518-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="07518-123">当用户的音频会议提供商从 Microsoft 更改为其他提供商或"无 **"时**。</span><span class="sxs-lookup"><span data-stu-id="07518-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="07518-124">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="07518-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="07518-125">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="07518-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="07518-126">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="07518-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="07518-127">使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="07518-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="07518-128">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="07518-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="07518-129">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="07518-129">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="07518-130">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="07518-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="07518-131">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="07518-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="07518-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="07518-132">Related topics</span></span>

[<span data-ttu-id="07518-133">在 Microsoft 365 或 Office 365 中试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="07518-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)