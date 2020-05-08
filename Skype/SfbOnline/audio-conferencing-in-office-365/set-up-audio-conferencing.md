---
title: 为 Skype for business 设置音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '了解如何为业务中需要使用电话加入电话会议的人员设置拨号或音频会议。 '
ms.openlocfilehash: bfd9c9ec31736b0f7fc16f15a907c87406113871
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163941"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="d7164-103">为 Skype for business 设置音频会议</span><span class="sxs-lookup"><span data-stu-id="d7164-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="d7164-p101">您的组织中的人员有时需要使用电话拨入会议。Skype for business 仅为这种情况提供音频会议功能！用户可以使用手机与 Skype for business 会议通话，而不是在移动设备或电脑上使用 Skype for business 应用。</span><span class="sxs-lookup"><span data-stu-id="d7164-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business includes the audio conferencing feature for just this situation! People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="d7164-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="d7164-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="d7164-109">有关音频会议的常见问题，请参阅 [音频会议的常见问题](/MicrosoftTeams/audio-conferencing-common-questions) 。</span><span class="sxs-lookup"><span data-stu-id="d7164-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="d7164-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="d7164-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="d7164-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d7164-111"><a name="__top"> </a></span></span>

<span data-ttu-id="d7164-112">转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="d7164-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="d7164-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="d7164-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="d7164-p103">对于音频会议，需要将设置拨入式会议的每个用户都拥有一个许可证。若要了解需要购买哪些许可证才能购买音频会议和费用，请参阅[Skype for business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d7164-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="d7164-116">Office 365 企业版 E5 许可证中包含音频会议，并用作加载项。</span><span class="sxs-lookup"><span data-stu-id="d7164-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="d7164-117">购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。</span><span class="sxs-lookup"><span data-stu-id="d7164-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="d7164-118">请参阅为您购买的适用于您的组织中要安排或领导会议的人员[分配或删除适用于企业的 Microsoft 365 应用的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="d7164-118">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="d7164-119">我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。</span><span class="sxs-lookup"><span data-stu-id="d7164-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="d7164-120">若要了解如何设置通信点数，请参阅[为你的组织设置通信点数](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="d7164-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d7164-121">你还可以设置[按分钟付费的音频会议](/microsoftteams/audio-conferencing-pay-per-minute)。</span><span class="sxs-lookup"><span data-stu-id="d7164-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="d7164-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="d7164-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="d7164-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d7164-123"><a name="__top"> </a></span></span>

<span data-ttu-id="d7164-124">针对音频会议，你不能使用用户电话号码；你需要获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="d7164-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="d7164-125">你可以获取会议网桥的收费或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="d7164-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="d7164-126">有三种获取收费和免费电话服务号码的方法：</span><span class="sxs-lookup"><span data-stu-id="d7164-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="d7164-127">**使用 Skype For business 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d7164-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="d7164-128">对于某些国家/地区，您可以使用 Skype for Business 管理中心获取您的会议桥的服务号码。</span><span class="sxs-lookup"><span data-stu-id="d7164-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="d7164-129">参见[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="d7164-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="d7164-130">**转网现有服务号码**。</span><span class="sxs-lookup"><span data-stu-id="d7164-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="d7164-131">将当前服务提供商或电话运营商的现有号码移植或转移到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d7164-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d7164-132">有关详细信息，请参阅[将电话号码转移到 Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，从而帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d7164-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="d7164-133">**使用新号码的请求表单**。</span><span class="sxs-lookup"><span data-stu-id="d7164-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="d7164-134">有时（取决于您所在的国家/地区）您将无法使用 Skype for Business 管理中心获取新的服务号码，或者您需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="d7164-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="d7164-135">如果是这样，则需下载表单并将其发回给我们。</span><span class="sxs-lookup"><span data-stu-id="d7164-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="d7164-136">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="d7164-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="d7164-137">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="d7164-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="d7164-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d7164-138"><a name="__top"> </a></span></span>

<span data-ttu-id="d7164-139">获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。</span><span class="sxs-lookup"><span data-stu-id="d7164-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="d7164-140">将新的电话号码分配给音频会议网桥：</span><span class="sxs-lookup"><span data-stu-id="d7164-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="d7164-141">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="d7164-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="d7164-142">转到 **Microsoft 365 管理中心** > **管理中心** > **Teams** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="d7164-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="d7164-143">选择“**语音**” > “**电话号码**”。</span><span class="sxs-lookup"><span data-stu-id="d7164-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="d7164-144">选择电话号码，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="d7164-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="d7164-145">有关更多详细信息，请参阅[在音频会议网桥上更改电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d7164-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="d7164-146">第 5 步：设置会议网桥的默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="d7164-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="d7164-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d7164-147"><a name="__top"> </a></span></span>

<span data-ttu-id="d7164-148">接下来，你希望为会议自动助理在拨入到音频会议的电话号码时使用的[音频会议设置自动助理语言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)问候呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d7164-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="d7164-149">![显示 Microsoft Teams 徽标的图标](../images/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d7164-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d7164-150">从仪表板中，转到**会议** > **会议网桥**。</span><span class="sxs-lookup"><span data-stu-id="d7164-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d7164-151">选择会议网桥电话号码，单击“**编辑**”，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="d7164-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="d7164-152">![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标：</span><span class="sxs-lookup"><span data-stu-id="d7164-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="d7164-153">转到管理中心**团队** >  >  **> "管理中心"** 团队 "**旧版门户**"。</span><span class="sxs-lookup"><span data-stu-id="d7164-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d7164-154">选择 "**音频会议** > "**Microsoft 网桥**。</span><span class="sxs-lookup"><span data-stu-id="d7164-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="d7164-155">选择 "会议桥接电话号码"，选择 "**设置语言**"，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="d7164-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="d7164-156">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="d7164-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="d7164-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d7164-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="d7164-158">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="d7164-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="d7164-159">![显示 Microsoft Teams 徽标的图标](../images/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d7164-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d7164-160">从仪表板中，转到**会议** > **会议网桥**。</span><span class="sxs-lookup"><span data-stu-id="d7164-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d7164-161">选择“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="d7164-161">Select **Bridge settings**.</span></span> <span data-ttu-id="d7164-162">这将打开**网桥设置**窗格。</span><span class="sxs-lookup"><span data-stu-id="d7164-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="d7164-163">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d7164-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="d7164-164">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="d7164-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="d7164-165">转到 **Microsoft 365 管理中心** > **管理中心** > **Teams** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="d7164-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d7164-166">选择 "**音频会议** > "**Microsoft bridge 设置**。</span><span class="sxs-lookup"><span data-stu-id="d7164-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="d7164-167">这将打开 **Microsoft 网桥设置** 页。</span><span class="sxs-lookup"><span data-stu-id="d7164-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="d7164-168">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d7164-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="d7164-169">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="d7164-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="d7164-170">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d7164-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="d7164-171">你需要为在组织中主持或安排会议的所有人员执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d7164-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="d7164-172">![显示 Microsoft Teams 徽标的图标](../images/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d7164-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d7164-173">在仪表板上，单击“**用户**”，从列表中选择用户，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="d7164-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="d7164-174">选择“**音频会议**”旁边的“**编辑**”，然后在“**音频会议**”窗格中，在“**收费电话号码**”和“**免费**”电话号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="d7164-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="d7164-175">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="d7164-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="d7164-176">转到**Microsoft 365 管理中心** > **团队** > "**旧版门户**"。</span><span class="sxs-lookup"><span data-stu-id="d7164-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="d7164-177">选择 "**音频会议** > **用户**"，然后从列表中选择用户，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d7164-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="d7164-178">如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="d7164-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="d7164-179">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="d7164-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="d7164-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d7164-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="d7164-181">为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="d7164-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="d7164-182">但是，如果需要也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。</span><span class="sxs-lookup"><span data-stu-id="d7164-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="d7164-183">参见[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="d7164-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="d7164-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7164-184">Related topics</span></span>

[<span data-ttu-id="d7164-185">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="d7164-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="d7164-186">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d7164-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="d7164-187">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="d7164-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="d7164-188">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="d7164-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
