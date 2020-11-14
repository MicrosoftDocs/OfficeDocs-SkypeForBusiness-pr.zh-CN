---
title: 为用户获取电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: '了解如何为团队获取新的、移植或转移现有号码，以及如何向用户显示所做的更改。 '
ms.openlocfilehash: f2028a4d7b49560ff426d83241da8f1f7c3243d3
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030458"
---
# <a name="getting-phone-numbers-for-your-users"></a><span data-ttu-id="ca07f-103">为用户获取电话号码</span><span class="sxs-lookup"><span data-stu-id="ca07f-103">Getting phone numbers for your users</span></span>

<span data-ttu-id="ca07f-104">在您可以将组织中的用户设置为拨打和接收电话呼叫之前，您必须为他们获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="ca07f-104">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>
  
<span data-ttu-id="ca07f-105">有三种方法可以获取用户号码：</span><span class="sxs-lookup"><span data-stu-id="ca07f-105">There are three ways to get user numbers:</span></span>

- <span data-ttu-id="ca07f-106">**使用 Microsoft 团队管理中心。**</span><span class="sxs-lookup"><span data-stu-id="ca07f-106">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="ca07f-107">对于某些国家和地区，你可以使用 Microsoft 团队管理中心为你的用户获取数字。</span><span class="sxs-lookup"><span data-stu-id="ca07f-107">For some countries and regions, you can get numbers for your users using the Microsoft Teams admin center.</span></span> <span data-ttu-id="ca07f-108">请参阅 [为您的用户获取新电话号码](#get-new-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="ca07f-108">See [Get new phone numbers for your users](#get-new-phone-numbers-for-your-users).</span></span>

- <span data-ttu-id="ca07f-109">**转网现有的号码。**</span><span class="sxs-lookup"><span data-stu-id="ca07f-109">**Port your existing numbers.**</span></span> <span data-ttu-id="ca07f-110">您可以从当前服务提供商或电话运营商处移植或转移现有号码。</span><span class="sxs-lookup"><span data-stu-id="ca07f-110">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="ca07f-111">如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="ca07f-111">See [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="ca07f-112">**使用新号码的请求表单。**</span><span class="sxs-lookup"><span data-stu-id="ca07f-112">**Use a request form for new numbers.**</span></span> <span data-ttu-id="ca07f-113">有时 (取决于您所在的国家或地区) 你无法使用 Microsoft 团队管理中心获取新电话号码，或者你将需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="ca07f-113">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams Admin Center or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="ca07f-114">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="ca07f-114">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca07f-115">如果您需要帮助为您的组织设置电话号码，请 [联系支持人员联系以获取商业产品-管理员帮助 (https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online 。</span><span class="sxs-lookup"><span data-stu-id="ca07f-115">If you need help setting up phone numbers for your organization, please [contact Support Contact for Business Products - Admin Help(https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online.</span></span>
  
## <a name="get-new-phone-numbers-for-your-users"></a><span data-ttu-id="ca07f-116">为用户获取新电话号码</span><span class="sxs-lookup"><span data-stu-id="ca07f-116">Get new phone numbers for your users</span></span>

<span data-ttu-id="ca07f-117">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="ca07f-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="ca07f-118">您必须是团队服务管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="ca07f-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="ca07f-119">请参阅 [使用团队管理员角色管理团队](https://docs.microsoft.com/microsoftteams/using-admin-roles) ，了解如何获取管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="ca07f-119">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="ca07f-120">转到 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="ca07f-120">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="ca07f-121">在左侧导航中，转到 " **语音**  >  **电话号码** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="ca07f-121">In the left navigation, go to **Voice** > **Phone numbers** , and then click **Add**.</span></span>
3. <span data-ttu-id="ca07f-122">输入订单的名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="ca07f-122">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="ca07f-123">在 "位置和数量" 页面上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ca07f-123">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="ca07f-124">在 " **国家或地区** " 下，选择一个国家或地区。</span><span class="sxs-lookup"><span data-stu-id="ca07f-124">Under **Country or region** , select a country or region.</span></span>
    2. <span data-ttu-id="ca07f-125">在 " **号码类型** " 下，选择 " **用户 (订阅者")** 。</span><span class="sxs-lookup"><span data-stu-id="ca07f-125">Under **Number type** , select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="ca07f-126">在 " **位置** " 下，选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="ca07f-126">Under **Location** , select a location.</span></span> <span data-ttu-id="ca07f-127">如果需要创建新位置，请单击 " **添加位置** "。</span><span class="sxs-lookup"><span data-stu-id="ca07f-127">If you need to create a new location, click **Add a location**.</span></span>
    4. <span data-ttu-id="ca07f-128">在 " **区域代码** " 下，选择区号。</span><span class="sxs-lookup"><span data-stu-id="ca07f-128">Under **Area code** , select an area code.</span></span>
    5. <span data-ttu-id="ca07f-129">在 " **数量** " 下，输入您的组织所需的号码数，然后单击 " **下一步** " 以选择您的号码。</span><span class="sxs-lookup"><span data-stu-id="ca07f-129">Under **Quantity** , enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="ca07f-130">选择所需的数字。</span><span class="sxs-lookup"><span data-stu-id="ca07f-130">Select the numbers you want.</span></span> <span data-ttu-id="ca07f-131">您有10分钟的时间来选择您的电话号码并放置您的订单。</span><span class="sxs-lookup"><span data-stu-id="ca07f-131">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="ca07f-132">如果您的时间超过10分钟，电话号码将返回到号码池。</span><span class="sxs-lookup"><span data-stu-id="ca07f-132">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="ca07f-133">准备好下订单后，单击 " **下订单** "。</span><span class="sxs-lookup"><span data-stu-id="ca07f-133">When you're ready to place your order, click **Place order**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ca07f-134">用户 （订户） 的电话号码数等于 **国内通话套餐** 和/或 **国内和国际通话套餐** 的许可证已分配乘以 1.1、 加上 10 个其他电话号码的总数。</span><span class="sxs-lookup"><span data-stu-id="ca07f-134">The number of phone numbers for users (subscribers) is equal to the total number of **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses you have assigned multiplied by 1.1, plus 10 additional phone numbers.</span></span> <span data-ttu-id="ca07f-135">例如，如果您总共有 50 个国内通话套餐和/或国内和国际通话套餐的用户，您可以获取 **65** 个电话号码 **(50 x 1.1 + 10)** 。</span><span class="sxs-lookup"><span data-stu-id="ca07f-135">For example, if you have 50 users in total with a Domestic Calling Plan and/or Domestic and International Calling Plan, you can acquire **65** phone numbers **(50 x 1.1 + 10)**.</span></span> <span data-ttu-id="ca07f-136">有关详细信息，请参阅 [您可以获取多少个电话号码？](/microsoftteams/how-many-phone-numbers-can-you-get)。</span><span class="sxs-lookup"><span data-stu-id="ca07f-136">For details, see [How many phone numbers can you get?](/microsoftteams/how-many-phone-numbers-can-you-get).</span></span> <span data-ttu-id="ca07f-137">如果您需要获得比这更多的电话号码，请 [联系支持人员联系以获取商业产品-管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)。</span><span class="sxs-lookup"><span data-stu-id="ca07f-137">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).</span></span>
  
## <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="ca07f-138">将你的服务提供商或电话运营商提供的电话号码转网或转移</span><span class="sxs-lookup"><span data-stu-id="ca07f-138">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="ca07f-139">如果你需要999或更少的用户电话号码，请使用 Microsoft 团队管理中心中的移植向导。</span><span class="sxs-lookup"><span data-stu-id="ca07f-139">If you need 999 or fewer phone numbers for your users, use the porting wizard in the Microsoft Teams Admin Center.</span></span> <span data-ttu-id="ca07f-140">按照将 [电话号码转移到团队](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="ca07f-140">Follow the steps in [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span> <span data-ttu-id="ca07f-141">如果您的国家或地区未在 "移植向导" 中列出，您可以 [手动提交一个端口订单](phone-number-calling-plans/manually-submit-port-order.md) ，或参阅 [管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) 以下载正确的授权 (LOA) 。</span><span class="sxs-lookup"><span data-stu-id="ca07f-141">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA).</span></span>

- <span data-ttu-id="ca07f-142">如果您需要使用超过999的电话号码，您可以 [手动提交一个端口订单](phone-number-calling-plans/manually-submit-port-order.md) ，或参阅 [管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization) 以下载正确的授权 (LOA) ，然后将其发送到 [PSTN 服务桌面](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) ，以获取您的所有已转移号码。</span><span class="sxs-lookup"><span data-stu-id="ca07f-142">If you need to port more than 999 phone numbers, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or see [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) to download the correct Letter of Authorization (LOA) and then send it to [the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to get all your numbers transferred.</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="ca07f-143">查看您的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="ca07f-143">View the phone numbers for your organization</span></span>

<span data-ttu-id="ca07f-144">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="ca07f-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="ca07f-145">在管理中心的左侧导航中，转到 " **语音**  >  **电话号码** " 以查看您的组织的号码，包括位置、号码类型和状态信息。</span><span class="sxs-lookup"><span data-stu-id="ca07f-145">In the left navigation of the admin center, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>
  
## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="ca07f-146">向用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="ca07f-146">Assign phone numbers to users</span></span>

<span data-ttu-id="ca07f-147">获得您的电话号码后，您需要为每个用户分配一个号码。</span><span class="sxs-lookup"><span data-stu-id="ca07f-147">After you get your phone numbers, you'll need to assign a number to each of your users.</span></span> <span data-ttu-id="ca07f-148">有关详细信息，请参阅 [为用户分配、更改或删除电话号码](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) 。</span><span class="sxs-lookup"><span data-stu-id="ca07f-148">See [Assign, change, or remove a phone number for a user](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="ca07f-149">如果您需要获得比这更多的电话号码，请 [联系支持人员联系以获取商业产品-管理员帮助](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)。</span><span class="sxs-lookup"><span data-stu-id="ca07f-149">If you need to get more phone numbers than this, [contact Support Contact for Business Products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca07f-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="ca07f-150">Related topics</span></span>

[<span data-ttu-id="ca07f-151">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="ca07f-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="ca07f-152">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="ca07f-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="ca07f-153">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="ca07f-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="ca07f-154">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="ca07f-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="ca07f-155">[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ca07f-155">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
