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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '获取创建默认的电话号码的呼叫者加入 Microsoft 团队会议的步骤。 '
ms.openlocfilehash: 8cbe7a88d1fcb857ce94a95b2a9af7a159ccef5a
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754556"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="9ba64-103">在 Microsoft Teams 中设置包含在邀请中的电话号码</span><span class="sxs-lookup"><span data-stu-id="9ba64-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="9ba64-104">Office 365 中的音频会议，组织中的用户创建的 Microsoft 团队会议，然后允许这些会议使用电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="9ba64-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="9ba64-105">会议桥为你的组织提供了一套拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="9ba64-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="9ba64-106">它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。</span><span class="sxs-lookup"><span data-stu-id="9ba64-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ba64-107">会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="9ba64-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="9ba64-108">初始工作分配的会议中包含的电话号码邀请新用户</span><span class="sxs-lookup"><span data-stu-id="9ba64-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="9ba64-109">获取包含在会议中的电话号码邀请启用的默认会议收费电话号码和默认会议免费电话号码用户的设置来定义要进行音频会议的用户。</span><span class="sxs-lookup"><span data-stu-id="9ba64-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="9ba64-110">每个设置指定的收费和免费电话号码将包含给定用户的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="9ba64-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="9ba64-111">如上所述，每个会议邀请将包含一个收费电话号码、 一个可选的免费电话号码和打开可用于加入给定的会议的所有电话拨入电话号码的完整列表的链接。</span><span class="sxs-lookup"><span data-stu-id="9ba64-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="9ba64-112">为新用户，基于时设置的用户的 Office 365 配置文件中为用户启用音频会议服务的国家/地区分配的默认会议收费电话号码。</span><span class="sxs-lookup"><span data-stu-id="9ba64-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="9ba64-113">如果没有匹配的用户的国家/地区的会议桥收费电话号码，将自动将该号码分配为用户的默认收费电话号码。</span><span class="sxs-lookup"><span data-stu-id="9ba64-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="9ba64-114">如果没有一个，定义为默认收费电话号码的会议桥的号码将分配为默认收费电话号码的用户。</span><span class="sxs-lookup"><span data-stu-id="9ba64-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="9ba64-115">一旦用户启用了音频会议服务，默认收费和免费电话号码的用户可以更改由租户管理员从其初始值任何时刻。</span><span class="sxs-lookup"><span data-stu-id="9ba64-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="9ba64-116">设置或更改会议组织者或用户的默认音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="9ba64-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="9ba64-117">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="9ba64-117">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9ba64-118">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="9ba64-118">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![在管理中心中的 Microsoft 团队选择用户的显示](media/teamsselectusers.png)

2. <span data-ttu-id="9ba64-120">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9ba64-120">At the top of the page, click **Edit**.</span></span>

    ![单击编辑中的 Microsoft 团队管理中心](media/teamsedituser.png)

3. <span data-ttu-id="9ba64-122">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9ba64-122">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![单击编辑旁边音频会议](media/teamseditaudioconf.png)

4. <span data-ttu-id="9ba64-124">使用**收费电话号码**或**免费电话号码**字段，用户输入的数字。</span><span class="sxs-lookup"><span data-stu-id="9ba64-124">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9ba64-125">更改用户的音频会议设置时，必须更新定期和将来的 Microsoft 团队会议，并将其发送给与会者中。</span><span class="sxs-lookup"><span data-stu-id="9ba64-125">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="9ba64-126">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="9ba64-126">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="9ba64-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="9ba64-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9ba64-130">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ba64-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9ba64-131">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="9ba64-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9ba64-132">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="9ba64-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="9ba64-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="9ba64-133">Related topics</span></span>

[<span data-ttu-id="9ba64-134">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="9ba64-134">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
