---
title: 添加、更改、删除紧急位置的位置
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
description: 了解如何在 Microsoft 团队管理中心中为你的组织添加、更改或删除紧急位置的位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232493"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="ee1a3-103">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="ee1a3-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="ee1a3-104">根据您的组织中的物理位置数，您可以添加建筑物、楼层和办事处的位置，以创建更具体的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="ee1a3-105">有关详细信息，请参阅[管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="ee1a3-106">若要了解如何获取呼叫计划以及成本，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="ee1a3-107">可在 Microsoft 团队管理中心或通过使用 PowerShell 管理你的组织的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="ee1a3-108">将地点添加到紧急位置</span><span class="sxs-lookup"><span data-stu-id="ee1a3-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ee1a3-109">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="ee1a3-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ee1a3-110">在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ee1a3-111">在列表中，单击要为其添加位置的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="ee1a3-112">在 "**位置**" 选项卡上，单击 "**添加位置**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="ee1a3-113">输入一个位置名称，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ee1a3-114">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee1a3-114">Using PowerShell</span></span>

<span data-ttu-id="ee1a3-115">请参阅[新-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="ee1a3-116">更改紧急位置的位置</span><span class="sxs-lookup"><span data-stu-id="ee1a3-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ee1a3-117">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="ee1a3-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ee1a3-118">在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ee1a3-119">在列表中，单击要更改位置的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="ee1a3-120">在 "**位置**" 选项卡上，选择要更改的位置，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="ee1a3-121">更新位置信息，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ee1a3-122">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee1a3-122">Using PowerShell</span></span>

<span data-ttu-id="ee1a3-123">请参阅[设置-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="ee1a3-124">从紧急位置删除位置</span><span class="sxs-lookup"><span data-stu-id="ee1a3-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ee1a3-125">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="ee1a3-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ee1a3-126">在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="ee1a3-127">在列表中，单击要删除其位置的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="ee1a3-128">在 "**位置**" 选项卡上，选择要删除的位置，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ee1a3-129">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee1a3-129">Using PowerShell</span></span>

<span data-ttu-id="ee1a3-130">请参阅[删除-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="ee1a3-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ee1a3-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="ee1a3-131">Related topics</span></span>

- [<span data-ttu-id="ee1a3-132">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="ee1a3-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ee1a3-133">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="ee1a3-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ee1a3-134">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="ee1a3-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
