---
title: 设置组织内的电话系统
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '了解如何为你的组织设置电话系统（云 PBX）。 '
ms.openlocfilehash: 8c534607ca50baae75c3b0b2fdf5bc54359c22e4
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779809"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="bcadb-103">在组织中设置电话系统</span><span class="sxs-lookup"><span data-stu-id="bcadb-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="bcadb-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span><span class="sxs-lookup"><span data-stu-id="bcadb-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="bcadb-106">步骤 1： 请确保您的国家或地区可用使用电话系统</span><span class="sxs-lookup"><span data-stu-id="bcadb-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="bcadb-107">首先转到 [国家和地区的音频会议和呼叫计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="bcadb-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.  <span data-ttu-id="bcadb-108">在 **电话系统** ，下查看的功能和详细信息的列表。</span><span class="sxs-lookup"><span data-stu-id="bcadb-108">Under **Phone System**, review the list of features and details.</span></span> 
3.  <span data-ttu-id="bcadb-109">如果可用电话系统，转到步骤 2。</span><span class="sxs-lookup"><span data-stu-id="bcadb-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="bcadb-110">步骤 2： 购买和分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="bcadb-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="bcadb-111">若要向单个用户分配电话系统和呼叫计划许可证，步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="bcadb-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning an Office 365 license.</span></span>  <span data-ttu-id="bcadb-112">您还可以批量将许可证分配给多个用户。</span><span class="sxs-lookup"><span data-stu-id="bcadb-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="bcadb-113">有关详细信息，请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-113">For more information, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

<span data-ttu-id="bcadb-114">如果通话计划不适用于您所在的国家或地区，请考虑使用直接路由将本地电话基础结构连接到电话系统。</span><span class="sxs-lookup"><span data-stu-id="bcadb-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="bcadb-115">有关详细信息，请参阅[手机系统直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="bcadb-116">步骤3：为用户获取电话号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="bcadb-117">在您可以将组织中的用户设置为拨打和接收电话呼叫之前，您必须为他们获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="bcadb-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="bcadb-118">有三种方法可为用户获取号码：</span><span class="sxs-lookup"><span data-stu-id="bcadb-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="bcadb-119">使用团队管理中心获取新号码。</span><span class="sxs-lookup"><span data-stu-id="bcadb-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="bcadb-120">获取团队管理中心中不可用的新号码。</span><span class="sxs-lookup"><span data-stu-id="bcadb-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="bcadb-121">将您的现有服务提供商或电话运营商中的现有号码移植或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bcadb-121">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="bcadb-122">您必须使用 "**添加号码**" 页面查看、搜索、获取和保留这些号码。</span><span class="sxs-lookup"><span data-stu-id="bcadb-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="bcadb-123">您可以按国家/地区、省/市/县和市/县进行搜索，然后输入您需要的用户电话号码的数量。</span><span class="sxs-lookup"><span data-stu-id="bcadb-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="bcadb-124">使用团队管理中心获取新的用户电话号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="bcadb-125">使用你的工作或学校帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bcadb-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="bcadb-126">转到 "**团队管理中心**"。</span><span class="sxs-lookup"><span data-stu-id="bcadb-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="bcadb-127">在左侧导航中，转到 "**语音** > **电话号码**"，单击 "**添加**"，然后按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="bcadb-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="bcadb-128">获取团队管理中心中不可用的新号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="bcadb-129">有时（取决于您所在的国家/地区）您将无法使用团队管理中心获取您的新号码。</span><span class="sxs-lookup"><span data-stu-id="bcadb-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="bcadb-130">在这种情况下，你需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="bcadb-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="bcadb-131">若要了解如何申请新的用户号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="bcadb-132">将你的服务提供商或电话运营商提供的电话号码转网或转移</span><span class="sxs-lookup"><span data-stu-id="bcadb-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="bcadb-133">如果您需要999或更少的用户电话号码，您可以使用团队管理中心中的 "**新的本地号码" 端口订单**向导。</span><span class="sxs-lookup"><span data-stu-id="bcadb-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="bcadb-134">按照将[电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)转移电话号码中找到的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="bcadb-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="bcadb-135">如果您需要移植超过999的电话号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交 "订单" 服务请求或订单。</span><span class="sxs-lookup"><span data-stu-id="bcadb-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="bcadb-136">有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="bcadb-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="bcadb-137">步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）</span><span class="sxs-lookup"><span data-stu-id="bcadb-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="bcadb-138">除了从 Office 365 中获取用户的电话号码之外，您还可以搜索和获取服务的收费电话号码或免费电话号码，如音频会议（适用于会议桥）、自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="bcadb-138">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="bcadb-139">服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。</span><span class="sxs-lookup"><span data-stu-id="bcadb-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="bcadb-140">例如，服务号码可以同时处理数百个通话，而用户的电话号码只能同时处理多个通话。</span><span class="sxs-lookup"><span data-stu-id="bcadb-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="bcadb-141">使用团队管理中心获取新的服务号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="bcadb-142">使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bcadb-142">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="bcadb-143">转到 "**团队管理中心**"。</span><span class="sxs-lookup"><span data-stu-id="bcadb-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="bcadb-144">在左侧导航窗格中，转到 "**语音** > **电话号码** > "**添加新号码**，然后单击 "**新的服务号码**"。</span><span class="sxs-lookup"><span data-stu-id="bcadb-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bcadb-145">要在团队管理中心的左侧导航窗格中看到 "**语音**" 选项，您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。</span><span class="sxs-lookup"><span data-stu-id="bcadb-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="bcadb-146">获取团队管理中心中不可用的新号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="bcadb-147">有时（取决于您所在的国家/地区）您将无法使用团队管理中心获取您的新号码。</span><span class="sxs-lookup"><span data-stu-id="bcadb-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="bcadb-148">在这种情况下，你将需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="bcadb-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="bcadb-149">若要了解如何申请新号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="bcadb-150">转网或转移现有服务号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="bcadb-151">如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。</span><span class="sxs-lookup"><span data-stu-id="bcadb-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="bcadb-152">您需要为每种类型的服务号码（如收费电话）提交单独的端口订单，您将使用授权书（LOA）进行转移。</span><span class="sxs-lookup"><span data-stu-id="bcadb-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="bcadb-153">在授权书（LOA）中，您必须选择正确的服务号码类型。</span><span class="sxs-lookup"><span data-stu-id="bcadb-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="bcadb-154">联系 Microsoft 支持时，请指定你正在转移服务号码（*而不是用户或订阅者号码*），或者同时拨打的通话量可能不足以处理呼叫卷。</span><span class="sxs-lookup"><span data-stu-id="bcadb-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="bcadb-155">如果您想要转接电话号码，或执行其他操作与您的电话号码，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="bcadb-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="bcadb-156">步骤 5： 如果您想要设置调用计划</span><span class="sxs-lookup"><span data-stu-id="bcadb-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="bcadb-157">如果你一直在遵循以上步骤，您已购买并分配电话系统和许可证以及通话套餐 （第 2 步）并且为用户获取电话号码（第 3 步），因此您通话套餐i已部分设置。</span><span class="sxs-lookup"><span data-stu-id="bcadb-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="bcadb-158">若要完成设置呼叫计划的过程，请参阅[设置呼叫计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="bcadb-159">步骤 6： 如果您想要设置音频会议</span><span class="sxs-lookup"><span data-stu-id="bcadb-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="bcadb-160">有时，组织中的人员需要使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="bcadb-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="bcadb-161">Microsoft 团队仅为此情况提供音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="bcadb-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="bcadb-162">用户可以使用电话呼叫团队会议，而不是在移动设备或电脑上使用 "团队" 应用。</span><span class="sxs-lookup"><span data-stu-id="bcadb-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="bcadb-163">有关如何设置音频会议的信息，请参阅[设置团队的音频会议](set-up-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="bcadb-164">步骤7：要设置云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="bcadb-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="bcadb-165">云呼叫队列包括当某人拨入到您的组织的电话号码时使用的问候语、自动将呼叫置于保持状态的功能，以及搜索下一个可用的呼叫代理以处理呼叫的功能，同时呼叫正在收听音乐的用户。</span><span class="sxs-lookup"><span data-stu-id="bcadb-165">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="bcadb-166">您可以为您的组织创建单个或多个通话队列。</span><span class="sxs-lookup"><span data-stu-id="bcadb-166">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="bcadb-167">有关通话队列的详细信息，请参阅[创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="bcadb-168">步骤8：如果要设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="bcadb-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="bcadb-169">自动助理允许与你的组织进行通话的人员，并导航到相应的菜单系统以将其转到相应的部门、呼叫队列、人员或运营商。</span><span class="sxs-lookup"><span data-stu-id="bcadb-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="bcadb-170">您可以使用 "团队管理中心" 为您的组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="bcadb-170">You can create an auto attendant for your organization by using the Teams admin center.</span></span>

<span data-ttu-id="bcadb-171">有关设置云自动 attendendant 的信息，请参阅[设置云自动助理](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="bcadb-172">步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）</span><span class="sxs-lookup"><span data-stu-id="bcadb-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="bcadb-173">一旦您从 **上面的步骤 4** 获得服务号码后，您需要将其分配给所需每种类型服务。</span><span class="sxs-lookup"><span data-stu-id="bcadb-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="bcadb-174">例如，如果您需要专用服务电话号码（收费或免费），您需要将该号码分配给会议桥。</span><span class="sxs-lookup"><span data-stu-id="bcadb-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="bcadb-175">对于音频会议，您可以通过转到**团队管理中心** > **会议** > **桥**并按照提示将专用号码分配给会议桥。</span><span class="sxs-lookup"><span data-stu-id="bcadb-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="bcadb-176">有关详细信息，请参阅[在音频会议网桥上更改收费或免费号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="bcadb-177">对于自动助理，你可以通过转到 "**团队管理中心** > "**语音** > **自动助理**，将专用号码分配给自动助理，然后按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="bcadb-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="bcadb-178">有关详细信息，请参阅[设置云自动助理](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="bcadb-179">对于呼叫队列，您可以通过转到 "**团队管理员中心** > **语音** > **呼叫" 队列**将专用号码分配给呼叫队列，然后按照提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="bcadb-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="bcadb-180">有关详细信息，请参阅[创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="bcadb-181">有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](getting-service-phone-numbers.md) 。</span><span class="sxs-lookup"><span data-stu-id="bcadb-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="bcadb-182">步骤10：为你的组织设置通讯信用点数</span><span class="sxs-lookup"><span data-stu-id="bcadb-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="bcadb-183">如果您想要与 Microsoft 团队一起使用免费电话号码，您需要设置通讯信用点数。</span><span class="sxs-lookup"><span data-stu-id="bcadb-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="bcadb-184">Microsoft 建议为您的呼叫计划（国内或国际）和需要拨出到任何目的地的音频会议用户设置通讯信用点数。</span><span class="sxs-lookup"><span data-stu-id="bcadb-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="bcadb-185">包括许多国家/地区，但某些目的地可能不包括在您的通话计划或音频会议套餐中。</span><span class="sxs-lookup"><span data-stu-id="bcadb-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="bcadb-186">如果您不设置通讯信用帐单并为您的用户分配**通讯信用**许可证，而您的组织的分钟数（取决于您所在国家/地区的通话计划或音频会议计划），这些用户将无法通过音频会议会议进行呼叫或拨出。</span><span class="sxs-lookup"><span data-stu-id="bcadb-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="bcadb-187">有关详细信息（包括推荐的融资金额），请参阅[什么是通讯信用点数？](what-are-communications-credits.md)并[为您的组织设置通讯信用点数](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="bcadb-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="bcadb-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="bcadb-188">Related topics</span></span>
[<span data-ttu-id="bcadb-189">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="bcadb-189">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="bcadb-190">管理组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="bcadb-191">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="bcadb-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="bcadb-192">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="bcadb-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
