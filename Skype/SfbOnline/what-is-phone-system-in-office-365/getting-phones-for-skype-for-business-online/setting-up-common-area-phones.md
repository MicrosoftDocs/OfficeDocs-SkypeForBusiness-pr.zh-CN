---
title: 设置公共区域电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: a2abc74960b04b7b39e4e31961c849009fb9543f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23248333"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="96aa7-103">设置公共区域电话</span><span class="sxs-lookup"><span data-stu-id="96aa7-103">Set up common area phones</span></span>
<span data-ttu-id="96aa7-104">公共区域电话 (CAP) 通常放置在诸如大厅或另一个可供很多人使用的的区域。</span><span class="sxs-lookup"><span data-stu-id="96aa7-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="96aa7-105">例如，CAP 可以是接待室电话、门铃电话或会议室电话，它们设置为设备而不是用户并自动登录网络。</span><span class="sxs-lookup"><span data-stu-id="96aa7-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="96aa7-106">在以下步骤中，我们将帮助你设置带通话套餐的电话系统帐户，以便你为组织部署这些类型的电话。</span><span class="sxs-lookup"><span data-stu-id="96aa7-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="96aa7-107">公共区域电话的先决条件</span><span class="sxs-lookup"><span data-stu-id="96aa7-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="96aa7-108">你需要做的第一件事是确认你拥有以下组件：</span><span class="sxs-lookup"><span data-stu-id="96aa7-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="96aa7-109">购买公共区域电话许可证和通话套餐。</span><span class="sxs-lookup"><span data-stu-id="96aa7-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="96aa7-110">搜索并购买批准的手机（[在此处](deploying-skype-for-business-online-phones.md)查看列表）。</span><span class="sxs-lookup"><span data-stu-id="96aa7-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
 - <span data-ttu-id="96aa7-111">更新手机上的固件（请参阅[本主题](getting-phones-for-skype-for-business-online.md)中支持的固件 ）。</span><span class="sxs-lookup"><span data-stu-id="96aa7-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="96aa7-112">可通过以下方式检查手机上的固件：</span><span class="sxs-lookup"><span data-stu-id="96aa7-112">You can check the firmware on you phone by doing this:</span></span>
    - <span data-ttu-id="96aa7-113">**Polycom VVX 电话**： 转到**设置** > **状态** > **平台** > **应用程序** > **主**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="96aa7-114">**Yealink 电话**： 主要电话屏幕上转到**状态**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="96aa7-115">**AudioCodes 电话**： 转到**菜单** > **设备状态** > 从开始屏幕的**固件版本**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    - <span data-ttu-id="96aa7-116">**Lync Phone Edition (LPE) 电话**： 转到**菜单** > **系统信息**开始屏幕。</span><span class="sxs-lookup"><span data-stu-id="96aa7-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="96aa7-117">固件更新由 Skype for Business 服务管理。</span><span class="sxs-lookup"><span data-stu-id="96aa7-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="96aa7-118">每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。</span><span class="sxs-lookup"><span data-stu-id="96aa7-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="96aa7-119">根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。</span><span class="sxs-lookup"><span data-stu-id="96aa7-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="96aa7-120">您可以通过使用[Set CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet 并将*EnableDeviceUpdate*参数设置为禁用设备更新设置`false`。</span><span class="sxs-lookup"><span data-stu-id="96aa7-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="96aa7-121">设置公共区域电话</span><span class="sxs-lookup"><span data-stu-id="96aa7-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="96aa7-122">你需要按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="96aa7-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="96aa7-123">第 1 步 - 购买许可证</span><span class="sxs-lookup"><span data-stu-id="96aa7-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="96aa7-124">在 Office 365 管理中心，转至**账单** > **购买服务**，然后添加**其他计划**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="96aa7-126">在** 结账**页面上点击 >  **  公共区域电话**** ** 立即购买，点击** 立即购买** 。</span><span class="sxs-lookup"><span data-stu-id="96aa7-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="96aa7-127">点击展开**外接程序订阅**，然后点击购买通话套餐。</span><span class="sxs-lookup"><span data-stu-id="96aa7-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="96aa7-128">选择**国内调用计划**或**规划国内和国际呼叫**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="96aa7-129">不需要电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="96aa7-129">You don't need a Phone System license.</span></span> <span data-ttu-id="96aa7-130">许可证包含在**公共区域电话**许可证中。</span><span class="sxs-lookup"><span data-stu-id="96aa7-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="96aa7-131">有关许可证的更多信息，请参阅 [Skype for Business 和 Microsoft Teams 外接程序许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="96aa7-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="96aa7-132">第 2 步 - 为手机创建一个新的用户帐户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="96aa7-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="96aa7-133">在 Office 365 管理中心，转至**用户** > **活动用户** > **添加用户**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="96aa7-134">输入**用户名**，如“Main”为第一个词，“Reception”为第二个词。</span><span class="sxs-lookup"><span data-stu-id="96aa7-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="96aa7-135">如果没有自动生成“Main Reception”用户名，则输入**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="96aa7-136">输入一个**用户名**，如“MainReception”或“Mainlobby”。</span><span class="sxs-lookup"><span data-stu-id="96aa7-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="96aa7-137">对于公共区域电话，你可能需要手动设置密码，或为所有公共区域电话设置相同的密码。</span><span class="sxs-lookup"><span data-stu-id="96aa7-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="96aa7-138">另外，你可能会考虑取消选择**让用户在第一次登录时更改密码**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="96aa7-139">且慢！！</span><span class="sxs-lookup"><span data-stu-id="96aa7-139">WAIT!!</span></span> <span data-ttu-id="96aa7-140">请勿点击**添加**！！</span><span class="sxs-lookup"><span data-stu-id="96aa7-140">Don't click **Add**!!</span></span> <span data-ttu-id="96aa7-141">如果你点击了**添加**，则依次选择：Office 365 管理中心 > **用户** > **活动用户**，然后找到用户。</span><span class="sxs-lookup"><span data-stu-id="96aa7-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="96aa7-142">然后在用户的属性页面上点击**产品许可证**，然后点击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="96aa7-143">在**产品许可证**页面，打开**公共区域电话**，然后选择一个**国内通话套餐**或国内和**国际通话套餐**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="96aa7-144">如果你仍在该页面，将许可证分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="96aa7-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="96aa7-145">在同一页面上，点击展开**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="96aa7-146">打开以下内容：</span><span class="sxs-lookup"><span data-stu-id="96aa7-146">Turn on the following:</span></span>
    - <span data-ttu-id="96aa7-147">公共区域电话</span><span class="sxs-lookup"><span data-stu-id="96aa7-147">Common Area Phone</span></span>
    - <span data-ttu-id="96aa7-148">然后需选择一个**国内通话套餐**或国内和**国际通话套餐**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

    <span data-ttu-id="96aa7-149">许可证的分配将如下所示：</span><span class="sxs-lookup"><span data-stu-id="96aa7-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="96aa7-151">如你所知，Skype for Business 套餐 2 包含在**公共区域电话**许可证中。</span><span class="sxs-lookup"><span data-stu-id="96aa7-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="96aa7-152">有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="96aa7-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="96aa7-153">第 3 步 - 将电话号码分配给公共区域电话用户帐户</span><span class="sxs-lookup"><span data-stu-id="96aa7-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="96aa7-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 使用 **Skype for Business 管理中心**将电话号码分配给用户</span><span class="sxs-lookup"><span data-stu-id="96aa7-154">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="96aa7-155">在 Office 365 管理中心 >**管理中心** > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-155">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="96aa7-156">在 **Skype for Business 管理中心** >  **语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="96aa7-157">从电话号码列表中选择一个号码，然后点击**分配**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="96aa7-158">在**分配**页面的**语音用户**框中，输入用于电话的用户名称，然后在**选择语音用户**下拉列表中选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="96aa7-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="96aa7-159">此时你还需要添加一个紧急联系地址。</span><span class="sxs-lookup"><span data-stu-id="96aa7-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="96aa7-160">开始搜索时，在**选择紧急联系地址**下选择一个合适的地址。</span><span class="sxs-lookup"><span data-stu-id="96aa7-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="96aa7-161">点击**保存**，你的用户将显示如下：</span><span class="sxs-lookup"><span data-stu-id="96aa7-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="96aa7-163">用户只有应用了一个**电话系统**许可证，才会显示。</span><span class="sxs-lookup"><span data-stu-id="96aa7-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="96aa7-164">如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="96aa7-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="96aa7-165">有关更多内容，请参阅[为用户获取电话号码](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="96aa7-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="96aa7-166">如果你正在漫游，也可以把另一家电信公司的电话号码“*导出*”或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="96aa7-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="96aa7-167">请参阅[传输到 Office 365 的电话号码](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="96aa7-167">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="96aa7-168">第 4 步 - 设置电话</span><span class="sxs-lookup"><span data-stu-id="96aa7-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="96aa7-169">**设置电话模式**</span><span class="sxs-lookup"><span data-stu-id="96aa7-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="96aa7-170">你的电话必须打开**公共区域电话模式**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="96aa7-171">建议手动检查以确认。</span><span class="sxs-lookup"><span data-stu-id="96aa7-171">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="96aa7-172">**以下是如何设置宝利通 VVX 电话的示例**</span><span class="sxs-lookup"><span data-stu-id="96aa7-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="96aa7-173">通过以下步骤为宝利通 VVX 启用公共区域电话模式：</span><span class="sxs-lookup"><span data-stu-id="96aa7-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="96aa7-174">在浏览器中，连接到 Web 界面以便启用 CAP 模式。</span><span class="sxs-lookup"><span data-stu-id="96aa7-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="96aa7-175">然后进入**设置**并在 **Skype for Business 设置**选项中选择**公共区域电话**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="96aa7-176">点击**是**保存设置。</span><span class="sxs-lookup"><span data-stu-id="96aa7-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="96aa7-177">CAP 模式已启用，请使用电话的显示器设置电话。</span><span class="sxs-lookup"><span data-stu-id="96aa7-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="96aa7-178">显示屏应显示 **CAP 已启用**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="96aa7-179">然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="96aa7-179">Then do the following:</span></span>

    1. <span data-ttu-id="96aa7-180">点击**设置**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="96aa7-181">选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-181">Select **Advanced**.</span></span>
    3. <span data-ttu-id="96aa7-182">输入密码。</span><span class="sxs-lookup"><span data-stu-id="96aa7-182">Enter the password.</span></span>
    4. <span data-ttu-id="96aa7-183">在**管理设置**，选择**公共区域电话设置**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="96aa7-184">启用 **CAP** 和 **CAP 管理模式**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="96aa7-185">点击**保存配置**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-185">Click **Save Config**.</span></span>

- <span data-ttu-id="96aa7-186">现在，电话已准备就绪，你可以在主屏幕上登录。</span><span class="sxs-lookup"><span data-stu-id="96aa7-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="96aa7-187">通过选择**设置** > **功能** > **Skype for Business** 登录。</span><span class="sxs-lookup"><span data-stu-id="96aa7-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="96aa7-188">选择**用户凭证**，然后选择 **Web 登录 (CAP)** 生成一个代码。</span><span class="sxs-lookup"><span data-stu-id="96aa7-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="96aa7-189">转至[设置门户](https://aka.ms/skypecap)，并登录为**管理员**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-189">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="96aa7-190">输入显示名称（例如，Main Reception）。</span><span class="sxs-lookup"><span data-stu-id="96aa7-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="96aa7-191">如果**仅搜索公共区域电话**被选中，清除该复选框并重新搜索。</span><span class="sxs-lookup"><span data-stu-id="96aa7-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="96aa7-192">在配对代码窗口中，输入电话上显示的代码并单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="96aa7-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="96aa7-193">执行最后一步之后，电话应自动登录。</span><span class="sxs-lookup"><span data-stu-id="96aa7-193">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="96aa7-194">CAP 设置站点声明它将 CAP 帐户的密码重置为随机密码。</span><span class="sxs-lookup"><span data-stu-id="96aa7-194">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="96aa7-195">请注意，CAP 所指的帐户是 Azure Active Directory (AAD) 帐户。</span><span class="sxs-lookup"><span data-stu-id="96aa7-195">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="96aa7-196">如果仅在 AAD 中创建了帐户，则该过程非常简单。</span><span class="sxs-lookup"><span data-stu-id="96aa7-196">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="96aa7-197">如果已将本地 Active Directory 同步到 AAD，请确保记下正在使用的凭据，这些凭据将在 CAP 设置中更改。</span><span class="sxs-lookup"><span data-stu-id="96aa7-197">If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="96aa7-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="96aa7-198">Related topics</span></span>

- <span data-ttu-id="96aa7-199">阅读[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)，详细了解可用电话。</span><span class="sxs-lookup"><span data-stu-id="96aa7-199">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="96aa7-200">获取适用于 Skype for Business Online 的电话</span><span class="sxs-lookup"><span data-stu-id="96aa7-200">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


