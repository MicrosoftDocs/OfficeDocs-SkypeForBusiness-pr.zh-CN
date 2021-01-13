---
title: 为用户分配、更改紧急位置的位置
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 本文将了解如何为组织中用户分配或更改紧急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809522"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="d1ffc-103">为用户分配或更改紧急位置的位置</span><span class="sxs-lookup"><span data-stu-id="d1ffc-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="d1ffc-104">将电话号码分配给用户时，每个活动电话号码必须具有关联的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="d1ffc-105"> (在 Office 365 中获取电话号码时或转移电话号码时，将关联该地址。) 将号码与紧急位置关联时，还可以添加一个位置，在物理位置内提供更精确的位置。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="d1ffc-106">位置可以是用户所在的楼层、建筑物侧楼或办公室号码。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="d1ffc-107">对于给定的紧急位置，你可以有无限数量的地点，并且如果用户移动到其他办公室或建筑物，你可以更改位置。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="d1ffc-108">例如，如果用户从 34 楼移到 35 楼。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="d1ffc-109">若要了解如何获取通话套餐及其费用，请参阅 [Teams 附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="d1ffc-110">可以在 Microsoft Teams 管理中心或 PowerShell 中为用户分配或更改紧急位置的位置。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d1ffc-111">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="d1ffc-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="d1ffc-112">在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"语音**  >  **电话号码"。**</span><span class="sxs-lookup"><span data-stu-id="d1ffc-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d1ffc-113">在"**电话号码"** 页面上，单击"号码 **"选项卡，** 在列表中选择用户号码，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1ffc-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="d1ffc-114">在" **编辑** "窗格的 **"紧急位置"下**，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d1ffc-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="d1ffc-115">若要分配位置，请搜索位置或位置，然后在搜索结果中选择该位置。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="d1ffc-116">若要更改已分配给用户的位置，请单击 **"X"** 以删除现有位置和位置，搜索并选择要分配的位置。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="d1ffc-117">根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含电话号码 **信息的电子邮件用户**。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="d1ffc-118">默认情况下，此选项为打开状态。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-118">By default, this is on.</span></span>

5. <span data-ttu-id="d1ffc-119">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="d1ffc-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="d1ffc-120">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1ffc-120">Using PowerShell</span></span>

<span data-ttu-id="d1ffc-121">请参阅[Set-CsOnlineLisLocation。](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="d1ffc-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d1ffc-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="d1ffc-122">Related topics</span></span>

- [<span data-ttu-id="d1ffc-123">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="d1ffc-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="d1ffc-124">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="d1ffc-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="d1ffc-125">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="d1ffc-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="d1ffc-126">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="d1ffc-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="d1ffc-127">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="d1ffc-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="d1ffc-128">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="d1ffc-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
