---
title: 创建 Microsoft 365 用户、添加 Microsoft 365 商务语音许可证，并分配电话号码
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: a789300c7b7b646ab7b7d288ce5679b6fe3dfff2
ms.sourcegitcommit: 000957709b841ce55a6813ccc2fbe745b1a9295b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2019
ms.locfileid: "39218019"
---
# <a name="create-and-license-users-and-assign-phone-numbers-to-them"></a><span data-ttu-id="499bd-102">创建用户并为其授予许可并分配电话号码</span><span class="sxs-lookup"><span data-stu-id="499bd-102">Create and license users and assign phone numbers to them</span></span>

<span data-ttu-id="499bd-103">若要使用 :::no-loc text="Microsoft 365 Business Voice":::，用户需要具有 :::no-loc text="Microsoft 365 Business Voice with SMS"::: 许可证的 :::no-loc text="Microsoft 365"::: 帐户。</span><span class="sxs-lookup"><span data-stu-id="499bd-103">To use Microsoft 365 Business Voice, a user needs an Microsoft 365 account with a Microsoft 365 Business Voice with SMS license.</span></span> <span data-ttu-id="499bd-104">在创建具有 :::no-loc text="Microsoft 365 Business Voice with SMS"::: 许可证的帐户后，可以向其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="499bd-104">After an account has been created with a Microsoft 365 Business Voice with SMS license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="499bd-105">创建用户并向其授予许可</span><span class="sxs-lookup"><span data-stu-id="499bd-105">Create and license users</span></span>

1. <span data-ttu-id="499bd-106">按照[将用户单独或批量添加到 :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users) 中的步骤添加一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="499bd-106">Follow the steps in Add users individually or in bulk to Office 365 to add one or more users.</span></span>
2. <span data-ttu-id="499bd-107">在“分配产品许可证”窗格中，确保选择 \*\*:::no-loc text="Microsoft 365 Business Voice with SMS":::\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="499bd-107">In the Assign product licenses pane, be sure to select Microsoft 365 Business Voice with SMS.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="499bd-108">向用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="499bd-108">Assign phone numbers to users</span></span>

<span data-ttu-id="499bd-109">在创建用户并向其分配 :::no-loc text="Microsoft 365 Business Voice with SMS"::: 许可证后，可以向其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="499bd-109">After users have been created and assigned a Microsoft 365 Business Voice with SMS license, you can assign phone numbers to them.</span></span> <span data-ttu-id="499bd-110">每个需要电话号码的用户需要一个未分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="499bd-110">You need one unassigned phone number for each user that needs one.</span></span> <span data-ttu-id="499bd-111">如果没有足够的未分配电话号码，请参阅本文后面的[获取更多电话号码](#get-more-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="499bd-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="499bd-112">转到 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="499bd-112">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="499bd-113">输入电话号码请求的名称和说明</span><span class="sxs-lookup"><span data-stu-id="499bd-113">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="499bd-114">选择“**语音**” > “**电话号码**”</span><span class="sxs-lookup"><span data-stu-id="499bd-114">Select **Voice** > **Phone numbers**</span></span>
4. <span data-ttu-id="499bd-115">选择要分配给用户的电话号码并选择“**编辑**”</span><span class="sxs-lookup"><span data-stu-id="499bd-115">Select a phone number you want to assign to a user and select **Edit**</span></span>
5. <span data-ttu-id="499bd-116">在“**编辑**”面板中，在“**分配对象**”中输入要向其分配号码的用户名称，然后选择“**分配**”</span><span class="sxs-lookup"><span data-stu-id="499bd-116">In the **Edit** panel, enter the name of the user you want to assign the number to in **Assigned to** and select **Assign**</span></span>
6. <span data-ttu-id="499bd-117">在“**紧急位置**”中，输入用户所在的位置，然后选择“**应用**”</span><span class="sxs-lookup"><span data-stu-id="499bd-117">In **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>


## <a name="get-more-phone-numbers"></a><span data-ttu-id="499bd-118">获取更多电话号码</span><span class="sxs-lookup"><span data-stu-id="499bd-118">Get more phone numbers</span></span>

<span data-ttu-id="499bd-119">如果没有足够的电话号码分配给新用户，可以获取更多电话号码。</span><span class="sxs-lookup"><span data-stu-id="499bd-119">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="499bd-120">下订单后，可能需要最多 24 小时才可获取这些号码。</span><span class="sxs-lookup"><span data-stu-id="499bd-120">After you've placed your order, it might take up to 24 hours for the numbers to become available.</span></span>

1. <span data-ttu-id="499bd-121">转到 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="499bd-121">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="499bd-122">输入电话号码请求的名称和说明</span><span class="sxs-lookup"><span data-stu-id="499bd-122">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="499bd-123">选择“**语音**” > “**电话号码**”，然后选择“**添加**”</span><span class="sxs-lookup"><span data-stu-id="499bd-123">Select **Voice** > **Phone numbers**, and then **Add**</span></span>
4. <span data-ttu-id="499bd-124">选择要创建电话号码的国家或地区</span><span class="sxs-lookup"><span data-stu-id="499bd-124">Choose the country or region where the phone number should be created</span></span>
5. <span data-ttu-id="499bd-125">在“**号码类型**”中，选择“**用户（订阅者）**”</span><span class="sxs-lookup"><span data-stu-id="499bd-125">In **Number type**, select **User (subscriber)**</span></span>
6. <span data-ttu-id="499bd-126">在“**位置**”中，搜索用户的位置并选中它。</span><span class="sxs-lookup"><span data-stu-id="499bd-126">In **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="499bd-127">如果需要添加新位置，请选择“**添加位置**”。</span><span class="sxs-lookup"><span data-stu-id="499bd-127">If you need to add a new location, select **Add a location**</span></span>
7. <span data-ttu-id="499bd-128">选择一个区号，输入要获取的电话号码，然后单击“**下一步**”</span><span class="sxs-lookup"><span data-stu-id="499bd-128">Choose an area code, enter the number of phone numbers to get, and then click **Next**</span></span>
8. <span data-ttu-id="499bd-129">等待保留电话号码，查看所选号码，如果所有内容看起来正确，请选择“**下订单**”，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="499bd-129">Wait for the phone numbers to be reserved, review the numbers chosen and then, if everything looks ok, select **Place order** and then **Finish**.</span></span>

