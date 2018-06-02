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
description: 了解部署步骤以获取正确的固件、根据需要进行更新、分配许可证并配置公共区域电话的设置。
ms.openlocfilehash: ef5f1de6af237d26571e6914087a01341808dbaa
ms.sourcegitcommit: 10eb49f35e5d76e483b6f5af13d59c3059d66acf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
ms.locfileid: "19403756"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="c888b-103">设置公共区域电话</span><span class="sxs-lookup"><span data-stu-id="c888b-103">Set up common area phones</span></span>
<span data-ttu-id="c888b-104">公共区域电话 (CAP) 通常放置在诸如大厅或另一个可供很多人使用的的区域。</span><span class="sxs-lookup"><span data-stu-id="c888b-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="c888b-105">例如，CAP 可以是接待室电话、门铃电话或会议室电话，它们设置为设备而不是用户并自动登录网络。</span><span class="sxs-lookup"><span data-stu-id="c888b-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="c888b-106">在以下步骤中，我们将帮助你设置带通话套餐的电话系统帐户，以便你为组织部署这些类型的电话。</span><span class="sxs-lookup"><span data-stu-id="c888b-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="c888b-107">公共区域电话的先决条件</span><span class="sxs-lookup"><span data-stu-id="c888b-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="c888b-108">你需要做的第一件事是确认你拥有以下组件：</span><span class="sxs-lookup"><span data-stu-id="c888b-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="c888b-109">购买公共区域电话许可证和通话套餐。</span><span class="sxs-lookup"><span data-stu-id="c888b-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="c888b-110">搜索并购买批准的手机（[在此处](deploying-skype-for-business-online-phones.md)查看列表）。</span><span class="sxs-lookup"><span data-stu-id="c888b-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="c888b-111">更新手机上的固件（请参阅[本主题](getting-phones-for-skype-for-business-online.md)中支持的固件 ）。</span><span class="sxs-lookup"><span data-stu-id="c888b-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="c888b-112">可通过以下方式检查手机上的固件：</span><span class="sxs-lookup"><span data-stu-id="c888b-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="c888b-113">**宝利通 VVX 电话**：转至**设置** > **状态** > **平台** > **应用程序** > **主菜单**。</span><span class="sxs-lookup"><span data-stu-id="c888b-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="c888b-114">**亿联电话**：转至电话主屏幕上的**状态**。</span><span class="sxs-lookup"><span data-stu-id="c888b-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="c888b-115">**奥科电话**：从开始屏幕转至**菜单** > **设备状态** > **固件版本**。</span><span class="sxs-lookup"><span data-stu-id="c888b-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="c888b-116">**Lync Phone Edition (LPE) 电话**：从开始屏幕转至**菜单** > **系统信息**。</span><span class="sxs-lookup"><span data-stu-id="c888b-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="c888b-117">固件更新由 Skype for Business 服务管理。</span><span class="sxs-lookup"><span data-stu-id="c888b-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="c888b-118">每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。</span><span class="sxs-lookup"><span data-stu-id="c888b-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="c888b-119">根据电话的非活动时间和轮询间隔，电话将自动下载并安装最新认证的版本。</span><span class="sxs-lookup"><span data-stu-id="c888b-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="c888b-120">你可以通过使用 [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet 并将 *EnableDeviceUpdate* 参数设置为 `false` 来禁用设备更新设置。</span><span class="sxs-lookup"><span data-stu-id="c888b-120">You can disable the device update settings using the [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="c888b-121">设置公共区域电话</span><span class="sxs-lookup"><span data-stu-id="c888b-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="c888b-122">你需要按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c888b-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="c888b-123">第 1 步 - 购买许可证</span><span class="sxs-lookup"><span data-stu-id="c888b-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="c888b-124">在 Office 365 管理中心，转至**账单** > **购买服务**，然后添加**其他计划**。</span><span class="sxs-lookup"><span data-stu-id="c888b-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="c888b-126">在** 结账**页面上点击 >  **  公共区域电话**** ** 立即购买，点击** 立即购买** 。</span><span class="sxs-lookup"><span data-stu-id="c888b-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="c888b-127">点击展开**外接程序订阅**，然后点击购买通话套餐。</span><span class="sxs-lookup"><span data-stu-id="c888b-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="c888b-128">选择**国内通话套餐**或**国内和国际通话套餐**。</span><span class="sxs-lookup"><span data-stu-id="c888b-128">Domestic Calling Plan, or Domestic and International Calling Plan</span></span>

> [!Note]
> <span data-ttu-id="c888b-129">不需要电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="c888b-129">You don't need a Phone System license.</span></span> <span data-ttu-id="c888b-130">许可证包含在**公共区域电话**许可证中。</span><span class="sxs-lookup"><span data-stu-id="c888b-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="c888b-131">有关许可证的更多信息，请参阅 [Skype for Business 和 Microsoft Teams 外接程序许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="c888b-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="c888b-132">第 2 步 - 为手机创建一个新的用户帐户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="c888b-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="c888b-133">在 Office 365 管理中心，转至**用户** > **活动用户** > **添加用户**。</span><span class="sxs-lookup"><span data-stu-id="c888b-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="c888b-134">输入**用户名**，如“Main”为第一个词，“Reception”为第二个词。</span><span class="sxs-lookup"><span data-stu-id="c888b-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="c888b-135">如果没有自动生成“Main Reception”用户名，则输入**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="c888b-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="c888b-136">输入一个**用户名**，如“MainReception”或“Mainlobby”。</span><span class="sxs-lookup"><span data-stu-id="c888b-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="c888b-137">对于公共区域电话，你可能需要手动设置密码，或为所有公共区域电话设置相同的密码。</span><span class="sxs-lookup"><span data-stu-id="c888b-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="c888b-138">另外，你可能会考虑取消选择**让用户在第一次登录时更改密码**。</span><span class="sxs-lookup"><span data-stu-id="c888b-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="c888b-139">且慢！！</span><span class="sxs-lookup"><span data-stu-id="c888b-139">WAIT!!</span></span> <span data-ttu-id="c888b-140">请勿点击**添加**！！</span><span class="sxs-lookup"><span data-stu-id="c888b-140">Don't click **Add**!!</span></span> <span data-ttu-id="c888b-141">如果你点击了**添加**，则依次选择：Office 365 管理中心 > **用户** > **活动用户**，然后找到用户。</span><span class="sxs-lookup"><span data-stu-id="c888b-141">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="c888b-142">然后在用户的属性页面上点击**产品许可证**，然后点击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c888b-142">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="c888b-143">在**产品许可证**页面，打开**公共区域电话**，然后选择一个**国内通话套餐**或国内和**国际通话套餐**。</span><span class="sxs-lookup"><span data-stu-id="c888b-143">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="c888b-144">如果你仍在该页面，将许可证分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="c888b-144">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="c888b-145">在同一页面上，点击展开**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="c888b-145">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="c888b-146">打开以下内容：</span><span class="sxs-lookup"><span data-stu-id="c888b-146">Turn on the following:</span></span>
    - <span data-ttu-id="c888b-147">公共区域电话</span><span class="sxs-lookup"><span data-stu-id="c888b-147">Common Area Phone</span></span>
    - <span data-ttu-id="c888b-148">然后需选择一个**国内通话套餐**或国内和**国际通话套餐**。</span><span class="sxs-lookup"><span data-stu-id="c888b-148">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="c888b-149">许可证的分配将如下所示：</span><span class="sxs-lookup"><span data-stu-id="c888b-149">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="c888b-151">如你所知，Skype for Business 套餐 2 包含在**公共区域电话**许可证中。</span><span class="sxs-lookup"><span data-stu-id="c888b-151">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="c888b-152">有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="c888b-152">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="c888b-153">第 3 步 - 将电话号码分配给公共区域电话用户帐户</span><span class="sxs-lookup"><span data-stu-id="c888b-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="c888b-154">[sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 使用 **Skype for Business 管理中心**将电话号码分配给用户</span><span class="sxs-lookup"><span data-stu-id="c888b-154">[sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="c888b-155">在 Office 365 管理中心，转至**管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="c888b-155">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="c888b-156">在 **Skype for Business 管理中心** >  **语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="c888b-156">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="c888b-157">从电话号码列表中选择一个号码，然后点击**分配**。</span><span class="sxs-lookup"><span data-stu-id="c888b-157">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="c888b-158">在**分配**页面的**语音用户**框中，输入用于电话的用户名称，然后在**选择语音用户**下拉列表中选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="c888b-158">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="c888b-159">此时你还需要添加一个紧急联系地址。</span><span class="sxs-lookup"><span data-stu-id="c888b-159">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="c888b-160">开始搜索时，在**选择紧急联系地址**下选择一个合适的地址。</span><span class="sxs-lookup"><span data-stu-id="c888b-160">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="c888b-161">点击**保存**，你的用户将显示如下：</span><span class="sxs-lookup"><span data-stu-id="c888b-161">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="c888b-163">用户只有应用了一个**电话系统**许可证，才会显示。</span><span class="sxs-lookup"><span data-stu-id="c888b-163">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="c888b-164">如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。</span><span class="sxs-lookup"><span data-stu-id="c888b-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="c888b-165">有关更多内容，请参阅[为用户获取电话号码](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c888b-165">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="c888b-166">如果你正在漫游，也可以把另一家电信公司的电话号码“*导出*”或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c888b-166">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="c888b-167">请参阅[将电话号码转移到 Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c888b-167">See [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) for more information.</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="c888b-168">第 4 步 - 设置电话</span><span class="sxs-lookup"><span data-stu-id="c888b-168">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="c888b-169">**设置电话模式**</span><span class="sxs-lookup"><span data-stu-id="c888b-169">**Setting the mode on a phone**</span></span>

<span data-ttu-id="c888b-170">你的电话必须打开**公共区域电话模式**。</span><span class="sxs-lookup"><span data-stu-id="c888b-170">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="c888b-171">建议手动检查以确认。</span><span class="sxs-lookup"><span data-stu-id="c888b-171">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="c888b-172">**以下是如何设置宝利通 VVX 电话的示例**</span><span class="sxs-lookup"><span data-stu-id="c888b-172">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="c888b-173">通过以下步骤为宝利通 VVX 启用公共区域电话模式：</span><span class="sxs-lookup"><span data-stu-id="c888b-173">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="c888b-174">在浏览器中，连接到 Web 界面以便启用 CAP 模式。</span><span class="sxs-lookup"><span data-stu-id="c888b-174">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="c888b-175">然后进入**设置**并在 **Skype for Business 设置**选项中选择**公共区域电话**。</span><span class="sxs-lookup"><span data-stu-id="c888b-175">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="c888b-176">点击**是**保存设置。</span><span class="sxs-lookup"><span data-stu-id="c888b-176">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="c888b-177">CAP 模式已启用，请使用电话的显示器设置电话。</span><span class="sxs-lookup"><span data-stu-id="c888b-177">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="c888b-178">显示屏应显示 **CAP 已启用**。</span><span class="sxs-lookup"><span data-stu-id="c888b-178">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="c888b-179">然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c888b-179">Then do the following:</span></span>

    1. <span data-ttu-id="c888b-180">点击**设置**。</span><span class="sxs-lookup"><span data-stu-id="c888b-180">Click **Settings**.</span></span>
    2. <span data-ttu-id="c888b-181">选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="c888b-181">Select **Advanced Request**.</span></span>
    3. <span data-ttu-id="c888b-182">输入密码。</span><span class="sxs-lookup"><span data-stu-id="c888b-182">Enter the password.</span></span>
    4. <span data-ttu-id="c888b-183">在**管理设置**，选择**公共区域电话设置**。</span><span class="sxs-lookup"><span data-stu-id="c888b-183">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="c888b-184">启用 **CAP** 和 **CAP 管理模式**。</span><span class="sxs-lookup"><span data-stu-id="c888b-184">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="c888b-185">点击**保存配置**。</span><span class="sxs-lookup"><span data-stu-id="c888b-185">Click **Save Config**.</span></span>

- <span data-ttu-id="c888b-186">现在，电话已准备就绪，你可以在主屏幕上登录。</span><span class="sxs-lookup"><span data-stu-id="c888b-186">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="c888b-187">通过选择**设置** > **功能** > **Skype for Business** 登录。</span><span class="sxs-lookup"><span data-stu-id="c888b-187">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="c888b-188">选择**用户凭证**，然后选择 **Web 登录 (CAP)** 生成一个代码。</span><span class="sxs-lookup"><span data-stu-id="c888b-188">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="c888b-189">转至[设置门户](http://aka.ms/skypecap)，并登录为**管理员**。</span><span class="sxs-lookup"><span data-stu-id="c888b-189">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="c888b-190">输入显示名称（例如，Main Reception）。</span><span class="sxs-lookup"><span data-stu-id="c888b-190">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="c888b-191">如果**仅搜索公共区域电话**被选中，清除该复选框并重新搜索。</span><span class="sxs-lookup"><span data-stu-id="c888b-191">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="c888b-192">在配对代码窗口中，输入电话上显示的代码并单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="c888b-192">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="c888b-193">执行最后一步之后，电话应自动登录。</span><span class="sxs-lookup"><span data-stu-id="c888b-193">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="c888b-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="c888b-194">Related topics</span></span>

- <span data-ttu-id="c888b-195">阅读[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)，详细了解可用电话。</span><span class="sxs-lookup"><span data-stu-id="c888b-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="c888b-196">获取适用于 Skype for Business Online 的电话</span><span class="sxs-lookup"><span data-stu-id="c888b-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


