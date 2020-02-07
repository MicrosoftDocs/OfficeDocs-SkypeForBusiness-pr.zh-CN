---
title: 在 Microsoft Teams 中设置包含在邀请中的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '获取为呼叫者创建默认电话号码以加入 Microsoft 团队会议的步骤。 '
ms.openlocfilehash: b5a43b0987160b87ac4a6e25b10ae6d850612ac1
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845233"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="42c6e-103">在 Microsoft Teams 中设置包含在邀请中的电话号码</span><span class="sxs-lookup"><span data-stu-id="42c6e-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="42c6e-104">Office 365 中的音频会议使组织中的用户可以创建 Microsoft 团队会议，然后允许用户使用手机拨入这些会议。</span><span class="sxs-lookup"><span data-stu-id="42c6e-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="42c6e-105">会议桥为你的组织提供了一套拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="42c6e-106">它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42c6e-107">会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="42c6e-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="42c6e-108">新用户的会议邀请中包含的电话号码的初始分配</span><span class="sxs-lookup"><span data-stu-id="42c6e-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="42c6e-109">启用音频会议的用户的会议邀请中包含的电话号码由默认会议收费电话号码和默认会议免费电话号码用户设置定义。</span><span class="sxs-lookup"><span data-stu-id="42c6e-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="42c6e-110">每个设置指定用户的会议邀请中将包含哪些收费电话号码和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="42c6e-111">如上所述，每个会议邀请包含一个收费号码，一个可选的免费电话号码和一个链接，用于打开所有拨入电话号码的完整列表，这些电话号码可用于加入给定的会议。</span><span class="sxs-lookup"><span data-stu-id="42c6e-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="42c6e-112">对于新用户，根据为音频会议服务启用用户时在用户的 Office 365 配置文件中设置的国家/地区分配默认的会议收费号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="42c6e-113">如果在会议桥中有收费号码与用户所在的国家/地区相匹配，则该号码将自动分配为用户的默认收费号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="42c6e-114">如果没有，则定义为该会议桥的默认收费号码的号码将被分配为用户的默认收费号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="42c6e-115">用户启用音频会议服务后，租户管理员可以随时从其初始值更改用户的默认收费电话号码和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="42c6e-116">设置或更改会议组织者或用户的默认音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="42c6e-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="42c6e-117">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="42c6e-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="42c6e-118">在左侧导航中，单击 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="42c6e-118">In the left navigation, click **Users**.</span></span>

    ![显示在 Microsoft 团队管理中心中选择用户](media/teams-set-phone-numbers-on-invites-image1.png)

2. <span data-ttu-id="42c6e-120">从可用用户列表中单击该用户名。</span><span class="sxs-lookup"><span data-stu-id="42c6e-120">Click the user name from the list of available users.</span></span>

3. <span data-ttu-id="42c6e-121">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="42c6e-121">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![单击 "音频会议" 旁边的 "编辑"](media/teams-set-phone-numbers-on-invites-image3.png)

4. <span data-ttu-id="42c6e-123">使用 "**收费电话号码**" 或 "免费**电话号码**" 字段输入用户的号码。</span><span class="sxs-lookup"><span data-stu-id="42c6e-123">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="42c6e-124">更改用户的音频会议设置时，必须更新定期和将来的 Microsoft 团队会议，并将其发送给与会者。</span><span class="sxs-lookup"><span data-stu-id="42c6e-124">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="42c6e-125">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="42c6e-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="42c6e-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="42c6e-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="42c6e-129">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="42c6e-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="42c6e-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="42c6e-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="42c6e-131">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="42c6e-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="42c6e-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="42c6e-132">Related topics</span></span>

[<span data-ttu-id="42c6e-133">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="42c6e-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="42c6e-134">更改音频会议网桥中的电话号码</span><span class="sxs-lookup"><span data-stu-id="42c6e-134">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
