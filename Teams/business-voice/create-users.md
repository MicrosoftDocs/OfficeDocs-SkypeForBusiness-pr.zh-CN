---
title: 创建 Microsoft 365 用户、添加商务语音许可证，并分配电话号码
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16827d1b90ea07fcd84be286e03f3d3b22a55bd1
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868629"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="e27d5-102">创建商业语音用户并提供许可证，然后为其分配电话号码</span><span class="sxs-lookup"><span data-stu-id="e27d5-102">Create and license Business Voice users and assign them phone numbers</span></span>

<span data-ttu-id="e27d5-103">使用 :::no-loc text="Microsoft 365 Business Voice":::，需要一个拥有 :::no-loc text="Microsoft 365 Business Voice"::: 许可证的 :::no-loc text="Microsoft 365"::: 账户。</span><span class="sxs-lookup"><span data-stu-id="e27d5-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice"::: license.</span></span> <span data-ttu-id="e27d5-104">如果拥有账户和许可证，可向其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="e27d5-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="e27d5-105">创建用户并向其授予许可</span><span class="sxs-lookup"><span data-stu-id="e27d5-105">Create and license users</span></span>

<span data-ttu-id="e27d5-106">请按照[单独或批量添加用户](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)和[向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="e27d5-106">Follow the steps in [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="e27d5-107">在“**分配产品许可证**”窗格中，选择 **:::no-loc text="Microsoft 365 Business Voice":::**。</span><span class="sxs-lookup"><span data-stu-id="e27d5-107">In the **Assign product licenses** pane,  select **:::no-loc text="Microsoft 365 Business Voice":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="e27d5-108">向用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="e27d5-108">Assign phone numbers to users</span></span>

<span data-ttu-id="e27d5-109">创建用户并向其分配 :::no-loc text="Microsoft 365 Business Voice"::: 许可证后，可以向他们分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="e27d5-109">After you create users and assigned them a :::no-loc text="Microsoft 365 Business Voice"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="e27d5-110">对于需要拨打或接听外部电话号码的用户，需要一个未分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e27d5-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="e27d5-111">如果没有足够的未分配电话号码，请参阅本文后面的[获取更多电话号码](#get-more-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="e27d5-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="e27d5-112">转到 https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e27d5-112">Go to https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="e27d5-113">输入电话号码请求的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e27d5-113">Enter a name and description for the phone number request.</span></span>
3. <span data-ttu-id="e27d5-114">选择“**语音**” > “**电话号码**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-114">Select **Voice** > **Phone numbers**.</span></span>
4. <span data-ttu-id="e27d5-115">选择要分配给用户的电话号码，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-115">Select a phone number that you want to assign to a user, and then select **Edit**.</span></span>
5. <span data-ttu-id="e27d5-116">在“**编辑**”窗格中，在“**分配对象**”中输入要向其分配号码的用户名称。</span><span class="sxs-lookup"><span data-stu-id="e27d5-116">In the **Edit** panel, enter the name of the user that you want to assign the number to in **Assigned to**.</span></span> <span data-ttu-id="e27d5-117">然后选择“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="e27d5-118">对于“**紧急位置**”，输入用户所在的位置，然后选择“**应用**”</span><span class="sxs-lookup"><span data-stu-id="e27d5-118">For **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="e27d5-119">获取更多电话号码</span><span class="sxs-lookup"><span data-stu-id="e27d5-119">Get more phone numbers</span></span>

<span data-ttu-id="e27d5-120">如果没有足够的电话号码分配给新用户，可以获取更多电话号码。</span><span class="sxs-lookup"><span data-stu-id="e27d5-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="e27d5-121">订购的号码可用可能最长需要 24 小时。</span><span class="sxs-lookup"><span data-stu-id="e27d5-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="e27d5-122">转到 https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e27d5-122">Go to https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="e27d5-123">输入电话号码请求的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e27d5-123">Enter a name and description for the phone number request.</span></span>
3. <span data-ttu-id="e27d5-124">选择“**语音**” > “**电话号码**” > “**添加**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="e27d5-125">选择电话号码所在国家或地区。</span><span class="sxs-lookup"><span data-stu-id="e27d5-125">Choose the country or region for the phone number.</span></span>
5. <span data-ttu-id="e27d5-126">对于“**号码类型**”，选择“**用户（订阅者）**”</span><span class="sxs-lookup"><span data-stu-id="e27d5-126">For **Number type**, select **User (subscriber)**.</span></span>
6. <span data-ttu-id="e27d5-127">对于“**位置**”，搜索用户的位置并选中它。</span><span class="sxs-lookup"><span data-stu-id="e27d5-127">For **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="e27d5-128">还可选择“**添加位置**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="e27d5-129">选择一个区号，输入需要的电话号码，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-129">Choose an area code, enter the number of phone numbers that you need, and then select **Next**.</span></span>
8. <span data-ttu-id="e27d5-130">等待保留电话号码，然后查看获得的号码。</span><span class="sxs-lookup"><span data-stu-id="e27d5-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="e27d5-131">如果一切就绪，选择“**下单**”并随后点击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="e27d5-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>
