---
title: 添加、更改、删除紧急位置
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
description: '了解如何在 Microsoft 团队管理中心添加、更改或删除你的组织的紧急位置。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bed76fdfff2a6af2dabb3eef5c01dcfb39f422a
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539459"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="3ee12-103">添加、 更改或删除您的组织紧急地点</span><span class="sxs-lookup"><span data-stu-id="3ee12-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="3ee12-104">紧急位置必须与电话号码相关联，但是如果发生这种情况，国家和地区之间可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="3ee12-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="3ee12-105">例如，在美国，当您为用户分配电话号码时，您需要关联紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3ee12-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="3ee12-106">在英国，当您获得 Office 365 中的电话号码或从您的当前服务提供商转移电话号码时，您需要将紧急位置与电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="3ee12-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="3ee12-107">无论您所在的国家或地区如何，您都可以将一个或多个地点添加到紧急地点，并删除紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3ee12-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="3ee12-108">根据您的组织中的物理位置数，您可以为建筑物、楼层和办事处创建场所。</span><span class="sxs-lookup"><span data-stu-id="3ee12-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="3ee12-109">请参阅[管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="3ee12-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="3ee12-110">若要了解如何获取呼叫计划以及成本，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="3ee12-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="3ee12-111">可在 Microsoft 团队管理中心或通过使用 PowerShell 管理你的组织的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3ee12-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="3ee12-112">添加紧急位置</span><span class="sxs-lookup"><span data-stu-id="3ee12-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ee12-113">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3ee12-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3ee12-114">在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。</span><span class="sxs-lookup"><span data-stu-id="3ee12-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="3ee12-115">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3ee12-115">Click **Add**.</span></span>
3. <span data-ttu-id="3ee12-116">输入位置的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="3ee12-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="3ee12-117">选择国家或地区，然后输入地址。</span><span class="sxs-lookup"><span data-stu-id="3ee12-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ee12-118">在比利时、法国、德国、爱尔兰、荷兰和西班牙，请务必了解要在 Office 365 中成功激活电话号码，在紧急位置（用于获取号码）中设置的地址必须与电话号码的区号匹配。</span><span class="sxs-lookup"><span data-stu-id="3ee12-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>
5. <span data-ttu-id="3ee12-119">如果找不到地址，而您想要手动编辑地址，请打开 "**手动编辑地址"**。</span><span class="sxs-lookup"><span data-stu-id="3ee12-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="3ee12-120">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3ee12-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3ee12-121">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ee12-121">Using PowerShell</span></span>

<span data-ttu-id="3ee12-122">请参阅[新-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)。</span><span class="sxs-lookup"><span data-stu-id="3ee12-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="3ee12-123">更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="3ee12-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ee12-124">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3ee12-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3ee12-125">在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。</span><span class="sxs-lookup"><span data-stu-id="3ee12-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="3ee12-126">在列表中，选择要更改的位置，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="3ee12-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="3ee12-127">进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="3ee12-127">Make the changes you want.</span></span>
4. <span data-ttu-id="3ee12-128">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3ee12-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ee12-129">只有在地址未经验证时，才能更改位置的地址信息。</span><span class="sxs-lookup"><span data-stu-id="3ee12-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="3ee12-130">如果地址已验证，并且您需要更改地址，请删除该位置，然后使用正确的地址创建新位置。</span><span class="sxs-lookup"><span data-stu-id="3ee12-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3ee12-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ee12-131">Using PowerShell</span></span>

<span data-ttu-id="3ee12-132">请参阅[设置-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)。</span><span class="sxs-lookup"><span data-stu-id="3ee12-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="3ee12-133">删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="3ee12-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3ee12-134">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3ee12-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3ee12-135">在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。</span><span class="sxs-lookup"><span data-stu-id="3ee12-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="3ee12-136">在列表中，选择要删除的位置，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="3ee12-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3ee12-137">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ee12-137">Using PowerShell</span></span>

<span data-ttu-id="3ee12-138">请参阅[删除-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)。</span><span class="sxs-lookup"><span data-stu-id="3ee12-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ee12-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ee12-139">Related topics</span></span>

- [<span data-ttu-id="3ee12-140">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="3ee12-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="3ee12-141">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="3ee12-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="3ee12-142">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="3ee12-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="3ee12-143">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="3ee12-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
