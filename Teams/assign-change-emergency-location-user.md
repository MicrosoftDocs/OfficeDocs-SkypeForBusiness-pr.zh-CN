---
title: 为用户分配或更改紧急位置
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
description: 在本文中，你将了解如何为你的组织中的用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232473"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="d3325-103">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="d3325-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="d3325-104">设置呼叫计划时，您需要为每个电话号码或用户分配紧急地点。</span><span class="sxs-lookup"><span data-stu-id="d3325-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="d3325-105">在欧洲国家，当您从 Office 365 获取电话号码时，或将电话号码转移到 Office 365 时，紧急位置将与电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="d3325-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="d3325-106">在美国，紧急位置与分配给用户的电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="d3325-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="d3325-107">如果分配的用户移动到新位置，则可以更改紧急地址。</span><span class="sxs-lookup"><span data-stu-id="d3325-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="d3325-108">有关紧急地址和位置的详细信息，请参阅[管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="d3325-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="d3325-109">若要了解如何获取呼叫计划以及成本，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d3325-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="d3325-110">你可以在 Microsoft 团队管理中心或通过使用 PowerShell 为用户分配或更改紧急位置。</span><span class="sxs-lookup"><span data-stu-id="d3325-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d3325-111">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="d3325-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="d3325-112">在 Microsoft 团队管理中心的左侧导航中，单击 "**语音**  >  **电话号码**"。</span><span class="sxs-lookup"><span data-stu-id="d3325-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d3325-113">在 "**电话号码**" 页面上，选择列表中的一个用户号码，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d3325-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="d3325-114">在 "**编辑**" 窗格的 "**紧急位置**" 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d3325-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="d3325-115">若要分配紧急位置，请搜索，然后选择紧急位置。</span><span class="sxs-lookup"><span data-stu-id="d3325-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="d3325-116">若要更改已分配给用户的紧急位置，请单击 " **X** " 以删除现有位置，然后搜索并选择要分配的位置。</span><span class="sxs-lookup"><span data-stu-id="d3325-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="d3325-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d3325-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="d3325-118">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3325-118">Using PowerShell</span></span>

<span data-ttu-id="d3325-119">请参阅[设置-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)。</span><span class="sxs-lookup"><span data-stu-id="d3325-119">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="d3325-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="d3325-120">Related topics</span></span>

- [<span data-ttu-id="d3325-121">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="d3325-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="d3325-122">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="d3325-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="d3325-123">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="d3325-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="d3325-124">为用户分配或更改紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="d3325-124">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="d3325-125">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="d3325-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="d3325-126">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="d3325-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="d3325-127">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="d3325-127">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
