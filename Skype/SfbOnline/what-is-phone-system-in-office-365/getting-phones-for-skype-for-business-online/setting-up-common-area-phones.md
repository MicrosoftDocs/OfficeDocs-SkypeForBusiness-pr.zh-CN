---
title: 设置公用区域电话
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
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="099c4-103">设置公用区域电话</span><span class="sxs-lookup"><span data-stu-id="099c4-103">Set up common area phones</span></span>
<span data-ttu-id="099c4-104">公用区域电话 （帽） 通常位于类似会议厅区域或可供很多人的另一个区域。</span><span class="sxs-lookup"><span data-stu-id="099c4-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="099c4-105">例如，接收区域电话，门电话或会议室电话，大写设置为设备，而不是用户和自动登录到网络。</span><span class="sxs-lookup"><span data-stu-id="099c4-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="099c4-106">下面的步骤中，我们将帮助您与调用计划的电话系统，以便您可以为您的组织中部署这些类型的电话的帐户设置。</span><span class="sxs-lookup"><span data-stu-id="099c4-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="099c4-107">公用区域电话的先决条件</span><span class="sxs-lookup"><span data-stu-id="099c4-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="099c4-108">首先需要执行的是以确认您具有以下：</span><span class="sxs-lookup"><span data-stu-id="099c4-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="099c4-109">购买公共区域电话的许可证和调用规划。</span><span class="sxs-lookup"><span data-stu-id="099c4-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="099c4-110">搜索和购买已批准的电话 (查看列表[此处](deploying-skype-for-business-online-phones.md))。</span><span class="sxs-lookup"><span data-stu-id="099c4-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="099c4-111">更新电话上的固件 （请参阅支持固件[本主题中](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="099c4-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="099c4-112">您可以通过执行此操作来检查您的电话上的固件：</span><span class="sxs-lookup"><span data-stu-id="099c4-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="099c4-113">**Polycom VVX 电话**： 转到**设置** > **状态** > **平台** > **应用程序** > **主**。</span><span class="sxs-lookup"><span data-stu-id="099c4-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="099c4-114">**Yealink 电话**： 主要电话屏幕上转到**状态**。</span><span class="sxs-lookup"><span data-stu-id="099c4-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="099c4-115">**AudioCodes 电话**： 转到**菜单** > **设备状态** > 从开始屏幕的**固件版本**。</span><span class="sxs-lookup"><span data-stu-id="099c4-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="099c4-116">**Lync Phone Edition (LPE) 电话**： 转到**菜单** > **系统信息**开始屏幕。</span><span class="sxs-lookup"><span data-stu-id="099c4-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="099c4-117">固件更新由 Skype for Business 服务管理。</span><span class="sxs-lookup"><span data-stu-id="099c4-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="099c4-118">每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。</span><span class="sxs-lookup"><span data-stu-id="099c4-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="099c4-119">根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。</span><span class="sxs-lookup"><span data-stu-id="099c4-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="099c4-120">您可以通过使用[Set CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet 并将*EnableDeviceUpdate*参数设置为禁用设备更新设置`false`。</span><span class="sxs-lookup"><span data-stu-id="099c4-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="099c4-121">设置公用区域电话</span><span class="sxs-lookup"><span data-stu-id="099c4-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="099c4-122">您将需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="099c4-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="099c4-123">设置您的电话的用户帐户</span><span class="sxs-lookup"><span data-stu-id="099c4-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="099c4-124">步骤 1-购买许可证</span><span class="sxs-lookup"><span data-stu-id="099c4-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="099c4-125">在 Office 365 管理中心，转到**帐单** > **购买服务**，并将其添加**其他计划**。</span><span class="sxs-lookup"><span data-stu-id="099c4-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![盖 license.png](../../images/cap-license.png)
2. <span data-ttu-id="099c4-127">**公用区域电话**上单击 > **立即购买**> 上**立即购买****签出**页上单击。</span><span class="sxs-lookup"><span data-stu-id="099c4-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="099c4-128">单击以展开**加载项订阅**，然后单击上若要购买调用规划。</span><span class="sxs-lookup"><span data-stu-id="099c4-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="099c4-129">选择**国内调用计划**或**规划国内和国际呼叫**。</span><span class="sxs-lookup"><span data-stu-id="099c4-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="099c4-130">您无需电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="099c4-130">You don't need a Phone System license.</span></span> <span data-ttu-id="099c4-131">它包含使用**公用区域电话**的许可证。</span><span class="sxs-lookup"><span data-stu-id="099c4-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="099c4-132">许可证的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="099c4-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="099c4-133">步骤 2-创建新的用户帐户的电话和分配许可证</span><span class="sxs-lookup"><span data-stu-id="099c4-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="099c4-134">在 Office 365 管理中心，转到**用户** > **活动用户** > **添加用户**。</span><span class="sxs-lookup"><span data-stu-id="099c4-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="099c4-135">放入**用户名**类似"Main"的第一个名称和"接收"的第二个名称。</span><span class="sxs-lookup"><span data-stu-id="099c4-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="099c4-136">如果不是，则自动生成类似"Main 接收"将其放在一个**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="099c4-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="099c4-137">放入类似"MainReception"或"Mainlobby"**用户名**。</span><span class="sxs-lookup"><span data-stu-id="099c4-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="099c4-138">为公用区域电话，您可能需要手动设置密码或您的公用区域电话的所有有相同的密码。</span><span class="sxs-lookup"><span data-stu-id="099c4-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="099c4-139">此外，您可能会认为取消选择**进行此更改其密码它们首次登录时的用户**信息。</span><span class="sxs-lookup"><span data-stu-id="099c4-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="099c4-140">等待 ！</span><span class="sxs-lookup"><span data-stu-id="099c4-140">WAIT!!</span></span> <span data-ttu-id="099c4-141">不要单击**添加**！</span><span class="sxs-lookup"><span data-stu-id="099c4-141">Don't click **Add**!!</span></span> <span data-ttu-id="099c4-142">嗯，如果未单击**添加**执行这： Office 365 管理中心 >**用户** > **活动用户**，然后查找用户。</span><span class="sxs-lookup"><span data-stu-id="099c4-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="099c4-143">然后在用户的属性页上，单击**产品许可证**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="099c4-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="099c4-144">在**产品许可证**页上，打开**公用区域电话**和选取是**国内调用规划**或国内和**国际呼叫规划**。</span><span class="sxs-lookup"><span data-stu-id="099c4-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="099c4-145">如果仍然存在，则将许可证分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="099c4-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="099c4-146">在同一页上，单击以展开**产品许可证**。</span><span class="sxs-lookup"><span data-stu-id="099c4-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="099c4-147">启用以下：</span><span class="sxs-lookup"><span data-stu-id="099c4-147">Turn on the following:</span></span>
    - <span data-ttu-id="099c4-148">公用区域电话</span><span class="sxs-lookup"><span data-stu-id="099c4-148">Common Area Phone</span></span>
    - <span data-ttu-id="099c4-149">然后，您需要选择是**国内调用规划**或国内和**国际呼叫规划**。</span><span class="sxs-lookup"><span data-stu-id="099c4-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="099c4-150">分配许可证将显示如下：</span><span class="sxs-lookup"><span data-stu-id="099c4-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="099c4-152">只要您知道，业务计划 2 的 Skype 随**公用区域电话**的许可证。</span><span class="sxs-lookup"><span data-stu-id="099c4-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="099c4-153">有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="099c4-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="099c4-154">步骤 3-向用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="099c4-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="099c4-155">![sfb-徽标-30x30.png](../../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="099c4-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="099c4-156">在 Office 365 管理中心 >**管理中心** > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="099c4-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="099c4-157">在**业务管理中心的 Skype** >  **语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="099c4-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="099c4-158">从的电话号码列表中选择一个号码，然后单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="099c4-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="099c4-159">在**分配**页上，在**语音用户**框中输入用于电话然后选择下拉列表中**选择一个语音用户**的用户的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="099c4-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="099c4-160">您有时将需要添加紧急地址。</span><span class="sxs-lookup"><span data-stu-id="099c4-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="099c4-161">一旦您搜索，查找下**选择紧急地址**选取适合您。</span><span class="sxs-lookup"><span data-stu-id="099c4-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="099c4-162">单击**保存**和您的用户应如下所示：</span><span class="sxs-lookup"><span data-stu-id="099c4-162">Click **Save** and your user should look like this:</span></span>

    ![盖-用户 number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="099c4-164">用户将仅显示它们是否能应用的**电话系统**许可。</span><span class="sxs-lookup"><span data-stu-id="099c4-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="099c4-165">如果您刚这，然后有时计有点显示在列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="099c4-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="099c4-166">更多的东西，请参阅[为用户获取电话号码](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="099c4-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="099c4-167">如果您想知道，您还可使您的电话号码与另一个运营商和"*端口*"或其转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="099c4-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="099c4-168">请参阅[传输到 Office 365 的电话号码](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="099c4-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="099c4-169">步骤 4-设置您的电话</span><span class="sxs-lookup"><span data-stu-id="099c4-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="099c4-170">**在电话上设置模式**</span><span class="sxs-lookup"><span data-stu-id="099c4-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="099c4-171">电话或电话必须必须打开公用区域电话模式。</span><span class="sxs-lookup"><span data-stu-id="099c4-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="099c4-172">您可能想要检查的以确保这些操作。</span><span class="sxs-lookup"><span data-stu-id="099c4-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="099c4-173">**下面是一个有关如何设置 Polycom VVX 电话示例**</span><span class="sxs-lookup"><span data-stu-id="099c4-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="099c4-174">通过执行以下步骤为 Polycom VVX 启用公用区域电话模式：</span><span class="sxs-lookup"><span data-stu-id="099c4-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="099c4-175">在浏览器中，连接到的 web 接口，以便您可以启用帽模式。</span><span class="sxs-lookup"><span data-stu-id="099c4-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="099c4-176">然后转至**设置****业务设置 Skype**选项中，选择**公用区域电话**。</span><span class="sxs-lookup"><span data-stu-id="099c4-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="099c4-177">单击**是**以保存您的设置。</span><span class="sxs-lookup"><span data-stu-id="099c4-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="099c4-178">既然帽模式已启用，则设置使用电话的显示电话。</span><span class="sxs-lookup"><span data-stu-id="099c4-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="099c4-179">显示应显示**CaAP 已启用**。</span><span class="sxs-lookup"><span data-stu-id="099c4-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="099c4-180">然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="099c4-180">Then do the following:</span></span>

    1. <span data-ttu-id="099c4-181">单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="099c4-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="099c4-182">选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="099c4-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="099c4-183">输入密码。</span><span class="sxs-lookup"><span data-stu-id="099c4-183">Enter the password.</span></span>
    4. <span data-ttu-id="099c4-184">在**管理设置**中，选择**公共区域电话设置**。</span><span class="sxs-lookup"><span data-stu-id="099c4-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="099c4-185">启用**上限**和**帽管理员模式**。</span><span class="sxs-lookup"><span data-stu-id="099c4-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="099c4-186">单击**保存配置**。</span><span class="sxs-lookup"><span data-stu-id="099c4-186">Click **Save Config**.</span></span>

- <span data-ttu-id="099c4-187">确定，现在您的电话已准备以便您可以在主屏幕上登录。</span><span class="sxs-lookup"><span data-stu-id="099c4-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="099c4-188">通过选择**设置**登录 > **功能** > **for Business 的 Skype。**</span><span class="sxs-lookup"><span data-stu-id="099c4-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="099c4-189">选择**用户凭据**，然后选择**web 登录助手 （帽）** 生成代码。</span><span class="sxs-lookup"><span data-stu-id="099c4-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="099c4-190">转到[设置门户](http://aka.ms/skypecap)，并以**管理员**身份登录。</span><span class="sxs-lookup"><span data-stu-id="099c4-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="099c4-191">输入显示名称 （例如，Main 接收）。</span><span class="sxs-lookup"><span data-stu-id="099c4-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="099c4-192">如果选中**为公用区域电话的搜索**，则清除该复选框，并再次进行搜索。</span><span class="sxs-lookup"><span data-stu-id="099c4-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="099c4-193">在配对的代码窗口中，输入电话上显示的代码，并单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="099c4-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="099c4-194">以下此最后一步，电话应自动登录。</span><span class="sxs-lookup"><span data-stu-id="099c4-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="099c4-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="099c4-195">Related topics</span></span>

- <span data-ttu-id="099c4-196">了解有关在[部署的 Skype Online 业务电话的](deploying-skype-for-business-online-phones.md)可用电话。</span><span class="sxs-lookup"><span data-stu-id="099c4-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="099c4-197">获取适用于 Skype for Business Online 的电话</span><span class="sxs-lookup"><span data-stu-id="099c4-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


