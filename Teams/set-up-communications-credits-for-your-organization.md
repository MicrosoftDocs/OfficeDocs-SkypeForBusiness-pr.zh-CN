---
title: 为组织设置通信点数
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: d97c95ed3fd4d398a4422645ab1e1491e1df6e3c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375234"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="f700f-103">为组织设置通信点数</span><span class="sxs-lookup"><span data-stu-id="f700f-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="f700f-104">您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="f700f-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="f700f-105">此外，我们建议您设置 Communications 字幕式调用计划 （国内或国际） 和音频会议用户需要拨出**任何目标**的能力。</span><span class="sxs-lookup"><span data-stu-id="f700f-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="f700f-106">多个国家/地区内包括在内，但某些目标不能包含在您调用规划或音频会议的订阅。</span><span class="sxs-lookup"><span data-stu-id="f700f-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="f700f-107">如果您不会设置 Communications 字幕式帐单且将**Communications 字幕式**许可证分配给用户，并且您运行出分钟，以便您的组织 （具体取决于您调用计划或音频会议中计划国家/地区），这些用户将无法发起呼叫或从音频会议拨出。</span><span class="sxs-lookup"><span data-stu-id="f700f-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="f700f-108">您可以获取详细信息，请通过读取资金数量，包括建议[Communications 字幕式是什么？](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="f700f-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="f700f-109">若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。</span><span class="sxs-lookup"><span data-stu-id="f700f-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="f700f-110">步骤 1： 向用户分配音频会议和调用规划许可证</span><span class="sxs-lookup"><span data-stu-id="f700f-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="f700f-111">当您注册时，您将获取一定数量的分钟，具体取决于您的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="f700f-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="f700f-112">您可以看到您将收到搜索的国家或地区的分钟数[此处](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="f700f-112">You can see the number of minutes you will get search for the country or region [here](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> <span data-ttu-id="f700f-113">使用这些分钟后，呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="f700f-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="f700f-114">若要防止这种情况，您需要设置 Communications 字幕式。</span><span class="sxs-lookup"><span data-stu-id="f700f-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="f700f-115">这样，**您需要为音频会议或电话系统许可证分配**用户。</span><span class="sxs-lookup"><span data-stu-id="f700f-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="f700f-116">将**音频会议**许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f700f-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="f700f-117">请参阅[业务和 Microsoft 团队许可证分配 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f700f-117">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>
    
    <span data-ttu-id="f700f-118">指定此许可证后，您需要设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="f700f-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="f700f-119">有关分步说明，请参阅[尝试或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="f700f-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365).</span></span>
    
- <span data-ttu-id="f700f-120">将**电话系统**和国内或国内和国际呼叫规划许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f700f-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="f700f-121">请参阅[业务和 Microsoft 团队许可证分配 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f700f-121">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f700f-122">尽管不需要的通信字幕式，则仍需还分配**国内调用规划**或**国内和国际呼叫规划**许可证。</span><span class="sxs-lookup"><span data-stu-id="f700f-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="f700f-123">分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="f700f-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="f700f-124">有关分步说明，请参阅[Set up 调用计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="f700f-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="f700f-125">有关详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="f700f-125">For more information, see [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="f700f-126">步骤 2： 为您的组织的通信字幕式设置</span><span class="sxs-lookup"><span data-stu-id="f700f-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="f700f-127">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f700f-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f700f-128">在 Office 365 管理中心的左侧导航窗格中，转到**帐单** > **订阅** > **添加订阅**。</span><span class="sxs-lookup"><span data-stu-id="f700f-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>

3. <span data-ttu-id="f700f-129">展开**加载项订阅**，然后选择**Communications 字幕式** > **立即购买**。</span><span class="sxs-lookup"><span data-stu-id="f700f-129">Expand **Add-on subscriptions**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
4. <span data-ttu-id="f700f-130">在**Communications 字幕式**订阅页中，填写您的信息，然后单击**下一步**:</span><span class="sxs-lookup"><span data-stu-id="f700f-130">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="f700f-131">**添加资金**输入要添加到您的帐户的金额。</span><span class="sxs-lookup"><span data-stu-id="f700f-131">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="f700f-132">如果您不启用自动充电，都用完这些资金，调用使用 Communications 字幕式启用的功能将会中断 （如入站免费电话服务）。</span><span class="sxs-lookup"><span data-stu-id="f700f-132">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="f700f-133">若要避免无需手动补充 Communications 字幕式平衡每次您平衡达到 0 （零），我们建议您启用自动充电功能。</span><span class="sxs-lookup"><span data-stu-id="f700f-133">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="f700f-134">**自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。</span><span class="sxs-lookup"><span data-stu-id="f700f-134">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="f700f-135">建议使用**自动充电**设置以避免服务的任何中断应 Communications 字幕式平衡达到 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="f700f-135">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="f700f-136">充电事务成功，充电事务失败 （如信用卡过期），以及 Communications 字幕式平衡达到 0 （零） 时，您将会发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f700f-136">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="f700f-137">**为充电量**在要添加到您的帐户下, 触发量到达的**为充电与**框中输入的金额。</span><span class="sxs-lookup"><span data-stu-id="f700f-137">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="f700f-138">**触发量**向*触发器*自动充电**平衡低于时**将使用的框中输入的金额。</span><span class="sxs-lookup"><span data-stu-id="f700f-138">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="f700f-139">一旦您平衡低于这个值，将自动将充电量添加到您的帐户。</span><span class="sxs-lookup"><span data-stu-id="f700f-139">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="f700f-140">资金将仅可用于使用服务时，microsoft Communications 字幕式发布率。</span><span class="sxs-lookup"><span data-stu-id="f700f-140">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="f700f-141">自购买之日起的 12 个月内未使用的任何资金将过期并丢失。</span><span class="sxs-lookup"><span data-stu-id="f700f-141">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
5. <span data-ttu-id="f700f-142">输入您的付款信息并单击 **下订单** 。</span><span class="sxs-lookup"><span data-stu-id="f700f-142">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="f700f-143">如果您是批量授权客户，则可以选择您的企业协议编号进行付款。</span><span class="sxs-lookup"><span data-stu-id="f700f-143">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="f700f-144">如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。</span><span class="sxs-lookup"><span data-stu-id="f700f-144">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="f700f-145">您还将获得一个机会，指定要与企业协议编号关联的采购订单编号 （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="f700f-145">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="f700f-146">每个组织会调用规划卷和要考虑的其他用法。</span><span class="sxs-lookup"><span data-stu-id="f700f-146">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="f700f-147">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="f700f-147">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="f700f-148">已使用 Skype 业务 online 已作为其服务提供商的组织可以通过查看在**业务管理中心的 Skype**获取使用率数据 > **报告** > **PSTN 用法详细信息**报告。</span><span class="sxs-lookup"><span data-stu-id="f700f-148">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="f700f-149">设置 Communications 字幕式时，需要调查呼叫使用为您的组织，以确定您将需要置于的金额。</span><span class="sxs-lookup"><span data-stu-id="f700f-149">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="f700f-150">你可以通过查看" **PSTN 使用详细信息**"报告获取呼叫使用信息。</span><span class="sxs-lookup"><span data-stu-id="f700f-150">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="f700f-151">此报告可以将呼叫数据记录导出到 Excel 中，如果您想要导出的数据存储或创建自定义报告。</span><span class="sxs-lookup"><span data-stu-id="f700f-151">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="f700f-152">若要查看用法，请参阅[Skype 的业务 PSTN 使用率报告](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="f700f-152">To see usage, see [Skype for Business PSTN usage report](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="f700f-153">步骤 3： 将 Communications 字幕式许可证分配给用户</span><span class="sxs-lookup"><span data-stu-id="f700f-153">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="f700f-154">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f700f-154">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f700f-155">在 Office 365 管理中心的左侧导航窗格中，转到**用户** > **活动用户**，然后从列表中选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="f700f-155">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="f700f-156">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f700f-156">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="f700f-157">在**产品许可证**页上，切换到**在上**分配此许可证， **Communications 字幕式**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f700f-157">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f700f-158">即使已经分配一个**企业 E5**许可证的用户，仍建议您这样做。</span><span class="sxs-lookup"><span data-stu-id="f700f-158">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="f700f-159">想要了解计划和定价？</span><span class="sxs-lookup"><span data-stu-id="f700f-159">Want to know about plans and pricing?</span></span>

<span data-ttu-id="f700f-160">您可以看到计划和定价通过访问以下链接之一：</span><span class="sxs-lookup"><span data-stu-id="f700f-160">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="f700f-161">通话套餐</span><span class="sxs-lookup"><span data-stu-id="f700f-161">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="f700f-162">音频会议计划</span><span class="sxs-lookup"><span data-stu-id="f700f-162">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="f700f-163">电话系统计划</span><span class="sxs-lookup"><span data-stu-id="f700f-163">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="f700f-164">您还可以参见信息通过[登录到 Office 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)，转到**帐单** > **订阅** > **添加订阅**。</span><span class="sxs-lookup"><span data-stu-id="f700f-164">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="f700f-165">若要查看使用许可证或许可证需要为每个功能的表，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="f700f-165">To see a table with the license or licenses you will need for each feature, see [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f700f-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="f700f-166">Related topics</span></span>

- [<span data-ttu-id="f700f-167">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f700f-167">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="f700f-168">设置电话系统语音邮件 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="f700f-168">Set up Phone System voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="f700f-169">[设置通话套餐](set-up-calling-plans.md) 和 [Office 365 的通话套餐](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f700f-169">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="f700f-170">存入资金和管理通信点数</span><span class="sxs-lookup"><span data-stu-id="f700f-170">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
- <span data-ttu-id="f700f-171">[配置云连接器](https://technet.microsoft.com/library/mt605228.aspx)和[下载云连接器](https://aka.ms/CloudConnectorInstaller)</span><span class="sxs-lookup"><span data-stu-id="f700f-171">[Configure the Cloud Connector](https://technet.microsoft.com/library/mt605228.aspx) and [Download the Cloud Connector](https://aka.ms/CloudConnectorInstaller)</span></span>

  
 