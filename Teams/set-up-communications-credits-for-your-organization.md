---
title: 设置组织的通信点数
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117100"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="83372-103">设置组织的通信点数</span><span class="sxs-lookup"><span data-stu-id="83372-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="83372-104">您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="83372-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="83372-105">此外，我们建议你为需要拨出到任何目的地的呼叫计划 (或国际) 和音频会议用户设置通信 **积分**。</span><span class="sxs-lookup"><span data-stu-id="83372-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="83372-106">包括许多国家/地区，但某些目的地可能不包含在呼叫计划或音频会议订阅中。</span><span class="sxs-lookup"><span data-stu-id="83372-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="83372-107">如果未设置通信信用额度计费并将通信信用额度许可证分配给用户，并且你的组织 (根据你的呼叫计划或音频会议计划在你的国家/地区) 中用完了分钟数，则这些用户将无法进行呼叫或从音频会议会议拨出。</span><span class="sxs-lookup"><span data-stu-id="83372-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="83372-108">可以通过阅读什么是通信信用额度，获取更多信息，包括建议 [的金额？](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="83372-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="83372-109">若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。</span><span class="sxs-lookup"><span data-stu-id="83372-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="83372-110">步骤 1：为用户分配音频会议或通话计划许可证</span><span class="sxs-lookup"><span data-stu-id="83372-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="83372-111">注册时，你获得特定分钟数，具体取决于你的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="83372-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="83372-112">您可以在"音频会议"和"呼叫计划"[](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)的"国家/地区可用性"列表中搜索您的国家/地区，以查看您将获得的分钟数。</span><span class="sxs-lookup"><span data-stu-id="83372-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="83372-113">使用这些分钟数后，通话将断开连接。</span><span class="sxs-lookup"><span data-stu-id="83372-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="83372-114">若要防止这种情况发生，需要设置通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="83372-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="83372-115">为此， **你需要为用户分配音频会议或电话** 系统许可证。</span><span class="sxs-lookup"><span data-stu-id="83372-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="83372-116">为 **用户分配** 音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="83372-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="83372-117">请参阅 [分配 Microsoft Teams 附加许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="83372-117">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    <span data-ttu-id="83372-118">分配此许可证后，需要设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="83372-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="83372-119">有关分步说明，请参阅在 [Microsoft 365 或 Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)中试用或购买音频会议。</span><span class="sxs-lookup"><span data-stu-id="83372-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="83372-120">为 **用户分配** 电话 **系统以及** 国内或国内和国际呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="83372-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="83372-121">请参阅 [分配 Microsoft Teams 附加许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="83372-121">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83372-122">虽然通信积分不需要，但您仍然需要分配国内呼叫计划或 **国内和国际呼叫计划** 许可证。 </span><span class="sxs-lookup"><span data-stu-id="83372-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="83372-123">分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="83372-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="83372-124">有关分步说明，请参阅 [设置呼叫计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="83372-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="83372-125">有关详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="83372-125">For more information, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="83372-126">步骤 2：为组织设置通信信用额度</span><span class="sxs-lookup"><span data-stu-id="83372-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="83372-127">使用工作或学校 [帐户登录到 Microsoft 365](https://portal.office.com/Adminportal) 管理中心。</span><span class="sxs-lookup"><span data-stu-id="83372-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="83372-128">在 Microsoft 365 管理中心的左侧导航中，转到"**计费**  >  **购买服务"。**</span><span class="sxs-lookup"><span data-stu-id="83372-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="83372-129">向下滚动并选择"**附加内容"。**</span><span class="sxs-lookup"><span data-stu-id="83372-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="83372-130">选择 **"通信信用额度"。**</span><span class="sxs-lookup"><span data-stu-id="83372-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="83372-131">在"**通信信用额度"** 订阅页上，填写你的信息，然后单击"下一步 **"：**</span><span class="sxs-lookup"><span data-stu-id="83372-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="83372-132">**添加资金** 输入要添加到帐户的金额。</span><span class="sxs-lookup"><span data-stu-id="83372-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="83372-133">如果未启用自动充值，这些资金耗尽后，使用通信信用额度启用的呼叫功能将中断 (如入站免费服务) 。</span><span class="sxs-lookup"><span data-stu-id="83372-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="83372-134">为了避免每次余额达到 0 或零 (，) 手动补充通信信用额度余额，我们建议您启用自动充值功能。</span><span class="sxs-lookup"><span data-stu-id="83372-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="83372-135">**自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。</span><span class="sxs-lookup"><span data-stu-id="83372-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="83372-136">建议你使用自动充值设置，以免在通信信用额度余额达到 0 或零时 (中断) 。</span><span class="sxs-lookup"><span data-stu-id="83372-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="83372-137">当充值交易成功、充值交易失败（例如 (信用卡) ）以及通信积分余额达到 0 (零时) 。</span><span class="sxs-lookup"><span data-stu-id="83372-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="83372-138">**充值金额** 在"充值金额 **"** 框中输入在达到以下触发金额后要添加到帐户的金额。</span><span class="sxs-lookup"><span data-stu-id="83372-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="83372-139">**触发量** 在将用于"**触发**"自动充值的"余额低于"框中输入金额。 </span><span class="sxs-lookup"><span data-stu-id="83372-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="83372-140">余额低于此金额后，充值金额将自动添加到你的帐户。</span><span class="sxs-lookup"><span data-stu-id="83372-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="83372-141">使用服务时，资金将仅应用于 Microsoft 发布的通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="83372-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="83372-142">自购买之日起的 12 个月内未使用的任何资金将过期并丢失。</span><span class="sxs-lookup"><span data-stu-id="83372-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="83372-143">只有在已使用已分配资金时，才应用通信积分的每月计费，若要了解如何检查每月使用情况，请阅读 Skype for Business [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="83372-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="83372-144">输入您的付款信息并单击 **下订单** 。</span><span class="sxs-lookup"><span data-stu-id="83372-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="83372-145">如果您是批量授权客户，则可以选择您的企业协议编号进行付款。</span><span class="sxs-lookup"><span data-stu-id="83372-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="83372-146">如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。</span><span class="sxs-lookup"><span data-stu-id="83372-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="83372-147">您还将获得一个机会，指定要与企业协议编号关联的采购订单编号 （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="83372-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="83372-148">每个组织都会考虑不同的呼叫计划数量和费率使用情况。</span><span class="sxs-lookup"><span data-stu-id="83372-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="83372-149">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="83372-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="83372-150">已使用 Skype for Business Online 作为服务提供商的组织可以通过在 **Microsoft Teams** 管理中心报告 PSTN 使用情况详细信息报告中查看这些数据  >    >  **，获取使用情况** 数据。</span><span class="sxs-lookup"><span data-stu-id="83372-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="83372-151">设置通信信用额度时，需要调查组织的呼叫使用情况，以确定所需的金额。</span><span class="sxs-lookup"><span data-stu-id="83372-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="83372-152">你可以通过查看" **PSTN 使用详细信息**"报告获取呼叫使用信息。</span><span class="sxs-lookup"><span data-stu-id="83372-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="83372-153">如果需要存储数据或创建自定义报表，此报表允许您将呼叫数据记录导出到 Excel。</span><span class="sxs-lookup"><span data-stu-id="83372-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="83372-154">若要了解如何查看使用情况，请阅读 [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。</span><span class="sxs-lookup"><span data-stu-id="83372-154">To learn how to see usage, read [PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="83372-155">步骤 3：向用户分配通信信用额度许可证</span><span class="sxs-lookup"><span data-stu-id="83372-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="83372-156">使用工作或学校 [帐户登录到 Microsoft 365](https://portal.office.com/Adminportal) 管理中心。</span><span class="sxs-lookup"><span data-stu-id="83372-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="83372-157">在 Microsoft 365 管理中心的左侧导航中，转到"用户  >  **""活动** 用户"，然后从列表中选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="83372-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="83372-158">选择 **"许可证和应用"。**</span><span class="sxs-lookup"><span data-stu-id="83372-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="83372-159">将 **"通信信用额度"** 切换 **为"打开**"以分配此许可证，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="83372-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83372-160">即使为用户分配了企业 **版 E5** 许可证，也仍建议你这样做。</span><span class="sxs-lookup"><span data-stu-id="83372-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="83372-161">可以使用 [Powershell 通过](/powershell/module/skype/?view=skype-ps) 一个命令将许可证和应用分配给多个用户。</span><span class="sxs-lookup"><span data-stu-id="83372-161">You can use [Powershell](/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="83372-162">想要了解计划和定价？</span><span class="sxs-lookup"><span data-stu-id="83372-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="83372-163">可以通过访问以下链接之一来查看计划和定价：</span><span class="sxs-lookup"><span data-stu-id="83372-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="83372-164">通话套餐</span><span class="sxs-lookup"><span data-stu-id="83372-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="83372-165">音频会议计划</span><span class="sxs-lookup"><span data-stu-id="83372-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="83372-166">电话系统计划</span><span class="sxs-lookup"><span data-stu-id="83372-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="83372-167">还可通过登录 Microsoft [365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)管理中心并访问"计费订阅""添加订阅"  >    >  **来查看信息**。</span><span class="sxs-lookup"><span data-stu-id="83372-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="83372-168">若要查看包含每个功能所需的许可证的表，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="83372-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="83372-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="83372-169">Related topics</span></span>

- [<span data-ttu-id="83372-170">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="83372-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="83372-171">设置云语音邮件 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="83372-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="83372-172">[为](set-up-calling-plans.md) [Microsoft 365 或 Office 365](calling-plans-for-office-365.md)设置呼叫计划和呼叫计划</span><span class="sxs-lookup"><span data-stu-id="83372-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="83372-173">添加资金并管理通信点数</span><span class="sxs-lookup"><span data-stu-id="83372-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
