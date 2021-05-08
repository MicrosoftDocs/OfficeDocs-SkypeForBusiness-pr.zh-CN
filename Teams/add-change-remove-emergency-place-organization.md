---
title: 添加、更改、删除紧急位置的位置
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
description: 了解如何在管理中心为组织添加、更改或删除紧急Microsoft Teams位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121500"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="c5a4e-103">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="c5a4e-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="c5a4e-104">根据组织中物理位置的数量，您可以为建筑物、楼层和办公室添加位置，以创建更具体的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="c5a4e-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="c5a4e-105">有关详细信息 [，请参阅管理](what-are-emergency-locations-addresses-and-call-routing.md) 紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="c5a4e-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="c5a4e-106">若要了解如何获取通话套餐及其费用，请参阅Teams[附加许可。](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="c5a4e-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="c5a4e-107">在管理中心或 PowerShell 中Microsoft Teams组织的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="c5a4e-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="c5a4e-108">向紧急位置添加位置</span><span class="sxs-lookup"><span data-stu-id="c5a4e-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c5a4e-109">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c5a4e-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c5a4e-110">在管理中心的左侧导航Microsoft Teams，单击 **"位置**  >  **""紧急地址"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="c5a4e-111">在列表中，单击要添加位置的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="c5a4e-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="c5a4e-112">在"**位置"选项卡** 上，单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="c5a4e-113">输入地点名称，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c5a4e-114">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5a4e-114">Using PowerShell</span></span>

<span data-ttu-id="c5a4e-115">请参阅[New-CsOnlineLisLocation。](/powershell/module/skype/new-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="c5a4e-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="c5a4e-116">更改紧急位置的位置</span><span class="sxs-lookup"><span data-stu-id="c5a4e-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c5a4e-117">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c5a4e-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c5a4e-118">在管理中心的左侧导航Microsoft Teams，单击 **"位置**  >  **""紧急地址"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="c5a4e-119">在列表中，单击要更改其位置的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="c5a4e-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="c5a4e-120">在"**位置**"选项卡上，选择要更改的位置，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="c5a4e-121">更新地点信息，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c5a4e-122">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5a4e-122">Using PowerShell</span></span>

<span data-ttu-id="c5a4e-123">请参阅[Set-CsOnlineLisLocation。](/powershell/module/skype/set-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="c5a4e-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="c5a4e-124">从紧急位置删除位置</span><span class="sxs-lookup"><span data-stu-id="c5a4e-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c5a4e-125">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c5a4e-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c5a4e-126">在管理中心的左侧导航Microsoft Teams，单击 **"位置**  >  **""紧急地址"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="c5a4e-127">在列表中，单击要删除位置的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="c5a4e-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="c5a4e-128">在"**位置**"选项卡上，选择要删除的位置，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="c5a4e-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c5a4e-129">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5a4e-129">Using PowerShell</span></span>

<span data-ttu-id="c5a4e-130">请参阅[Remove-CsOnlineLisLocation。](/powershell/module/skype/remove-csonlinelislocation)</span><span class="sxs-lookup"><span data-stu-id="c5a4e-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c5a4e-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="c5a4e-131">Related topics</span></span>

- [<span data-ttu-id="c5a4e-132">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="c5a4e-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="c5a4e-133">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="c5a4e-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="c5a4e-134">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="c5a4e-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)