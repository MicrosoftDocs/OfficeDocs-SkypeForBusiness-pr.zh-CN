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
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: 在 Microsoft Teams 中向你的用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 9ebd650e487b4ef3108d50ecce31eea0a936b176
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012318"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="5d185-103">在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d185-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="5d185-104">有时 Microsoft 团队用户可能需要您向他们发送其音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="5d185-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="5d185-105">您可以通过单击**发送电子邮件的会议信息**下的用户属性来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5d185-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="5d185-106">当您发送此电子邮件时，它将包含的所有音频会议信息，包括：</span><span class="sxs-lookup"><span data-stu-id="5d185-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="5d185-107">用户的会议电话或拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="5d185-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="5d185-108">用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="5d185-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="5d185-109">下面是发送的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="5d185-109">Here is an example of the email that is sent:</span></span>
  
![电话拨入式会议电子邮件](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="5d185-111">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d185-111">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="5d185-112">在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="5d185-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5d185-113">在页面顶部，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="5d185-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5d185-114">在“**音频会议**”下，单击“**通过电子邮件发送会议信息**”。</span><span class="sxs-lookup"><span data-stu-id="5d185-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="5d185-115">你还应该了解有关此电子邮件的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="5d185-115">What else should you know about this email?</span></span>

- <span data-ttu-id="5d185-116">在为贵组织中的用户启用了音频会议后，会向他们发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="5d185-116">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="5d185-117">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="5d185-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="5d185-118">当你手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="5d185-118">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="5d185-119">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="5d185-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="5d185-120">删除用户的**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="5d185-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="5d185-121">当用户的音频会议提供商从 Microsoft 更改为另一个提供商或“**无**”时。</span><span class="sxs-lookup"><span data-stu-id="5d185-121">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="5d185-122">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="5d185-122">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="5d185-123">默认情况下，电子邮件发件人将从 Office 365，但您可以更改的电子邮件地址，并且可以使用 Windows PowerShell 显示名称。</span><span class="sxs-lookup"><span data-stu-id="5d185-123">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell.</span></span> <span data-ttu-id="5d185-124">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d185-124">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5d185-125">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="5d185-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5d185-p103">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5d185-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d185-129">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d185-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5d185-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5d185-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5d185-131">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d185-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="5d185-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d185-132">Related topics</span></span>

[<span data-ttu-id="5d185-133">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="5d185-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
