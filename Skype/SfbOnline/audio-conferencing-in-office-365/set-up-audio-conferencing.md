---
title: 为 for Business 的 Skype 设置音频会议
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何设置电话拨入式或音频会议的人员在您的业务需要使用电话加入电话会议。 '
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229308"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="82df4-103">为 for Business 的 Skype 设置音频会议</span><span class="sxs-lookup"><span data-stu-id="82df4-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="82df4-104">有时您的组织中的人员将需要使用电话呼入会议。</span><span class="sxs-lookup"><span data-stu-id="82df4-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="82df4-105">Skype for Business 包含只是这种情况下的音频会议功能 ！</span><span class="sxs-lookup"><span data-stu-id="82df4-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="82df4-106">人员可以呼叫 Skype 业务会议使用电话，而不使用 Skype 在移动设备或 PC 上的业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="82df4-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="82df4-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="82df4-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="82df4-109">有关音频会议的常见问题，请参阅 [音频会议的常见问题](/MicrosoftTeams/audio-conferencing-common-questions) 。</span><span class="sxs-lookup"><span data-stu-id="82df4-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="82df4-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="82df4-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="82df4-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="82df4-111"><a name="__top"> </a></span></span>

<span data-ttu-id="82df4-112">转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="82df4-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="82df4-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="82df4-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="82df4-114">针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。</span><span class="sxs-lookup"><span data-stu-id="82df4-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="82df4-115">若要了解您需要音频会议和它们将成本是多少购买的许可证，请参阅[业务加载项授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="82df4-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="82df4-116">包含在 Office 365 企业 E5 许可证和作为音频会议。</span><span class="sxs-lookup"><span data-stu-id="82df4-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="82df4-117">购买的音频会议许可证后，您需要将其分配给您的组织中要安排或潜在顾客会议的人员。</span><span class="sxs-lookup"><span data-stu-id="82df4-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="82df4-118">请参阅[分配或删除业务的 Office 365 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)购买了您的组织中转到安排或负责人会议的人员。</span><span class="sxs-lookup"><span data-stu-id="82df4-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="82df4-119">我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。</span><span class="sxs-lookup"><span data-stu-id="82df4-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="82df4-120">若要了解如何设置 Communications 字幕式，请参阅[设置为您的组织的通信字幕式](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="82df4-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="82df4-121">您还可以设置[付薪每分钟音频会议](/microsoftteams/audio-conferencing-pay-per-minute)。</span><span class="sxs-lookup"><span data-stu-id="82df4-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="82df4-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="82df4-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="82df4-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="82df4-123"></span></span>

<span data-ttu-id="82df4-124">针对音频会议，你不能使用用户电话号码；你需要获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="82df4-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="82df4-125">你可以获取会议网桥的收费或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="82df4-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="82df4-126">有三种获取收费和免费电话服务号码的方法：</span><span class="sxs-lookup"><span data-stu-id="82df4-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="82df4-127">**使用业务管理中心的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="82df4-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="82df4-128">某些国家/地区，可获得使用业务管理中心的 Skype 您会议网桥服务号码。</span><span class="sxs-lookup"><span data-stu-id="82df4-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="82df4-129">请参阅[Getting 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="82df4-129">See [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="82df4-130">**端口您现有的服务号码**。</span><span class="sxs-lookup"><span data-stu-id="82df4-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="82df4-131">将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="82df4-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="82df4-132">有关详细信息，请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，从而帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="82df4-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="82df4-133">**使用新的号码的请求窗体**。</span><span class="sxs-lookup"><span data-stu-id="82df4-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="82df4-134">有时 （根据您的国家/地区） 您将无法获取您的业务管理中心中，使用 Skype 的新服务号码，或需要特定的电话号码或区域代码。</span><span class="sxs-lookup"><span data-stu-id="82df4-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="82df4-135">如果是这样，你需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="82df4-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="82df4-136">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="82df4-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="82df4-137">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="82df4-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="82df4-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="82df4-138"></span></span>

<span data-ttu-id="82df4-139">获取后收费和/或免费电话号码的会议桥，您需要分配的号码，以便可以在会议邀请中使用。</span><span class="sxs-lookup"><span data-stu-id="82df4-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="82df4-140">将新的电话号码分配给音频会议网桥：</span><span class="sxs-lookup"><span data-stu-id="82df4-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="82df4-141">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="82df4-141">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="82df4-142">转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="82df4-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="82df4-143">选择**语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="82df4-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="82df4-144">选择电话号码，然后单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="82df4-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="82df4-145">有关详细信息，请参阅[Change 音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="82df4-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="82df4-146">第 5 步：设置会议网桥的默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="82df4-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="82df4-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="82df4-147"></span></span>

<span data-ttu-id="82df4-148">接下来，您要[进行音频会议自动助理语言设置](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议自动助理使用它们拨入电话号码的音频会议时问候呼叫者。</span><span class="sxs-lookup"><span data-stu-id="82df4-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="82df4-149">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="82df4-149">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="82df4-150">从仪表板中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="82df4-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="82df4-151">选择的会议桥接电话号码，单击**编辑**，然后选择的默认语言。</span><span class="sxs-lookup"><span data-stu-id="82df4-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="82df4-152">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**:</span><span class="sxs-lookup"><span data-stu-id="82df4-152">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="82df4-153">转到**Office 365 管理中心** > **管理中心** > **团队** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="82df4-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="82df4-154">选择**音频会议** > **Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="82df4-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="82df4-155">选择的会议桥接电话号码，选择**设置语言**，，然后选择的默认语言。</span><span class="sxs-lookup"><span data-stu-id="82df4-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="82df4-156">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="82df4-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="82df4-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="82df4-157"></span></span>
    
<span data-ttu-id="82df4-158">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="82df4-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="82df4-159">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="82df4-159">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="82df4-160">从仪表板中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="82df4-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="82df4-161">选择**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="82df4-161">Select **Bridge settings**.</span></span> <span data-ttu-id="82df4-162">这将打开**网桥设置**窗格。</span><span class="sxs-lookup"><span data-stu-id="82df4-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="82df4-163">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="82df4-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="82df4-164">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="82df4-164">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="82df4-165">转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="82df4-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="82df4-166">选择**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="82df4-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="82df4-167">这将打开 **Microsoft 网桥设置** 页。</span><span class="sxs-lookup"><span data-stu-id="82df4-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="82df4-168">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="82df4-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="82df4-169">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="82df4-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="82df4-170">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="82df4-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="82df4-171">你需要为在组织中主持或安排会议的所有人员执行此操作。</span><span class="sxs-lookup"><span data-stu-id="82df4-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="82df4-172">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="82df4-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="82df4-173">在仪表板中，单击**用户**，从列表中，选择用户以及选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="82df4-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="82df4-174">选择**音频会议**，旁边的**编辑**，然后在**音频会议**窗格中，选择**收费电话号码**和**免费电话**号码列表中的一个数字。</span><span class="sxs-lookup"><span data-stu-id="82df4-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="82df4-175">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="82df4-175">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="82df4-176">转到**Microsoft 365 管理中心** > **团队** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="82df4-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="82df4-177">选择**音频会议** > **用户**，然后从列表中选择用户并单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="82df4-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="82df4-178">如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="82df4-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="82df4-179">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="82df4-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="82df4-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="82df4-180"></span></span>
 
<span data-ttu-id="82df4-181">为用户设置的电话拨入式号码将自动添加到发送给会议与会者的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="82df4-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="82df4-182">但是，您可以添加您自己的帮助和法律链接、 短信和小公司图形，如果您希望。</span><span class="sxs-lookup"><span data-stu-id="82df4-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="82df4-183">请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="82df4-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="82df4-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="82df4-184">Related topics</span></span>

[<span data-ttu-id="82df4-185">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="82df4-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="82df4-186">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="82df4-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="82df4-187">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="82df4-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="82df4-188">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="82df4-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
