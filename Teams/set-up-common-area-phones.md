---
title: 设置通用区域电话许可证
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
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
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '了解如何为大厅、接待区和会议室设置公共区域电话 '
ms.openlocfilehash: da44a7d66cdc0810405711719f4545caf64007a7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140865"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="1e9d8-103">为 Microsoft Teams 设置公共区域电话许可证</span><span class="sxs-lookup"><span data-stu-id="1e9d8-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="1e9d8-104">常见的区域电话不支持语音邮件。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="1e9d8-105">常用的区域电话通常放置在一个区域中，该区域类似于供许多用户进行呼叫的前厅浏览区域或其他区域。例如，接收区域、会议厅或会议电话。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="1e9d8-106">常用的区域电话设置为设备，而不是用户，并且可以自动登录到网络。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="1e9d8-107">在下面的步骤中，我们将帮助你设置电话系统的帐户，以便为你的组织部署公共的区域电话。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-107">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="1e9d8-108">要获得更完整的会议室体验（包括音频会议），请考虑使用会议室设备购买专用的会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="1e9d8-109">首先，您需要购买一个通用的区域电话（CAP）许可证，并确保您有经过认证的电话。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-109">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="1e9d8-110">若要搜索并了解有关已认证手机的详细信息，请转到 " [Microsoft 团队设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="1e9d8-111">第 1 步 - 购买许可证</span><span class="sxs-lookup"><span data-stu-id="1e9d8-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="1e9d8-112">在 Microsoft 365 管理中心，转到 "**帐单** > **购买服务**"，然后展开 "**其他计划**"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![显示公共区域电话磁贴的屏幕截图](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="1e9d8-114">选择 "**通用区域电话** > **立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="1e9d8-115">在 "签出" 页面上，单击 "**立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-115">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="1e9d8-116">展开 **"加载项订阅**"，然后单击 "购买呼叫计划"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="1e9d8-117">选择 "**国内呼叫计划**" 或 "**国内和国际通话计划**"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="1e9d8-118">如果您使用的是 Microsoft Phone 系统直接路由，则不需要呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-118">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="1e9d8-119">无需添加电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-119">You don't need to add a Phone System license.</span></span> <span data-ttu-id="1e9d8-120">许可证包含在公共区域电话许可证中。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-120">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="1e9d8-121">有关许可证的详细信息，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-121">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="1e9d8-122">通用区域电话许可证支持：</span><span class="sxs-lookup"><span data-stu-id="1e9d8-122">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="1e9d8-123">公共区域电话</span><span class="sxs-lookup"><span data-stu-id="1e9d8-123">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="1e9d8-124">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1e9d8-124">Skype for Business</span></span> |   <span data-ttu-id="1e9d8-125">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="1e9d8-125">&#x2714;</span></span> |
|<span data-ttu-id="1e9d8-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e9d8-126">Microsoft Teams</span></span> |   <span data-ttu-id="1e9d8-127">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="1e9d8-127">&#x2714;</span></span> |
|<span data-ttu-id="1e9d8-128">电话系统</span><span class="sxs-lookup"><span data-stu-id="1e9d8-128">Phone Systems</span></span> |    <span data-ttu-id="1e9d8-129">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="1e9d8-129">&#x2714;</span></span> |
|<span data-ttu-id="1e9d8-130">音频会议</span><span class="sxs-lookup"><span data-stu-id="1e9d8-130">Audio Conferencing</span></span> |       <span data-ttu-id="1e9d8-131">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="1e9d8-131">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="1e9d8-132">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1e9d8-132">Microsoft Intune</span></span> |        <span data-ttu-id="1e9d8-133">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="1e9d8-133">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="1e9d8-134">全球可用性</span><span class="sxs-lookup"><span data-stu-id="1e9d8-134">Worldwide Availability</span></span> |    <span data-ttu-id="1e9d8-135">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="1e9d8-135">&#x2714;</span></span> |
|<span data-ttu-id="1e9d8-136">频道可用性</span><span class="sxs-lookup"><span data-stu-id="1e9d8-136">Channel Availability</span></span> |    <span data-ttu-id="1e9d8-137">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="1e9d8-137">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="1e9d8-138">&sup1;常见的区域电话可以通过会议组织者提供的拨入号码加入音频会议</span><span class="sxs-lookup"><span data-stu-id="1e9d8-138">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="1e9d8-139">&sup2;在主权云中不可用</span><span class="sxs-lookup"><span data-stu-id="1e9d8-139">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="1e9d8-140">第 2 步 - 为手机创建一个新的用户帐户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="1e9d8-140">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="1e9d8-141">在 Microsoft 365 管理中心中，转到 "**用户** > **活动用户** > "**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-141">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="1e9d8-142">输入用户名（如 "Main"）作为第一个名称，输入 "接收" 作为第二个名称。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-142">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="1e9d8-143">如果不自动生成类似 "主接收" 之类的显示名称，请输入一个显示名称。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-143">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="1e9d8-144">输入用户名，如 "MainReception" 或 "Mainlobby"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-144">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="1e9d8-145">对于常见的区域电话，您可能需要手动设置密码或对所有公共区域电话设置密码。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-145">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="1e9d8-146">此外，您可能会考虑清除 "**当用户首次登录时，使此用户更改其密码**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-146">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="1e9d8-147">将许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-147">Assign the licenses to the user.</span></span> <span data-ttu-id="1e9d8-148">在同一页面上，点击展开**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-148">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="1e9d8-149">打开公共区域电话，然后选择**国内呼叫计划**或**国内和国际通话计划**。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-149">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="1e9d8-151">如果您使用的是 Microsoft Phone 系统直接路由，则无需分配呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-151">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="1e9d8-152">有关详细信息，请参阅[添加用户](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-152">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="1e9d8-153">第 3 步 - 将电话号码分配给公共区域电话用户帐户</span><span class="sxs-lookup"><span data-stu-id="1e9d8-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="1e9d8-154">使用 "团队管理中心" 为用户分配一个号码。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-154">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="1e9d8-155">在 "团队" 管理中心中，选择 "**语音** > **电话号码**"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-155">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="1e9d8-156">从电话号码列表中选择一个号码，然后点击**分配**。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-156">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="1e9d8-157">在 "**分配**" 页面上的 "语音用户" 框中，键入将使用该电话的用户的名称，然后在 "**选择语音用户**" 下拉列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-157">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="1e9d8-158">接下来，你需要添加紧急地址。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-158">Next, you need to add an emergency address.</span></span> <span data-ttu-id="1e9d8-159">选择 "**按城市搜索**"、"**按说明搜索**" 或从下拉列表中选择 "**按位置搜索**"，然后在文本框中输入 "城市"、"说明" 或 "位置"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-159">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="1e9d8-160">搜索后，请在 "**选择紧急地址**" 下查看，选择合适的 "紧急地址"。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-160">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="1e9d8-161">点击**保存**，你的用户将显示如下：</span><span class="sxs-lookup"><span data-stu-id="1e9d8-161">Click **Save** and your user should look like this:</span></span>

   ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="1e9d8-163">仅当用户已应用电话系统许可证时，用户才会显示。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-163">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="1e9d8-164">如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="1e9d8-165">有关详细信息，请参阅[为用户获取电话号码](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-165">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="1e9d8-166">您还可以通过其他运营商和 "端口" 获取您的电话号码，或将其转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-166">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="1e9d8-167">请参阅[将电话号码转移给团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1e9d8-167">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


