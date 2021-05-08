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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 了解如何为音频会议、自动助理和呼叫队列获取新电话号码和转 (号码) 号码Teams。
ms.openlocfilehash: 72436591411070ed7ffc67aab5d8d4470f39521d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092230"
---
# <a name="getting-service-phone-numbers"></a><span data-ttu-id="2a1dc-103">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-103">Getting service phone numbers</span></span>

<span data-ttu-id="2a1dc-104">除了为用户[](./getting-phone-numbers-for-your-users.md)获取电话号码外，还可以获取音频会议 (（用于会议网桥) 、自动助理和呼叫队列 (也称为服务号码) ）的收费或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-104">In addition to [getting phone numbers for your users](./getting-phone-numbers-for-your-users.md), you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), auto attendants, and call queues (also called service numbers).</span></span> <span data-ttu-id="2a1dc-105">服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-105">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="2a1dc-106">例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-106">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a1dc-107">首先必须设置通信信用额度，才能获取免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-107">You have to first set up Communications Credits before you can get toll-free numbers.</span></span> <span data-ttu-id="2a1dc-108">有关详细信息，请参阅 [为组织设置通信信用额度](./set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-108">To learn more, see [Set up Communications Credits for your organization](./set-up-communications-credits-for-your-organization.md).</span></span>
  
<span data-ttu-id="2a1dc-109">有三种方法可获取服务编号：</span><span class="sxs-lookup"><span data-stu-id="2a1dc-109">There are three ways to get service numbers:</span></span>
  
- <span data-ttu-id="2a1dc-110">**使用Microsoft Teams管理中心。**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-110">**Use the Microsoft Teams admin center.**</span></span> <span data-ttu-id="2a1dc-111">对于一些国家和地区，可以使用管理中心获取Microsoft Teams号码。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-111">For some countries and regions, you can get service numbers using the Microsoft Teams admin center.</span></span> <span data-ttu-id="2a1dc-112">请参阅 [获取新服务编号](#get-new-service-numbers)。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-112">See [Get new service numbers](#get-new-service-numbers).</span></span>

- <span data-ttu-id="2a1dc-113">**转网现有的号码。**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-113">**Port your existing numbers.**</span></span> <span data-ttu-id="2a1dc-114">可以从当前服务提供商或电话运营商转转现有号码。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-114">You can port or transfer existing numbers from your current service provider or phone carrier.</span></span> <span data-ttu-id="2a1dc-115">如需获取有助于执行此操作的详细信息，请参阅[将电话号码转接到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-115">See [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="2a1dc-116">**使用新号码的请求表单。**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-116">**Use a request form for new numbers.**</span></span> <span data-ttu-id="2a1dc-117">有时 (你的国家/地区或地区) 你将无法使用 Microsoft Teams 管理中心获取新电话号码，或者你需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-117">Sometimes (depending on your country or region) you won't be able to get your new phone numbers using the Microsoft Teams admin center, or you'll need specific phone numbers or area codes.</span></span> <span data-ttu-id="2a1dc-118">如果是这样，则需要下载表单并将其发回给我们。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-118">If so, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="2a1dc-119">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-119">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a1dc-120">需要服务号码，以便可以获取特定号码的更高的并发调用容量。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-120">Service numbers are needed so you can get a higher concurrent call capacity for a specific number.</span></span> <span data-ttu-id="2a1dc-121">将号码转移给我们时，可以联系 [PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) 服务台，确保要转移的服务号码具有较高的并发呼叫容量。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-121">When you're transferring the number over to us, you can [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) to make sure the service number you're transferring has a high concurrent call capacity.</span></span>
  
## <a name="get-new-service-numbers"></a><span data-ttu-id="2a1dc-122">获取新服务号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-122">Get new service numbers</span></span>

<span data-ttu-id="2a1dc-123">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-123">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2a1dc-124">在左侧导航栏中，转到"语音  >  **电话"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-124">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
2. <span data-ttu-id="2a1dc-125">输入订单的名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-125">Enter a name for the order and add a description.</span></span>
3. <span data-ttu-id="2a1dc-126">在"位置和数量"页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2a1dc-126">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="2a1dc-127">在 **"国家/地区"下**，选择一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-127">Under **Country or region**, select a country or region.</span></span>
    1. <span data-ttu-id="2a1dc-128">在 **"数字类型**"下，选择需要的服务编号类型。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-128">Under **Number type**, select the type of service number that you want.</span></span>
    1. <span data-ttu-id="2a1dc-129">在 **"位置"** 下，选择一个位置。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-129">Under **Location**, select a location.</span></span> <span data-ttu-id="2a1dc-130">如果需要创建新位置，请单击"**添加位置"。**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-130">If you need to create a new location, click **Add a location**.</span></span>
    1. <span data-ttu-id="2a1dc-131">在 **"区号"** 下，选择区号。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-131">Under **Area code**, select an area code.</span></span> 
    2. <span data-ttu-id="2a1dc-132">在 **"** 数量"下，输入贵组织需要的数字数，然后单击"下一步"以选择号码。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-132">Under **Quantity**, enter the number of numbers that you want for your organization, and then click **Next** to select your numbers.</span></span>
4. <span data-ttu-id="2a1dc-133">选择您需要的数字。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-133">Select the numbers you want.</span></span> <span data-ttu-id="2a1dc-134">你有 10 分钟的时间来选择电话号码并下订单。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-134">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="2a1dc-135">如果时间超过 10 分钟，电话号码将返回到号码池。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-135">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
5. <span data-ttu-id="2a1dc-136">准备好下订单后，单击"下 **单"。**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-136">When you're ready to place your order, click **Place order**.</span></span>

## <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="2a1dc-137">转网或转移现有服务号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-137">Port or transfer existing service numbers</span></span>

<span data-ttu-id="2a1dc-138">若要将电话号码从当前服务提供商或运营商Teams，可以在管理中心使用Microsoft Teams向导。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-138">To transfer your phone numbers from your current service provider or carrier to Teams, you can use the porting wizard in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2a1dc-139">按照将电话号码[转移到 Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-139">Follow the steps in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

<span data-ttu-id="2a1dc-140">如果移植向导中未列出你的国家/地区，可以手动提交转寄订单[](phone-number-calling-plans/manually-submit-port-order.md)或转到"管理组织的电话号码"，选择[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)你的国家/地区，然后下载授权书 (LOA) 。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-140">If your country or region isn't listed in the porting wizard, you can [manually submit a port order](phone-number-calling-plans/manually-submit-port-order.md) or go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), select your country or region, and then download a Letter of Authorization (LOA).</span></span> <span data-ttu-id="2a1dc-141">必须针对每种类型的服务号码提交单独的转站订单 (例如，使用 LOA 转移的收费和免费) 收费与免费服务。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-141">You'll have to submit separate port orders for each type of service number (for example, toll vs. toll-free) that you'll be transferring by using an LOA.</span></span> <span data-ttu-id="2a1dc-142">在 LOA 中，必须选择正确的服务编号类型。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-142">In the LOA, you must select the correct type of service number.</span></span> <span data-ttu-id="2a1dc-143">请确保指定要转移服务号码 (而不是用户或订阅者号码) ，否则并发呼叫容量可能不足以处理呼叫量。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-143">Make sure you specify that you're transferring a service number (and not a user or subscriber number), or the concurrent calling capacity may not be enough to handle call volumes.</span></span>  

> [!NOTE]
> <span data-ttu-id="2a1dc-144">如果需要获取的电话号码超过此数目， [请联系 PSTN 服务台](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-144">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="view-the-phone-numbers-for-your-organization"></a><span data-ttu-id="2a1dc-145">查看组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-145">View the phone numbers for your organization</span></span>

<span data-ttu-id="2a1dc-146">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="2a1dc-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span> 

<span data-ttu-id="2a1dc-147">在左侧导航中，转到"语音电话号码以查看组织号码，包括位置、  >  号码类型和状态信息。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-147">In the left navigation, go to **Voice** > **Phone numbers** to view the numbers for your organization, including location, number type, and status information.</span></span>

## <a name="assign-service-phone-numbers"></a><span data-ttu-id="2a1dc-148">分配服务电话号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-148">Assign service phone numbers</span></span>

<span data-ttu-id="2a1dc-149">获取服务号码后，将每个号码分配给音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-149">After you get your service numbers, assign each number to an Audio Conferencing bridge.</span></span> <span data-ttu-id="2a1dc-150">请参阅 [更改音频会议网桥](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)上的收费或免费号码。</span><span class="sxs-lookup"><span data-stu-id="2a1dc-150">See [Change the toll or toll free numbers on your Audio Conferencing bridge](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a1dc-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="2a1dc-151">Related topics</span></span>

[<span data-ttu-id="2a1dc-152">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="2a1dc-152">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="2a1dc-153">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="2a1dc-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="2a1dc-154">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="2a1dc-155">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="2a1dc-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="2a1dc-156">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="2a1dc-156">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)