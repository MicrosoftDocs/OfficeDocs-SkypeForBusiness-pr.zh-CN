---
title: 设置的电话号码包含在邀请中 Microsfot 团队
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '获取创建默认的电话号码的呼叫者加入 Microsfot 团队会议的步骤。 '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882957"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="f21b4-103">设置的电话号码包含在邀请中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f21b4-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="f21b4-104">Office 365 中的音频会议，组织中的用户创建的 Microsoft 团队会议，然后允许这些会议使用电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="f21b4-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="f21b4-105">在 Office 365 中，您可以使用 Microsoft 音频会议网桥或位于由已批准的音频会议提供商 (ACP) 的第三方音频会议桥的选择。</span><span class="sxs-lookup"><span data-stu-id="f21b4-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="f21b4-106">会议桥为你的组织提供了一套拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="f21b4-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="f21b4-107">它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。</span><span class="sxs-lookup"><span data-stu-id="f21b4-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f21b4-108">会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="f21b4-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="f21b4-109">设置或更改会议组织者或用户的默认音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="f21b4-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="f21b4-110">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="f21b4-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![显示选择的 Microsoft 团队和 Skype 的业务管理中心中的用户](media/teamsselectusers.png)

2. <span data-ttu-id="f21b4-112">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f21b4-112">At the top of the page, click **Edit**.</span></span>

    ![单击编辑中的 Microsoft 团队和 Skype 的业务管理中心](media/teamsedituser.png)

3. <span data-ttu-id="f21b4-114">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f21b4-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![单击编辑旁边音频会议](media/teamseditaudioconf.png)

4. <span data-ttu-id="f21b4-116">使用**收费电话号码**或**免费电话号码**字段，用户输入的数字。</span><span class="sxs-lookup"><span data-stu-id="f21b4-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f21b4-117">更改用户的音频会议设置时，必须更新定期和将来的 Microsoft 团队会议，并将其发送给与会者中。</span><span class="sxs-lookup"><span data-stu-id="f21b4-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="f21b4-118">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="f21b4-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="f21b4-p103">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f21b4-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f21b4-122">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f21b4-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f21b4-123">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f21b4-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f21b4-124">有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f21b4-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="f21b4-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="f21b4-125">Related topics</span></span>

[<span data-ttu-id="f21b4-126">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="f21b4-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
