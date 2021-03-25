---
title: 设置包含在邀请中的电话号码
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
- seo-marvel-mar2020
description: 按照以下步骤创建默认电话号码，让呼叫者加入 Microsoft Teams 会议。
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117170"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="6253a-103">在 Microsoft Teams 中设置包含在邀请中的电话号码</span><span class="sxs-lookup"><span data-stu-id="6253a-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="6253a-104">Microsoft 365 和 Office 365 中的音频会议使贵组织的用户能够创建 Microsoft Teams 会议，然后允许用户使用电话拨入这些会议。</span><span class="sxs-lookup"><span data-stu-id="6253a-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="6253a-105">会议桥为你的组织提供了一套拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="6253a-106">它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6253a-107">会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="6253a-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="6253a-108">新用户的会议邀请中包含的电话号码的初始分配</span><span class="sxs-lookup"><span data-stu-id="6253a-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="6253a-109">已启用音频会议的用户的会议邀请中包含的电话号码由默认会议收费电话号码和默认会议免费电话号码用户设置定义。</span><span class="sxs-lookup"><span data-stu-id="6253a-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="6253a-110">每个设置指定将在给定用户的会议邀请中包括哪些收费和免费号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="6253a-111">如上所述，每个会议邀请都包含一个收费电话号码、一个可选的免费电话号码和一个链接，该链接可打开可用于加入给定会议的所有拨入电话号码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="6253a-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="6253a-112">对于新用户，默认会议收费号码是根据用户启用音频会议服务的 Microsoft 365 管理中心中设置的使用位置分配的。</span><span class="sxs-lookup"><span data-stu-id="6253a-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="6253a-113">如果会议网桥中的收费号码与用户的国家/地区匹配，该号码将自动分配为用户的默认收费号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="6253a-114">如果没有，则定义为会议网桥默认收费号码的号码将分配为用户的默认收费号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="6253a-115">为用户启用音频会议服务后，租户管理员随时都可以从用户的初始值更改用户的默认收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="6253a-116">设置或更改会议组织者或用户的默认音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="6253a-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="6253a-117">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="6253a-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="6253a-118">必须是 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="6253a-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="6253a-119">请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="6253a-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="6253a-120">登录到 Microsoft Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6253a-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="6253a-121">在左侧导航栏中，单击"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="6253a-121">In the left navigation, click **Users**.</span></span>

    ![显示 Microsoft Teams 管理中心中的选择用户](media/Admin-users.png)

3. <span data-ttu-id="6253a-123">从可用用户列表中单击用户名。</span><span class="sxs-lookup"><span data-stu-id="6253a-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="6253a-124">在 **音频会议** 旁边，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="6253a-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![单击"音频会议"旁边的"编辑"](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="6253a-126">使用 **"收费电话号码** " **或"免费** 电话号码"字段输入用户号码。</span><span class="sxs-lookup"><span data-stu-id="6253a-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6253a-127">更改用户的音频会议设置时，必须更新定期和将来的 Microsoft Teams 会议并发送给与会者。</span><span class="sxs-lookup"><span data-stu-id="6253a-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="6253a-128">想要使用Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6253a-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="6253a-129">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="6253a-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6253a-130">使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="6253a-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="6253a-131">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="6253a-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="6253a-132">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6253a-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="6253a-133">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6253a-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="6253a-134">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="6253a-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6253a-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="6253a-135">Related topics</span></span>

[<span data-ttu-id="6253a-136">在 Microsoft 365 或 Office 365 中试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="6253a-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="6253a-137">更改音频会议网桥中的电话号码</span><span class="sxs-lookup"><span data-stu-id="6253a-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)