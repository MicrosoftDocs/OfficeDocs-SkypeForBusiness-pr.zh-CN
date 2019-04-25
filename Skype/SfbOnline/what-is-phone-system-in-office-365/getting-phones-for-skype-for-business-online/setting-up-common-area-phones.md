---
title: 设置公共区域电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解获取正确的固件，如果需要对其进行更新、 分配许可证和为公用区域电话配置设置的部署步骤。
ms.openlocfilehash: b92cef4234823c53faf6193d2e9e90fe3e5b60f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231152"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="29c8e-103">设置公共区域电话</span><span class="sxs-lookup"><span data-stu-id="29c8e-103">Set up common area phones</span></span>
<span data-ttu-id="29c8e-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="29c8e-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="29c8e-107">公共区域电话的先决条件</span><span class="sxs-lookup"><span data-stu-id="29c8e-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="29c8e-108">你需要做的第一件事是确认你拥有以下组件：</span><span class="sxs-lookup"><span data-stu-id="29c8e-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="29c8e-109">购买公共区域电话许可证和通话套餐。</span><span class="sxs-lookup"><span data-stu-id="29c8e-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="29c8e-110">搜索并购买批准的手机（[在此处](deploying-skype-for-business-online-phones.md)查看列表）。</span><span class="sxs-lookup"><span data-stu-id="29c8e-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="29c8e-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="29c8e-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="29c8e-113">**Polycom VVX 电话**： 转到**设置** > **状态** > **平台** > **应用程序** > **主**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="29c8e-114">**Yealink 电话**： 主要电话屏幕上转到**状态**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="29c8e-115">**AudioCodes 电话**： 转到**菜单** > **设备状态** > 从开始屏幕的**固件版本**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="29c8e-116">**Lync Phone Edition (LPE) 电话**： 转到**菜单** > **系统信息**开始屏幕。</span><span class="sxs-lookup"><span data-stu-id="29c8e-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="29c8e-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="29c8e-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="29c8e-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="29c8e-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="29c8e-121">设置公共区域电话</span><span class="sxs-lookup"><span data-stu-id="29c8e-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="29c8e-122">你需要按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="29c8e-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="29c8e-123">第 1 步 - 购买许可证</span><span class="sxs-lookup"><span data-stu-id="29c8e-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="29c8e-124">在 Office 365 管理中心，转至**账单** > **购买服务**，然后添加**其他计划**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="29c8e-126">在\*\* 结账**页面上点击 >  \*\*  公共区域电话\*\*\*\* \*\* 立即购买，点击** 立即购买\*\* 。</span><span class="sxs-lookup"><span data-stu-id="29c8e-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="29c8e-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="29c8e-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="29c8e-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="29c8e-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="29c8e-131">有关许可证的更多信息，请参阅 [Skype for Business 和 Microsoft Teams 外接程序许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="29c8e-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="29c8e-132">第 2 步 - 为手机创建一个新的用户帐户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="29c8e-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="29c8e-133">在 Office 365 管理中心，转至**用户** > **活动用户** > **添加用户**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="29c8e-134">输入**用户名**，如“Main”为第一个词，“Reception”为第二个词。</span><span class="sxs-lookup"><span data-stu-id="29c8e-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="29c8e-135">如果没有自动生成“Main Reception”用户名，则输入**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="29c8e-136">输入一个**用户名**，如“MainReception”或“Mainlobby”。</span><span class="sxs-lookup"><span data-stu-id="29c8e-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="29c8e-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="29c8e-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="29c8e-139">如果你仍在该页面，将许可证分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="29c8e-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="29c8e-140">在同一页面上，点击展开**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="29c8e-141">打开以下内容：</span><span class="sxs-lookup"><span data-stu-id="29c8e-141">Turn on the following:</span></span>
   - <span data-ttu-id="29c8e-142">公共区域电话</span><span class="sxs-lookup"><span data-stu-id="29c8e-142">Common Area Phone</span></span>
   - <span data-ttu-id="29c8e-143">然后需选择一个**国内通话套餐**或国内和**国际通话套餐**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="29c8e-144">许可证的分配将如下所示：</span><span class="sxs-lookup"><span data-stu-id="29c8e-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="29c8e-146">如你所知，Skype for Business 套餐 2 包含在**公共区域电话**许可证中。</span><span class="sxs-lookup"><span data-stu-id="29c8e-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="29c8e-147">有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="29c8e-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="29c8e-148">第 3 步 - 将电话号码分配给公共区域电话用户帐户</span><span class="sxs-lookup"><span data-stu-id="29c8e-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="29c8e-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 使用 **Skype for Business 管理中心**将电话号码分配给用户</span><span class="sxs-lookup"><span data-stu-id="29c8e-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="29c8e-150">在**中心管理**Office 365 admin center > > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-150">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="29c8e-151">在 **Skype for Business 管理中心** >  **语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="29c8e-152">从电话号码列表中选择一个号码，然后点击**分配**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="29c8e-153">在**分配**页面的**语音用户**框中，输入用于电话的用户名称，然后在**选择语音用户**下拉列表中选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="29c8e-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="29c8e-154">此时你还需要添加一个紧急联系地址。</span><span class="sxs-lookup"><span data-stu-id="29c8e-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="29c8e-155">开始搜索时，在**选择紧急联系地址**下选择一个合适的地址。</span><span class="sxs-lookup"><span data-stu-id="29c8e-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="29c8e-156">点击**保存**，你的用户将显示如下：</span><span class="sxs-lookup"><span data-stu-id="29c8e-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="29c8e-158">用户只有应用了一个**电话系统**许可证，才会显示。</span><span class="sxs-lookup"><span data-stu-id="29c8e-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="29c8e-159">如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="29c8e-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="29c8e-160">有关更多内容，请参阅[为用户获取电话号码](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="29c8e-160">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="29c8e-161">如果你正在漫游，也可以把另一家电信公司的电话号码“*导出*”或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="29c8e-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="29c8e-162">请参阅[传输到 Office 365 的电话号码](/microsoftteams/transfer-phone-numbers-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="29c8e-162">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="29c8e-163">第 4 步 - 设置电话</span><span class="sxs-lookup"><span data-stu-id="29c8e-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="29c8e-164">**设置电话模式**</span><span class="sxs-lookup"><span data-stu-id="29c8e-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="29c8e-165">你的电话必须打开**公共区域电话模式**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="29c8e-166">建议手动检查以确认。</span><span class="sxs-lookup"><span data-stu-id="29c8e-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="29c8e-167">**以下是如何设置宝利通 VVX 电话的示例**</span><span class="sxs-lookup"><span data-stu-id="29c8e-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="29c8e-168">通过以下步骤为宝利通 VVX 启用公共区域电话模式：</span><span class="sxs-lookup"><span data-stu-id="29c8e-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="29c8e-169">在浏览器中，连接到 Web 界面以便启用 CAP 模式。</span><span class="sxs-lookup"><span data-stu-id="29c8e-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="29c8e-170">然后进入**设置**并在 **Skype for Business 设置**选项中选择**公共区域电话**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="29c8e-171">点击**是**保存设置。</span><span class="sxs-lookup"><span data-stu-id="29c8e-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="29c8e-172">CAP 模式已启用，请使用电话的显示器设置电话。</span><span class="sxs-lookup"><span data-stu-id="29c8e-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="29c8e-173">显示屏应显示 **CAP 已启用**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="29c8e-174">然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="29c8e-174">Then do the following:</span></span>

    1. <span data-ttu-id="29c8e-175">点击**设置**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="29c8e-176">选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="29c8e-177">输入密码。</span><span class="sxs-lookup"><span data-stu-id="29c8e-177">Enter the password.</span></span>
    4. <span data-ttu-id="29c8e-178">在**管理设置**，选择**公共区域电话设置**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="29c8e-179">启用 **CAP** 和 **CAP 管理模式**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="29c8e-180">点击**保存配置**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-180">Click **Save Config**.</span></span>

- <span data-ttu-id="29c8e-181">现在，电话已准备就绪，你可以在主屏幕上登录。</span><span class="sxs-lookup"><span data-stu-id="29c8e-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="29c8e-182">通过选择**设置** > **功能** > **Skype for Business** 登录。</span><span class="sxs-lookup"><span data-stu-id="29c8e-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="29c8e-183">选择**用户凭证**，然后选择 **Web 登录 (CAP)** 生成一个代码。</span><span class="sxs-lookup"><span data-stu-id="29c8e-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="29c8e-184">转至[设置门户](https://aka.ms/skypecap)，并登录为**管理员**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="29c8e-185">输入显示名称（例如，Main Reception）。</span><span class="sxs-lookup"><span data-stu-id="29c8e-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="29c8e-186">如果**仅搜索公共区域电话**被选中，清除该复选框并重新搜索。</span><span class="sxs-lookup"><span data-stu-id="29c8e-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="29c8e-187">在配对代码窗口中，输入电话上显示的代码并单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="29c8e-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="29c8e-188">执行最后一步之后，电话应自动登录。</span><span class="sxs-lookup"><span data-stu-id="29c8e-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="29c8e-189">CAP 设置站点声明它将 CAP 帐户的密码重置为随机密码。</span><span class="sxs-lookup"><span data-stu-id="29c8e-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="29c8e-190">请注意，CAP 所指的帐户是 Azure Active Directory (AAD) 帐户。</span><span class="sxs-lookup"><span data-stu-id="29c8e-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="29c8e-191">如果仅在 AAD 中创建了帐户，则该过程非常简单。</span><span class="sxs-lookup"><span data-stu-id="29c8e-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="29c8e-192">如果已同步本地 Active Directory AAD 到并使用第三方 IDP 或 ADFS，帽设置将会失败。</span><span class="sxs-lookup"><span data-stu-id="29c8e-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="29c8e-193">在这种情况下，您需要使用 Office 365/Azure 仅用于 Active Directory 帐户 （例如，使用**onmicrosoft.com**域的帐户） 用于帽设置工作。</span><span class="sxs-lookup"><span data-stu-id="29c8e-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="29c8e-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="29c8e-194">Related topics</span></span>

- <span data-ttu-id="29c8e-195">阅读[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)，详细了解可用电话。</span><span class="sxs-lookup"><span data-stu-id="29c8e-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="29c8e-196">获取适用于 Skype for Business Online 的手机</span><span class="sxs-lookup"><span data-stu-id="29c8e-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


