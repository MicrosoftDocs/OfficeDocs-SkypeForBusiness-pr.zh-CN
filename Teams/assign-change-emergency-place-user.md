---
title: 分配，为用户更改紧急位置的位置
author: lanachin
ms.author: v-lanac
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
description: 在本文中，你将了解如何为你的组织中的用户分配或更改紧急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539509"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="2d98f-103">为用户分配或更改紧急位置的位置</span><span class="sxs-lookup"><span data-stu-id="2d98f-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="2d98f-104">为用户分配电话号码时，每个活动电话号码都必须有相关联的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="2d98f-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="2d98f-105">（当您在 Office 365 中获取电话号码或转移电话号码时，您可以关联该地址。）将该号码与紧急位置相关联时，您还可以添加一个位置，以便在一个物理位置内提供更准确的位置。</span><span class="sxs-lookup"><span data-stu-id="2d98f-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="2d98f-106">地点可以是用户所在的楼层、建筑物翼形或办公室号码。</span><span class="sxs-lookup"><span data-stu-id="2d98f-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="2d98f-107">对于给定的紧急位置，您可以拥有无限数量的位置，如果用户移动到其他 office 或建筑物，则可以更改位置。</span><span class="sxs-lookup"><span data-stu-id="2d98f-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="2d98f-108">例如，如果用户从楼层34移动到地板35。</span><span class="sxs-lookup"><span data-stu-id="2d98f-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="2d98f-109">若要了解如何获取通话计划和费用，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="2d98f-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="2d98f-110">你可以在 Microsoft 团队管理中心或通过使用 PowerShell 为用户分配或更改紧急位置的位置。</span><span class="sxs-lookup"><span data-stu-id="2d98f-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2d98f-111">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="2d98f-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2d98f-112">在 Microsoft 团队管理中心的左侧导航中，单击 "**语音**  >  **电话号码**"。</span><span class="sxs-lookup"><span data-stu-id="2d98f-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="2d98f-113">在 "**电话号码**" 页面上，单击 "**数字**" 选项卡，选择列表中的用户号码，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2d98f-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="2d98f-114">在 "**编辑**" 窗格的 "**紧急位置**" 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2d98f-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="2d98f-115">若要分配位置，请搜索位置或位置，然后在搜索结果中选择位置。</span><span class="sxs-lookup"><span data-stu-id="2d98f-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="2d98f-116">若要更改已分配给用户的位置，请单击 " **X** " 以删除现有位置和位置，然后单击 "搜索"，然后选择要分配的位置。</span><span class="sxs-lookup"><span data-stu-id="2d98f-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="2d98f-117">根据您是否想要使用电话号码信息向用户发送电子邮件，请关闭或打开**包含电话号码信息的电子邮件用户**。</span><span class="sxs-lookup"><span data-stu-id="2d98f-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="2d98f-118">默认情况下，此项处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="2d98f-118">By default, this is on.</span></span>

5. <span data-ttu-id="2d98f-119">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="2d98f-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="2d98f-120">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d98f-120">Using PowerShell</span></span>

<span data-ttu-id="2d98f-121">请参阅[设置-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="2d98f-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2d98f-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="2d98f-122">Related topics</span></span>

- [<span data-ttu-id="2d98f-123">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="2d98f-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="2d98f-124">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="2d98f-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="2d98f-125">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="2d98f-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="2d98f-126">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="2d98f-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="2d98f-127">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="2d98f-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="2d98f-128">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="2d98f-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
