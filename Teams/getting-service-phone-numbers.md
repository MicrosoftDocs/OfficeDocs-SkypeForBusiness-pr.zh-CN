---
title: 获取服务电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
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
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 了解如何为团队获取新的电话号码和端口，或传输音频会议、自动助理和通话队列（服务号码）的现有号码。
ms.openlocfilehash: 9ce7875f06677ab6b9a4ad61a9e30bf0df861bb8
ms.sourcegitcommit: e618396eb8da958983668ad0884b4481e1ed7b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44021984"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="63754-103">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="63754-103">Getting service phone numbers</span></span>

<span data-ttu-id="63754-104">除了[获取用户的电话号码](/microsoftteams/getting-phone-numbers-for-your-users)，您还可以获取服务的收费电话号码或免费电话号码，如音频会议（适用于会议桥）、自动助理和呼叫队列（也称为服务号码）。</span><span class="sxs-lookup"><span data-stu-id="63754-104">In addition to [getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users), you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="63754-105">服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。</span><span class="sxs-lookup"><span data-stu-id="63754-105">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="63754-106">例如，服务号码可以同时处理数百个通话，而用户的电话号码只能同时处理多个通话。</span><span class="sxs-lookup"><span data-stu-id="63754-106">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63754-107">您必须先设置通讯信用点数，然后才能获取免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="63754-107">You have to first set up Communications Credits before you can get toll-free numbers.</span></span> <span data-ttu-id="63754-108">若要了解详细信息，请参阅[为你的组织设置通信信用点数](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="63754-108">To learn more, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
  
<span data-ttu-id="63754-109">可通过三种方式获取服务号码：</span><span class="sxs-lookup"><span data-stu-id="63754-109">There are three ways to get service numbers:</span></span>
  
- <span data-ttu-id="63754-110">**使用 Microsoft 团队管理中心。**</span><span class="sxs-lookup"><span data-stu-id="63754-110">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="63754-111">对于某些国家和地区，您可以使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="63754-111">For some countries and regions, you can get service numbers using the Microsoft Teams admin center.</span></span> <span data-ttu-id="63754-112">请参阅[获取新的服务号码](#get-new-service-numbers)。</span><span class="sxs-lookup"><span data-stu-id="63754-112">See [Get new service numbers](#get-new-service-numbers).</span></span>

- <span data-ttu-id="63754-113">**转网现有的号码。**</span><span class="sxs-lookup"><span data-stu-id="63754-113">**Port your existing numbers.**</span></span> <span data-ttu-id="63754-114">您可以从当前服务提供商或电话运营商处移植或转移现有号码。</span><span class="sxs-lookup"><span data-stu-id="63754-114">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="63754-115">如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="63754-115">See [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="63754-116">**使用新号码的请求表单。**</span><span class="sxs-lookup"><span data-stu-id="63754-116">**Use a request form for new numbers.**</span></span> <span data-ttu-id="63754-117">有时（取决于您所在的国家或地区）您将无法使用 Microsoft 团队管理中心获取新的电话号码，或者您需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="63754-117">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="63754-118">如果是这样，您将需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="63754-118">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="63754-119">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="63754-119">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63754-120">需要服务号码，以便您可以为特定号码获得更高的并发通话容量。</span><span class="sxs-lookup"><span data-stu-id="63754-120">Service numbers are needed so you can get a higher concurrent call capacity for a specific number.</span></span> <span data-ttu-id="63754-121">当您将号码转移给我们时，您可以[联系 PSTN 服务中心](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)，以确保您正在转移的服务号码具有高并发通话容量。</span><span class="sxs-lookup"><span data-stu-id="63754-121">When you're transferring the number over to us, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to make sure the service number you're transferring has a high concurrent call capacity.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="63754-122">获取新服务号码</span><span class="sxs-lookup"><span data-stu-id="63754-122">Get new service numbers</span></span>

<span data-ttu-id="63754-123">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="63754-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="63754-124">在左侧导航中，转到 "**语音** > **电话号码**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="63754-124">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="63754-125">输入订单的名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="63754-125">Enter a name for the order and add a description.</span></span>
3. <span data-ttu-id="63754-126">在 "位置和数量" 页面上，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="63754-126">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="63754-127">在 "**国家或地区**" 下，选择一个国家或地区。</span><span class="sxs-lookup"><span data-stu-id="63754-127">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="63754-128">在 "**号码类型**" 下，选择所需的服务号码类型。</span><span class="sxs-lookup"><span data-stu-id="63754-128">Under **Number type**, select the type of service number that you want.</span></span>
    1. <span data-ttu-id="63754-129">在 "**位置**" 下，选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="63754-129">Under **Location**, select a location.</span></span> <span data-ttu-id="63754-130">如果需要创建新位置，请单击 "**添加位置**"。</span><span class="sxs-lookup"><span data-stu-id="63754-130">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="63754-131">在 "**区域代码**" 下，选择区号。</span><span class="sxs-lookup"><span data-stu-id="63754-131">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="63754-132">在 "**数量**" 下，输入您的组织所需的号码数，然后单击 "**下一步**" 以选择您的号码。</span><span class="sxs-lookup"><span data-stu-id="63754-132">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="63754-133">选择所需的数字。</span><span class="sxs-lookup"><span data-stu-id="63754-133">Select the numbers you want.</span></span> <span data-ttu-id="63754-134">您有10分钟的时间来选择您的电话号码并放置您的订单。</span><span class="sxs-lookup"><span data-stu-id="63754-134">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="63754-135">如果您的时间超过10分钟，电话号码将返回到号码池。</span><span class="sxs-lookup"><span data-stu-id="63754-135">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="63754-136">准备好下订单后，单击 "**下订单**"。</span><span class="sxs-lookup"><span data-stu-id="63754-136">When you're ready to place your order, click **Place order**.</span></span>

## <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="63754-137">转网或转移现有服务号码</span><span class="sxs-lookup"><span data-stu-id="63754-137">Port or transfer existing service numbers</span></span>

<span data-ttu-id="63754-138">若要将您的电话号码从当前服务提供商或运营商转移到团队，您可以使用 Microsoft 团队管理中心中的移植向导。</span><span class="sxs-lookup"><span data-stu-id="63754-138">To transfer your phone numbers from your current service provider or carrier to Teams, you can use the porting wizard in the Microsoft Teams admin center.</span></span> <span data-ttu-id="63754-139">按照将[电话号码转移到团队](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="63754-139">Follow the steps in [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

<span data-ttu-id="63754-140">如果您的国家或地区未在移植向导中列出，您可以[手动提交一个端口订单](phone-number-calling-plans/manually-submit-port-order.md)或转到[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，选择您所在的国家或地区，然后下载授权书（LOA）。</span><span class="sxs-lookup"><span data-stu-id="63754-140">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), select your country or region, and then download a Letter of Authorization (LOA).</span></span> <span data-ttu-id="63754-141">您必须为每种类型的服务号码（例如，收费电话，即免费电话）提交单独的端口订单，您将使用 LOA 进行传输。</span><span class="sxs-lookup"><span data-stu-id="63754-141">You'll have to submit separate port orders for each type of service number (for example, toll vs. toll-free) that you'll be transferring by using an LOA.</span></span> <span data-ttu-id="63754-142">在 LOA 中，必须选择正确的服务编号类型。</span><span class="sxs-lookup"><span data-stu-id="63754-142">In the LOA, you must select the correct type of service number.</span></span> <span data-ttu-id="63754-143">确保你指定要转移的服务号码（而不是用户或订阅者号码），或者同时拨打的通话量可能不足以处理呼叫卷。</span><span class="sxs-lookup"><span data-stu-id="63754-143">Make sure you specify that you're transferring a service number (and not a user or subscriber number), or the concurrent calling capacity may not be enough to handle call volumes.</span></span>  

> [!NOTE]
> <span data-ttu-id="63754-144">如果您需要获得比这更多的电话号码，[请与 PSTN 服务支持人员联系](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="63754-144">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="63754-145">查看您的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="63754-145">View the phone numbers for your organization</span></span>

<span data-ttu-id="63754-146">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="63754-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="63754-147">在左侧导航中，转到 "**语音** > **电话号码**" 以查看您的组织的号码，包括位置、号码类型和状态信息。</span><span class="sxs-lookup"><span data-stu-id="63754-147">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>

## <a name="assign-service-phone-numbers"></a><span data-ttu-id="63754-148">分配服务电话号码</span><span class="sxs-lookup"><span data-stu-id="63754-148">Assign service phone numbers</span></span>

<span data-ttu-id="63754-149">获得服务号码后，将每个号码分配给音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="63754-149">After you get your service numbers, assign each number to an Audio Conferencing bridge.</span></span> <span data-ttu-id="63754-150">请参阅[在音频会议网桥上更改收费或免费电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="63754-150">See [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="related-topics"></a><span data-ttu-id="63754-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="63754-151">Related topics</span></span>

[<span data-ttu-id="63754-152">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="63754-152">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="63754-153">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="63754-153">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="63754-154">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="63754-154">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="63754-155">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="63754-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="63754-156">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="63754-156">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
