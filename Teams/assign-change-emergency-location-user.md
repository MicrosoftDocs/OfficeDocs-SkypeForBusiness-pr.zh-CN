---
title: 为用户分配或更改紧急位置
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
description: 本文介绍了如何为组织中用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102978"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="973e0-103">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="973e0-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="973e0-104">设置呼叫计划时，需要为每个电话号码或用户分配紧急位置。</span><span class="sxs-lookup"><span data-stu-id="973e0-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="973e0-105">在欧洲国家/地区，从 Microsoft 365 或 Office 365 获取紧急位置时，或者将电话号码转移到 Microsoft 365 或 Office 365 时，紧急位置与电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="973e0-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="973e0-106">在美国，紧急位置与分配给用户的电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="973e0-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="973e0-107">如果分配紧急地址的用户移动到新位置，则紧急地址可能会更改。</span><span class="sxs-lookup"><span data-stu-id="973e0-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="973e0-108">有关紧急地址和位置的信息，请参阅什么是紧急位置、地点和[呼叫路由？。](./what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="973e0-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](./what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="973e0-109">若要了解如何获取通话套餐及其费用，请参阅 [Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="973e0-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="973e0-110">可以在 Microsoft Teams 管理中心或 PowerShell 中为用户分配或更改紧急位置。</span><span class="sxs-lookup"><span data-stu-id="973e0-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="973e0-111">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="973e0-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="973e0-112">在 Microsoft Teams 管理中心的左侧导航栏中，单击"**语音**  >  **电话号码"。**</span><span class="sxs-lookup"><span data-stu-id="973e0-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="973e0-113">在"**电话号码"** 页面上，单击"号码 **"** 选项卡，在列表中选择用户号码，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="973e0-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="973e0-114">在" **编辑** "窗格的 **"紧急位置"下**，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="973e0-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="973e0-115">若要分配紧急位置，请搜索并选择紧急位置。</span><span class="sxs-lookup"><span data-stu-id="973e0-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="973e0-116">若要更改已分配给用户的紧急位置，请单击 **"X"** 删除现有位置，然后搜索并选择要分配的位置。</span><span class="sxs-lookup"><span data-stu-id="973e0-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="973e0-117">根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含 **电话号码信息的电子邮件用户**。</span><span class="sxs-lookup"><span data-stu-id="973e0-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="973e0-118">默认情况下，此选项为"打开"。</span><span class="sxs-lookup"><span data-stu-id="973e0-118">By default, this is on.</span></span>

5. <span data-ttu-id="973e0-119">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="973e0-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="973e0-120">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="973e0-120">Using PowerShell</span></span>

<span data-ttu-id="973e0-121">请参阅[Set-CsOnlineVoiceUser。](/powershell/module/skype/set-csonlinevoiceuser)</span><span class="sxs-lookup"><span data-stu-id="973e0-121">See [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="973e0-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="973e0-122">Related topics</span></span>

- [<span data-ttu-id="973e0-123">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="973e0-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="973e0-124">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="973e0-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="973e0-125">在组织中添加、更改或删除紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="973e0-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="973e0-126">为用户分配或更改紧急位置的地点</span><span class="sxs-lookup"><span data-stu-id="973e0-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="973e0-127">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="973e0-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="973e0-128">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="973e0-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)
- [<span data-ttu-id="973e0-129">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="973e0-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)