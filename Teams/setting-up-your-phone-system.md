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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: 分步指南详细介绍了如何为组织在 电话系统 (或) 中设置云 PBX Microsoft 365 Office 365。
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701210"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="ec145-103">在组织中设置电话系统</span><span class="sxs-lookup"><span data-stu-id="ec145-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="ec145-104">下面是在 Microsoft 365 或 Office 365 中设置电话系统的分步指南。</span><span class="sxs-lookup"><span data-stu-id="ec145-104">The following is a step-by-step guide for setting up Phone System in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ec145-105">在每个步骤的末尾都提供指向其他详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="ec145-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="ec145-106">步骤 1： 请确保您的国家或地区可用使用电话系统</span><span class="sxs-lookup"><span data-stu-id="ec145-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.    <span data-ttu-id="ec145-107">首先转到 [国家和地区的音频会议和呼叫计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="ec145-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.    <span data-ttu-id="ec145-108">在 **电话系统** ，下查看的功能和详细信息的列表。</span><span class="sxs-lookup"><span data-stu-id="ec145-108">Under **Phone System**, review the list of features and details.</span></span> 
3.    <span data-ttu-id="ec145-109">如果可用电话系统，转到步骤 2。</span><span class="sxs-lookup"><span data-stu-id="ec145-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="ec145-110">步骤 2： 购买和分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="ec145-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="ec145-111">若要将电话系统和呼叫计划许可证分配给单个用户，步骤与分配Microsoft 365或Office 365相同。</span><span class="sxs-lookup"><span data-stu-id="ec145-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span>  <span data-ttu-id="ec145-112">也可以批量向多个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="ec145-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="ec145-113">有关详细信息，请参阅[分配Microsoft Teams许可证。](teams-add-on-licensing/assign-teams-add-on-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="ec145-113">For more information, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

<span data-ttu-id="ec145-114">如果呼叫计划不适用于你的国家/地区，请考虑使用直接路由将本地电话基础结构连接到电话系统。</span><span class="sxs-lookup"><span data-stu-id="ec145-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="ec145-115">有关详细信息，请参阅直接[电话系统路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="ec145-116">步骤 3：获取用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="ec145-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="ec145-117">在将组织中用户设置为拨打和接听电话之前，必须获取其电话号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="ec145-118">有三种方法可获取用户的数字：</span><span class="sxs-lookup"><span data-stu-id="ec145-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="ec145-119">使用管理中心获取Teams号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="ec145-120">获取在管理中心内不可用Teams号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="ec145-121">将现有号码从当前服务提供商或电话运营商转Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="ec145-121">Port or transfer your existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="ec145-122">必须使用"添加 **号码"** 页面查看、搜索、获取和保留这些数字。</span><span class="sxs-lookup"><span data-stu-id="ec145-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="ec145-123">可以按"国家/地区、省/市/自治区"和"城市"进行搜索，然后输入用户所需的电话号码数。</span><span class="sxs-lookup"><span data-stu-id="ec145-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="ec145-124">使用管理中心获取Teams电话号码</span><span class="sxs-lookup"><span data-stu-id="ec145-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="ec145-125">使用工作Microsoft 365登录帐户。</span><span class="sxs-lookup"><span data-stu-id="ec145-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="ec145-126">转到 **"Teams管理中心"。**</span><span class="sxs-lookup"><span data-stu-id="ec145-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="ec145-127">在左侧导航中转到"语音  >  电话"，单击"**添加**"，然后按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="ec145-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="ec145-128">获取在管理中心内不可用Teams号码</span><span class="sxs-lookup"><span data-stu-id="ec145-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="ec145-129">有时 (你的国家/地区) 你将无法使用管理中心获取新Teams号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="ec145-130">在这种情况下，需要下载表单并将其发回给我们。</span><span class="sxs-lookup"><span data-stu-id="ec145-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="ec145-131">若要了解如何请求新用户号码，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="ec145-132">将你的服务提供商或电话运营商提供的电话号码转网或转移</span><span class="sxs-lookup"><span data-stu-id="ec145-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="ec145-133">如果你的用户需要的电话号码数少于 999 个，可以在管理中心使用"新建本地号码Teams向导。</span><span class="sxs-lookup"><span data-stu-id="ec145-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="ec145-134">按照[将电话号码转接](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)到Teams中的步骤转移电话号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="ec145-135">如果需要移植超过 999 个电话号码，请参阅管理组织[](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的电话号码以提交移植订单服务请求或订单。</span><span class="sxs-lookup"><span data-stu-id="ec145-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="ec145-136">有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="ec145-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="ec145-137">步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）</span><span class="sxs-lookup"><span data-stu-id="ec145-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="ec145-138">除了从 Microsoft 365 或 Office 365 获取用户的电话号码外，还可以搜索和获取音频会议 (会议网桥) 、自动助理和呼叫队列等服务的收费或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-138">In addition to getting phone numbers for your users from Microsoft 365 or Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="ec145-139">服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。</span><span class="sxs-lookup"><span data-stu-id="ec145-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="ec145-140">例如，服务号码可以同时处理数百个呼叫，而用户的电话号码只能同时处理几个呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec145-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="ec145-141">使用管理中心获取Teams号码</span><span class="sxs-lookup"><span data-stu-id="ec145-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="ec145-142">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ec145-142">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="ec145-143">转到 **"Teams管理中心"。**</span><span class="sxs-lookup"><span data-stu-id="ec145-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="ec145-144">在左侧导航窗格中，转到"语音转  >    >  **电话""** 添加新号码"，然后单击"新建 **服务号码"。**</span><span class="sxs-lookup"><span data-stu-id="ec145-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ec145-145">若要在 Teams管理中心的左侧导航窗格中查看"语音"选项，必须先购买至少一个 **Enterprise E5** 许可证、一个 **电话系统** 附加许可证或一个音频会议附加许可证。 </span><span class="sxs-lookup"><span data-stu-id="ec145-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="ec145-146">获取在管理中心内不可用Teams号码</span><span class="sxs-lookup"><span data-stu-id="ec145-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="ec145-147">有时 (你的国家/地区) 你将无法使用管理中心获取新Teams号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="ec145-148">在这种情况下，需要下载表单并将其发回给我们。</span><span class="sxs-lookup"><span data-stu-id="ec145-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="ec145-149">若要了解如何请求新号码，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="ec145-150">转网或转移现有服务号码</span><span class="sxs-lookup"><span data-stu-id="ec145-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="ec145-151">如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。</span><span class="sxs-lookup"><span data-stu-id="ec145-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="ec145-152">需要针对每种类型的服务号码（收费 (和免费）提交单独的转站订单) 使用授权书和 LOA (转移) 。</span><span class="sxs-lookup"><span data-stu-id="ec145-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="ec145-153">在"授权书 (LOA) 中，必须选择正确的服务编号类型。</span><span class="sxs-lookup"><span data-stu-id="ec145-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="ec145-154">联系 Microsoft 支持部门时，请指定要转移服务号码 (而不是用户或订阅者号码 *) ，* 否则并发呼叫容量可能不足以处理呼叫量。</span><span class="sxs-lookup"><span data-stu-id="ec145-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="ec145-155">如果您想要转接电话号码，或执行其他操作与您的电话号码，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="ec145-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="ec145-156">步骤 5： 如果您想要设置调用计划</span><span class="sxs-lookup"><span data-stu-id="ec145-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="ec145-157">如果你一直在遵循以上步骤，您已购买并分配电话系统和许可证以及通话套餐 （第 2 步）并且为用户获取电话号码（第 3 步），因此您通话套餐i已部分设置。</span><span class="sxs-lookup"><span data-stu-id="ec145-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="ec145-158">若要完成设置呼叫计划的过程，请参阅 [设置呼叫计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="ec145-159">步骤 6： 如果您想要设置音频会议</span><span class="sxs-lookup"><span data-stu-id="ec145-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="ec145-160">有时，组织中的人员需要使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="ec145-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="ec145-161">Microsoft Teams音频会议功能仅针对这种情况。</span><span class="sxs-lookup"><span data-stu-id="ec145-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="ec145-162">用户可以通过电话Teams会议，而不是在移动设备或电脑上Teams应用。</span><span class="sxs-lookup"><span data-stu-id="ec145-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="ec145-163">若要了解如何设置音频会议，请参阅为会议设置[音频Teams。](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ec145-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="ec145-164">步骤 7：如果要设置云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="ec145-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="ec145-165">云呼叫队列包括当某人呼叫组织的电话号码时使用的问候语、自动将呼叫置于保持状态的能力，以及搜索下一个可用的呼叫代理以在呼叫者收听保持音乐时处理呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="ec145-165">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="ec145-166">你可以为组织创建单个或多个呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="ec145-166">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="ec145-167">有关呼叫队列的信息，请参阅 [创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="ec145-168">步骤 8：如果要设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="ec145-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="ec145-169">自动助理允许呼叫组织并导航菜单系统以将其转到正确的部门、呼叫队列、人员或接线员。</span><span class="sxs-lookup"><span data-stu-id="ec145-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="ec145-170">可以使用管理中心为组织创建Teams助理。</span><span class="sxs-lookup"><span data-stu-id="ec145-170">You can create an auto attendant for your organization by using the Teams admin center.</span></span>

<span data-ttu-id="ec145-171">有关设置云自动出席者的信息，请参阅 [设置云自动助理](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="ec145-172">步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）</span><span class="sxs-lookup"><span data-stu-id="ec145-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="ec145-173">一旦您从 **上面的步骤 4** 获得服务号码后，您需要将其分配给所需每种类型服务。</span><span class="sxs-lookup"><span data-stu-id="ec145-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="ec145-174">例如，如果希望专用服务电话号码 (收费或免费) ，则需要将号码分配给会议网桥。</span><span class="sxs-lookup"><span data-stu-id="ec145-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="ec145-175">对于音频会议，你可以为会议网桥分配专用号码，Teams管理中心  >  **会议** 网桥并按照  >  提示。</span><span class="sxs-lookup"><span data-stu-id="ec145-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="ec145-176">有关详细信息，请参阅更改音频  [会议](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)网桥上的收费或免费号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="ec145-177">对于自动助理，你可以向自动助理分配专用号码，Teams管理中心语音自动助理并按照  >    >  提示。</span><span class="sxs-lookup"><span data-stu-id="ec145-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="ec145-178">有关详细信息，请参阅 [设置云自动助理](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="ec145-179">对于呼叫队列，可以通过访问管理中心语音呼叫队列Teams呼叫队列并按照提示操作，为呼叫 **队列** 分配专用  >    >  号码。</span><span class="sxs-lookup"><span data-stu-id="ec145-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="ec145-180">有关详细信息，请参阅 [创建云呼叫队列](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="ec145-181">有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](getting-service-phone-numbers.md) 。</span><span class="sxs-lookup"><span data-stu-id="ec145-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="ec145-182">步骤 10：为组织设置通信信用额度</span><span class="sxs-lookup"><span data-stu-id="ec145-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="ec145-183">如果要将免费电话号码与 Microsoft Teams，则需要设置通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="ec145-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="ec145-184">Microsoft 建议你为呼叫计划设置通信 (国内或国际) 和音频会议用户，这些用户需要能够拨出到任何目的地。</span><span class="sxs-lookup"><span data-stu-id="ec145-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="ec145-185">包括许多国家/地区，但某些目的地可能不包含在呼叫计划或音频会议订阅中。</span><span class="sxs-lookup"><span data-stu-id="ec145-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="ec145-186">如果未设置通信信用额度计费并将通信信用额度许可证分配给用户，并且你的组织 (根据你的呼叫计划或音频会议计划在你的国家/地区) 中用完了分钟数，则这些用户将无法进行呼叫或从音频会议会议拨出。</span><span class="sxs-lookup"><span data-stu-id="ec145-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="ec145-187">有关详细信息，包括建议的资金金额，请参阅 [什么是通信信用额度？](what-are-communications-credits.md) 和为组织设置通信 [信用额度](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ec145-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="ec145-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="ec145-188">Related topics</span></span>
[<span data-ttu-id="ec145-189">以下是使用 电话系统 或 Microsoft 365 获取Office 365</span><span class="sxs-lookup"><span data-stu-id="ec145-189">Here's what you get with Phone System in Microsoft 365 or Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ec145-190">管理组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="ec145-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="ec145-191">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="ec145-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="ec145-192">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="ec145-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
