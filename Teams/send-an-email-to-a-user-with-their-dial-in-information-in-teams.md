---
title: 在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: 在 Microsoft Teams 中向你的用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 505684bb2a73b60d1027c6cca6bbd7a306f48862
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344305"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="a0727-103">在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a0727-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="a0727-104">有时，Microsoft Teams 用户可能需要你向其发送电话音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="a0727-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="a0727-105">你可以单击用户的属性下的“**通过电子邮件发送会议信息**”来完成。</span><span class="sxs-lookup"><span data-stu-id="a0727-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="a0727-106">当你发送此电子邮件时，它将包含所有音频会议信息，包括：</span><span class="sxs-lookup"><span data-stu-id="a0727-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="a0727-107">用户的会议电话或拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="a0727-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="a0727-108">用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a0727-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="a0727-109">下面是发送的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="a0727-109">Here is an example of the email that is sent:</span></span>
  
![电话拨入式会议电子邮件](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="a0727-111">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a0727-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft 团队徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="a0727-113">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="a0727-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a0727-114">在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="a0727-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a0727-115">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a0727-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a0727-116">在 "**音频会议**" 下, 单击 "**通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="a0727-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="a0727-117">此电子邮件的其他须知事项。</span><span class="sxs-lookup"><span data-stu-id="a0727-117">What else should you know about this email?</span></span>

- <span data-ttu-id="a0727-118">在为您的组织中的用户启用音频会议后, 会向他们发送多封电子邮件:</span><span class="sxs-lookup"><span data-stu-id="a0727-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a0727-119">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="a0727-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a0727-120">当您手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="a0727-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a0727-121">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="a0727-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a0727-122">删除**音频会议**许可证后。</span><span class="sxs-lookup"><span data-stu-id="a0727-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a0727-123">当用户的音频会议提供商从 Microsoft 更改为另一个提供商或 "**无**" 时。</span><span class="sxs-lookup"><span data-stu-id="a0727-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a0727-124">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="a0727-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a0727-125">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="a0727-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a0727-p102">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a0727-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a0727-129">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0727-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a0727-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a0727-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a0727-131">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a0727-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="a0727-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0727-132">Related topics</span></span>

[<span data-ttu-id="a0727-133">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="a0727-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
