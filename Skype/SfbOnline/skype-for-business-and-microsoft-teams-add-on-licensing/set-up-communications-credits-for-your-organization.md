---
title: 为您的组织设置通信片尾
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
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
- Strat_SB_PSTN
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 8a60efc9318354b9873c976cf717d3dd2cf73b3d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="53624-103">为您的组织设置通信片尾</span><span class="sxs-lookup"><span data-stu-id="53624-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="53624-104">您将需要设置通信片尾，如果您想要使用 Skype 业务和 Microsoft 团队提供免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="53624-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="53624-105">此外，我们建议您设置通信贷 （国内或国际） 调用计划和音频会议需要拨出**任何目标**的能力的用户。</span><span class="sxs-lookup"><span data-stu-id="53624-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="53624-106">许多国家/地区都包括在内，但有些目标可能不包含在调用计划或音频会议预订。</span><span class="sxs-lookup"><span data-stu-id="53624-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="53624-107">如果不设置通信贷记帐和分派给您的用户的**通信贷**许可证并且运行出组织分钟 （取决于您调用计划或音频会议的计划在您的国家/地区），这些用户将无法进行呼叫或从音频会议的会议拨出。</span><span class="sxs-lookup"><span data-stu-id="53624-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="53624-108">可以获取详细信息，包括建议融资金额，通过读取[通信片尾是什么？](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="53624-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="53624-109">若要找出多少它的成本，[看到这里的速率](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="53624-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="53624-110">步骤 1： 将音频会议和调用规划许可证分配给用户</span><span class="sxs-lookup"><span data-stu-id="53624-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="53624-111">如果您注册，具体取决于您的国家/地区获得一定数量的分钟。</span><span class="sxs-lookup"><span data-stu-id="53624-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="53624-112">您可以看到您将获得搜索的国家/地区或地区 [此处] 的分钟数。(../ country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md））。</span><span class="sxs-lookup"><span data-stu-id="53624-112">You can see the number of minutes you will get search for the country or region [here].(../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)).</span></span> <span data-ttu-id="53624-113">在使用这一时间之后，调用将被断开。</span><span class="sxs-lookup"><span data-stu-id="53624-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="53624-114">若要防止这种情况发生，您需要设置通信贷。</span><span class="sxs-lookup"><span data-stu-id="53624-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="53624-115">为此，请向您的用户**需要将音频会议或电话系统许可分配**。</span><span class="sxs-lookup"><span data-stu-id="53624-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="53624-116">将**音频会议**许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="53624-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="53624-117">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="53624-117">See [Assign Skype for Business and Microsoft Teams licenses](assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    <span data-ttu-id="53624-118">分配此许可证后，您将需要设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="53624-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="53624-119">有关分步说明，请参见[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="53624-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md).</span></span>
    
- <span data-ttu-id="53624-120">将**电话系统**和国内或国内和国际调用规划许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="53624-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="53624-121">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="53624-121">See [Assign Skype for Business and Microsoft Teams licenses](assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53624-122">它具有不需要的通信片尾，虽然仍需要还将分配**计划调用国内**或**国内，并调用计划国际**许可证。</span><span class="sxs-lookup"><span data-stu-id="53624-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="53624-123">分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="53624-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="53624-124">有关分步说明，请参阅[设置调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="53624-124">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="53624-125">有关详细信息，请参阅[附加业务和 Microsoft 小组授权的 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="53624-125">For more information, see [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="53624-126">第 2 步： 为您的组织设置通信片尾</span><span class="sxs-lookup"><span data-stu-id="53624-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="53624-127">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="53624-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="53624-128">在 Office 365 管理中心左侧导航，请转到**收费** > **订阅** > **加载项** > **购买的加载项**，然后选择**通信信用** > **立即购买**。</span><span class="sxs-lookup"><span data-stu-id="53624-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
3. <span data-ttu-id="53624-129">在**通信片尾**订阅页中，填写您的信息，，然后单击**下一步**:</span><span class="sxs-lookup"><span data-stu-id="53624-129">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
  - <span data-ttu-id="53624-130">**添加资金**输入您想要添加到您的帐户的金额。</span><span class="sxs-lookup"><span data-stu-id="53624-130">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="53624-131">如果不启用自动充电的这些资金都用完时，调用启用信用卡通信的能力将会中断 （如入站免费电话服务）。</span><span class="sxs-lookup"><span data-stu-id="53624-131">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="53624-132">为了避免手动补充您的余额达到 0 （零） 每次通信的贷方余额，我们建议您启用自动充电功能。</span><span class="sxs-lookup"><span data-stu-id="53624-132">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
  - <span data-ttu-id="53624-133">**自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。</span><span class="sxs-lookup"><span data-stu-id="53624-133">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
    <span data-ttu-id="53624-134">建议使用**自动充电**设置以避免任何中断服务的通信的贷方余额应达到 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="53624-134">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="53624-135">充电交易成功，充电事务失败 （例如，信用卡已过期），以及通信的贷方余额达到 0 （零） 时，您将会发送一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="53624-135">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
  - <span data-ttu-id="53624-136">**为充电量**您想添加到您的帐户，下面的触发器量到达**重新充电**框中输入的金额。</span><span class="sxs-lookup"><span data-stu-id="53624-136">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
  - <span data-ttu-id="53624-137">**触发器的金额**到*触发器*自动充电，**余额低于时**将使用的框中输入的金额。</span><span class="sxs-lookup"><span data-stu-id="53624-137">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="53624-138">一旦您的余额低于这个数量，将自动将充电量添加到您的帐户。</span><span class="sxs-lookup"><span data-stu-id="53624-138">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
    > <span data-ttu-id="53624-139">基金将仅可用于在 Microsoft 通讯信用发布率使用服务时。</span><span class="sxs-lookup"><span data-stu-id="53624-139">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="53624-140">自购买之日起的 12 个月内未使用的任何资金将过期并丢失。</span><span class="sxs-lookup"><span data-stu-id="53624-140">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
4. <span data-ttu-id="53624-141">输入您的付款信息并单击**下订单**。</span><span class="sxs-lookup"><span data-stu-id="53624-141">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="53624-142">如果您不是批量许可证客户，您可以选择您企业协议编号的付款。</span><span class="sxs-lookup"><span data-stu-id="53624-142">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="53624-143">如果您有多个企业协议号，您将能够选择您想要使用的付款的哪些企业协议。</span><span class="sxs-lookup"><span data-stu-id="53624-143">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="53624-144">您会有机会指定采购订单编号相关联的企业协议编号 （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="53624-144">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="53624-145">每个组织必须调用计划卷和费率，要考虑的不同用法。</span><span class="sxs-lookup"><span data-stu-id="53624-145">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="53624-146">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="53624-146">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="53624-147">公司已经在使用 Skype 在线业务已为其服务提供商可以通过它查看**业务管理中心的 Skype**在获得使用率数据 > **报告** > **PSTN 用法详细信息**报告。</span><span class="sxs-lookup"><span data-stu-id="53624-147">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="53624-148">设置通信片尾，需要调查的您的组织可以确定您将需要将放入的金额的调用使用。</span><span class="sxs-lookup"><span data-stu-id="53624-148">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="53624-149">你可以通过查看" **PSTN 使用详细信息**"报告获取呼叫使用信息。</span><span class="sxs-lookup"><span data-stu-id="53624-149">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="53624-150">此报表中，可以将呼叫数据记录导出到 Excel 中，如果您想要导出的数据存储或创建自定义报表。</span><span class="sxs-lookup"><span data-stu-id="53624-150">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="53624-151">若要查看使用情况，请参阅[Skype 业务 PSTN 使用情况报告](../skype-for-business-online-reporting/pstn-usage-report.md)</span><span class="sxs-lookup"><span data-stu-id="53624-151">To see usage, see [Skype for Business PSTN usage report](../skype-for-business-online-reporting/pstn-usage-report.md)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="53624-152">步骤 3： 将通信片尾许可证分配给用户</span><span class="sxs-lookup"><span data-stu-id="53624-152">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="53624-153">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="53624-153">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="53624-154">在 Office 365 管理中心左侧导航，请转到**用户** > **活动用户**，然后从列表中选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="53624-154">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="53624-155">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="53624-155">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="53624-156">在**产品许可证**页面切换 * * 通信片尾 * * 到**上**指定此许可证，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="53624-156">On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53624-157">即使有**企业 E5**许可证分配的用户，但仍建议您这样做。</span><span class="sxs-lookup"><span data-stu-id="53624-157">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="53624-158">想要了解计划和定价？</span><span class="sxs-lookup"><span data-stu-id="53624-158">Want to know about plans and pricing?</span></span>

<span data-ttu-id="53624-159">您可以看到的计划和价格通过访问以下链接之一：</span><span class="sxs-lookup"><span data-stu-id="53624-159">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="53624-160">通话方案</span><span class="sxs-lookup"><span data-stu-id="53624-160">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="53624-161">音频会议计划</span><span class="sxs-lookup"><span data-stu-id="53624-161">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="53624-162">电话系统计划</span><span class="sxs-lookup"><span data-stu-id="53624-162">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="53624-163">您还可以通过[登录到 Office 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)查看信息并转到**收费** > **订阅** > **添加订阅**。</span><span class="sxs-lookup"><span data-stu-id="53624-163">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="53624-164">执照或许可证所需的每个功能的表，请参阅[附加业务和 Microsoft 小组授权的 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="53624-164">To see a table with the license or licenses you will need for each feature, see [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="53624-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="53624-165">Related topics</span></span>

- [<span data-ttu-id="53624-166">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="53624-166">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="53624-167">设置电话系统语音邮件 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="53624-167">Set up Phone System voicemail - Admin help</span></span>](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="53624-168">[设置调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)和[Office 365 调用计划](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="53624-168">[Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="53624-169">存入资金和管理通信点数</span><span class="sxs-lookup"><span data-stu-id="53624-169">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
- <span data-ttu-id="53624-170">[将云连接器配置](https://technet.microsoft.com/en-us/library/mt605228.aspx)并[下载云连接器](https://aka.ms/CloudConnectorInstaller)</span><span class="sxs-lookup"><span data-stu-id="53624-170">[Configure the Cloud Connector](https://technet.microsoft.com/en-us/library/mt605228.aspx) and [Download the Cloud Connector](https://aka.ms/CloudConnectorInstaller)</span></span>

  
 