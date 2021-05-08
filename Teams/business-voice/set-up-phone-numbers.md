---
title: 设置Microsoft 365 商务语音电话号码
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何为Microsoft 365 商务语音和服务设置电话号码。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7dcf582593cf09977f4992d6b78035a9726c12b8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282539"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="282f8-103">步骤 2：设置业务语音电话号码</span><span class="sxs-lookup"><span data-stu-id="282f8-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="282f8-104">在组织中设置用户或自动助理之前，需要获取其电话号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="282f8-105">有几种不同类型的电话号码，但以下是需要在此步骤中添加的两种类型的号码：</span><span class="sxs-lookup"><span data-stu-id="282f8-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="282f8-106">**服务编号** 这些号码用于自动助理、音频会议和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="282f8-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="282f8-107">它们可以是收费或免费号码，可以同时处理大量呼叫。</span><span class="sxs-lookup"><span data-stu-id="282f8-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="282f8-108">公司电话号码需要是服务号码，因为稍后的步骤会将其分配给自动助理。</span><span class="sxs-lookup"><span data-stu-id="282f8-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="282f8-109">**订阅者号码** 这些号码用于普通用户，以便他们可以拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="282f8-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="282f8-110">即使想使用现有电话号码，也需要创建临时电话号码并将其分配给公司的主电话线和用户。</span><span class="sxs-lookup"><span data-stu-id="282f8-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="282f8-111">在稍后的步骤中，你可以将这些临时号码替换为现有电话号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="282f8-112">新电话号码可能需要几个小时才能在 Teams。</span><span class="sxs-lookup"><span data-stu-id="282f8-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="282f8-113">设置服务号码</span><span class="sxs-lookup"><span data-stu-id="282f8-113">Set up a service number</span></span>

<span data-ttu-id="282f8-114">现在设置的服务号码将用于公司主电话号码的后一步。</span><span class="sxs-lookup"><span data-stu-id="282f8-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="282f8-115">打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="282f8-115">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="282f8-116">在左侧导航栏中，转到"<a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**语音**  >  **电话"，**</a>然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="282f8-116">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="282f8-117">输入订单的名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="282f8-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="282f8-118">在"位置和数量"页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="282f8-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="282f8-119">在 **"国家/地区"下**，选择一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="282f8-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="282f8-120">在 **"数字类型**"下，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="282f8-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="282f8-121">**自动助理 (收费)** 常规非免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="282f8-122">长距离费用将收取给呼叫方。</span><span class="sxs-lookup"><span data-stu-id="282f8-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="282f8-123">**自动助理 (免费)** 使用免费电话号码 (美国和加拿大) 免费电话 () 电话号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="282f8-124">长距离费用由公司收取。</span><span class="sxs-lookup"><span data-stu-id="282f8-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="282f8-125">在选择此选项之前，需要购买通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="282f8-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="282f8-126">有关详细信息，请参阅我需要购买哪些产品以[使用Microsoft 365 商务语音？。](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="282f8-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="282f8-127">在 **"数量"** 下，选择 **"1"。**</span><span class="sxs-lookup"><span data-stu-id="282f8-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="282f8-128">如果 **收到消息"** 没有足够的许可证来请求更多此类号码"，请确保已购买商业语音许可证。</span><span class="sxs-lookup"><span data-stu-id="282f8-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="282f8-129">有关详细信息，请参阅我需要购买哪些产品以[使用Microsoft 365 商务语音？。](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="282f8-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="282f8-130">选择 **"位置**"或"区号"，具体取决于是想要使用位置的城市搜索电话号码，还是想要搜索特定区号中的号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-130">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="282f8-131">如果选择"位置 **"：**</span><span class="sxs-lookup"><span data-stu-id="282f8-131">If you select **Location**:</span></span>

        1. <span data-ttu-id="282f8-132">在"设置紧急位置"步骤中键入紧急地址所在的城市 [](set-up-emergency-locations.md)，或者如果需要为另一个办公室或家庭办公室创建新位置，请单击"添加位置 **"。**</span><span class="sxs-lookup"><span data-stu-id="282f8-132">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="282f8-133">在 **"区号**"下，选择区号，然后选择"下一步"以保留号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-133">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="282f8-134">如果选择"**区号"，** 请键入要搜索的区号，然后选择"下一步"以保留号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-134">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="282f8-135">选择您需要的号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-135">Select the number you want.</span></span> <span data-ttu-id="282f8-136">你有 10 分钟的时间来选择电话号码并下订单。</span><span class="sxs-lookup"><span data-stu-id="282f8-136">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="282f8-137">如果时间超过 10 分钟，电话号码将返回到号码池。</span><span class="sxs-lookup"><span data-stu-id="282f8-137">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="282f8-138">准备好下单后，单击"下 **单"，** 然后单击"完成 **"**</span><span class="sxs-lookup"><span data-stu-id="282f8-138">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="282f8-139">为用户设置电话号码</span><span class="sxs-lookup"><span data-stu-id="282f8-139">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="282f8-140">打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="282f8-140">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="282f8-141">在左侧导航栏中，转到"<a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**语音**  >  **电话"，**</a>然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="282f8-141">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="282f8-142">输入订单的名称并添加说明。</span><span class="sxs-lookup"><span data-stu-id="282f8-142">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="282f8-143">在"位置和数量"页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="282f8-143">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="282f8-144">在 **"国家/地区"下**，选择一个或多个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="282f8-144">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="282f8-145">在 **"数字类型"** 下，选择" (**订阅) "**。</span><span class="sxs-lookup"><span data-stu-id="282f8-145">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="282f8-146">在 **"** 数量"下，输入希望组织使用的数字数。</span><span class="sxs-lookup"><span data-stu-id="282f8-146">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="282f8-147">选择 **"位置**"或"区号"，具体取决于是想要使用位置的城市搜索电话号码，还是想要搜索特定区号中的号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-147">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="282f8-148">如果选择"位置 **"：**</span><span class="sxs-lookup"><span data-stu-id="282f8-148">If you select **Location**:</span></span>

        1. <span data-ttu-id="282f8-149">在"设置紧急位置"步骤中键入紧急地址所在的城市 [](set-up-emergency-locations.md)，或者如果需要为另一个办公室或家庭办公室创建新位置，请单击"添加位置 **"。**</span><span class="sxs-lookup"><span data-stu-id="282f8-149">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="282f8-150">在 **"区号**"下，选择区号，然后选择"下一步"以保留号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-150">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="282f8-151">如果选择"**区号"，** 请键入要搜索的区号，然后选择"下一步"以保留号码。</span><span class="sxs-lookup"><span data-stu-id="282f8-151">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="282f8-152">选择您需要的数字。</span><span class="sxs-lookup"><span data-stu-id="282f8-152">Select the numbers you want.</span></span> <span data-ttu-id="282f8-153">你有 10 分钟的时间来选择电话号码并下订单。</span><span class="sxs-lookup"><span data-stu-id="282f8-153">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="282f8-154">如果时间超过 10 分钟，电话号码将返回到号码池。</span><span class="sxs-lookup"><span data-stu-id="282f8-154">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="282f8-155">准备好下订单后，单击"下 **单**"，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="282f8-155">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="282f8-156">下一步：向用户Teams许可证</span><span class="sxs-lookup"><span data-stu-id="282f8-156">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
