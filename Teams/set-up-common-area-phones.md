---
title: 为 Microsoft Teams 设置公共区域电话许可证
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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为大厅、接待区和会议室设置公共区域电话 '
ms.openlocfilehash: ea29fac8792c8c52112c34126f463cc3bde9873c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298755"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="90e77-103">为 Microsoft Teams 设置公共区域电话许可证</span><span class="sxs-lookup"><span data-stu-id="90e77-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="90e77-104">常见的区域电话不支持语音邮件。</span><span class="sxs-lookup"><span data-stu-id="90e77-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="90e77-105">常用的区域电话通常放置在一个类似于大厅或另一个区域的区域中, 供许多用户进行呼叫。例如, 接收区域、会议厅或会议电话。</span><span class="sxs-lookup"><span data-stu-id="90e77-105">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="90e77-106">常用的区域电话设置为设备, 而不是用户, 并且可以自动登录到网络。</span><span class="sxs-lookup"><span data-stu-id="90e77-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="90e77-107">在下面的步骤中, 我们将帮助你设置电话系统的帐户, 以便为你的组织部署公共的区域电话。</span><span class="sxs-lookup"><span data-stu-id="90e77-107">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="90e77-108">要获得更完整的会议室体验 (包括音频会议), 请考虑使用会议室设备购买专用的会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="90e77-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="90e77-109">您需要做的第一件工作是购买一个通用的区域电话 (CAP) 许可证, 并确保您有经过认证的电话。</span><span class="sxs-lookup"><span data-stu-id="90e77-109">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="90e77-110">若要搜索并了解有关已认证手机的详细信息, 请转到 " [Microsoft 团队设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)"。</span><span class="sxs-lookup"><span data-stu-id="90e77-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="90e77-111">第 1 步 - 购买许可证</span><span class="sxs-lookup"><span data-stu-id="90e77-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="90e77-112">在 Microsoft 365 管理中心, 转到 "**帐单** > **购买服务**", 然后展开 "**其他计划**"。</span><span class="sxs-lookup"><span data-stu-id="90e77-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![显示公共区域电话磁贴的屏幕截图](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="90e77-114">选择 "**通用区域电话** > **立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="90e77-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="90e77-115">在 "**签出**" 页面上, 单击 "**立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="90e77-115">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="90e77-116">展开 **"加载项订阅**", 然后单击 "购买呼叫计划"。</span><span class="sxs-lookup"><span data-stu-id="90e77-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="90e77-117">选择 "**国内呼叫计划**" 或 "**国内和国际通话计划**"。</span><span class="sxs-lookup"><span data-stu-id="90e77-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="90e77-118">不需要电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="90e77-118">You don't need a Phone System license.</span></span> <span data-ttu-id="90e77-119">许可证包含在公共区域电话许可证中。</span><span class="sxs-lookup"><span data-stu-id="90e77-119">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="90e77-120">有关许可证的详细信息, 请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="90e77-120">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="90e77-121">第 2 步 - 为手机创建一个新的用户帐户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="90e77-121">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="90e77-122">在 Microsoft 365 管理中心中, 转到 "**用户** > **活动用户** > "**添加用户**。</span><span class="sxs-lookup"><span data-stu-id="90e77-122">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="90e77-123">输入用户名 (如 "Main") 作为第一个名称, 输入 "接收" 作为第二个名称。</span><span class="sxs-lookup"><span data-stu-id="90e77-123">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="90e77-124">如果不自动生成类似 "主接收" 之类的显示名称, 请输入一个显示名称。</span><span class="sxs-lookup"><span data-stu-id="90e77-124">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="90e77-125">输入用户名, 如 "MainReception" 或 "Mainlobby"。</span><span class="sxs-lookup"><span data-stu-id="90e77-125">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="90e77-126">对于常见的区域电话, 您可能需要手动设置密码或对所有公共区域电话设置密码。</span><span class="sxs-lookup"><span data-stu-id="90e77-126">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="90e77-127">此外, 您可能会考虑清除 "**当用户首次登录时, 使此用户更改其密码**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="90e77-127">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="90e77-128">将许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="90e77-128">Assign the licenses to the user.</span></span> <span data-ttu-id="90e77-129">在同一页面上，点击展开**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="90e77-129">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="90e77-130">打开公共区域电话, 然后选择**国内呼叫计划**或**国内和国际通话计划**。</span><span class="sxs-lookup"><span data-stu-id="90e77-130">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="90e77-132">有关详细信息, 请参阅[添加用户](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="90e77-132">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="90e77-133">第 3 步 - 将电话号码分配给公共区域电话用户帐户</span><span class="sxs-lookup"><span data-stu-id="90e77-133">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="90e77-134">使用 Skype for Business 管理中心为用户分配一个号码。</span><span class="sxs-lookup"><span data-stu-id="90e77-134">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="90e77-135">在 Microsoft 365 管理中心, 选择 "**管理中心** > "**团队 & Skype** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="90e77-135">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="90e77-136">在 Skype for business 管理中心, 选择 "**语音** > **电话号码**"。</span><span class="sxs-lookup"><span data-stu-id="90e77-136">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="90e77-137">从电话号码列表中选择一个号码，然后点击**分配**。</span><span class="sxs-lookup"><span data-stu-id="90e77-137">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="90e77-138">在 "**分配**" 页面上的 "语音用户" 框中, 键入将使用该电话的用户的名称, 然后在 "**选择语音用户**" 下拉列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="90e77-138">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="90e77-139">此时你还需要添加一个紧急联系地址。</span><span class="sxs-lookup"><span data-stu-id="90e77-139">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="90e77-140">选择 "**按城市搜索**"、"**按说明搜索**" 或从下拉列表中选择 "**按位置搜索**", 然后在文本框中输入 "城市"、"说明" 或 "位置"。</span><span class="sxs-lookup"><span data-stu-id="90e77-140">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="90e77-141">搜索后, 请在 "**选择紧急地址**" 下查看, 选择合适的 "紧急地址"。</span><span class="sxs-lookup"><span data-stu-id="90e77-141">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="90e77-142">点击**保存**，你的用户将显示如下：</span><span class="sxs-lookup"><span data-stu-id="90e77-142">Click **Save** and your user should look like this:</span></span>

   ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="90e77-144">仅当用户已应用电话系统许可证时, 用户才会显示。</span><span class="sxs-lookup"><span data-stu-id="90e77-144">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="90e77-145">如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="90e77-145">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="90e77-146">有关详细信息, 请参阅[为用户获取电话号码](/microsoftteams/getting-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="90e77-146">For more information, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="90e77-147">您还可以通过其他运营商和 "端口" 获取您的电话号码, 或将其转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="90e77-147">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="90e77-148">请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="90e77-148">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


