---
title: 为会议设置音频Skype for Business
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
ms.openlocfilehash: ce5d80b8be0fe2e6983229be8185bcdf02e06ab6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237638"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="e0f3e-103">为会议设置音频Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e0f3e-103">Set up Audio Conferencing for Skype for Business</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e0f3e-104">有时，组织中的人员需要使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="e0f3e-105">Skype for Business音频会议功能，</span><span class="sxs-lookup"><span data-stu-id="e0f3e-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="e0f3e-106">用户可以通过电话Skype for Business呼叫参加会议，而不是在Skype for Business或电脑上使用会议应用。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="e0f3e-107">你只需为打算安排或主持会议的人设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="e0f3e-108">拨入会议与会者不需要分配给他们或其他安装程序的许可证。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="e0f3e-109">有关音频会议的常见问题，请参阅 [音频会议的常见问题](/MicrosoftTeams/audio-conferencing-common-questions) 。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="e0f3e-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="e0f3e-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="e0f3e-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e0f3e-111"><a name="__top"> </a></span></span>

<span data-ttu-id="e0f3e-112">转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="e0f3e-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="e0f3e-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="e0f3e-114">针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="e0f3e-115">若要了解需要为音频会议购买哪些许可证及其费用，请参阅Skype for Business[许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="e0f3e-116">Office 365 企业版 E5 许可证中包含音频会议，并用作加载项。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="e0f3e-117">购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="e0f3e-118">请参阅[为组织中计划或Microsoft 365 商业应用版](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)的人分配或删除您购买的许可证。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-118">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="e0f3e-119">我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="e0f3e-120">若要了解如何设置通信点数，请参阅[为你的组织设置通信点数](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e0f3e-121">你还可以设置[按分钟付费的音频会议](/microsoftteams/audio-conferencing-pay-per-minute)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="e0f3e-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="e0f3e-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="e0f3e-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e0f3e-123"><a name="__top"> </a></span></span>

<span data-ttu-id="e0f3e-124">针对音频会议，你不能使用用户电话号码；你需要获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="e0f3e-125">你可以获取会议网桥的收费或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="e0f3e-126">有三种获取收费和免费电话服务号码的方法：</span><span class="sxs-lookup"><span data-stu-id="e0f3e-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="e0f3e-127">**使用 Skype for Business管理中心**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="e0f3e-128">对于一些国家/地区，可以使用会议管理中心获取Skype for Business号码。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="e0f3e-129">参见[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="e0f3e-130">**转网现有服务号码**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="e0f3e-131">将现有号码从当前服务提供商或电话运营商转Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e0f3e-132">有关详细信息，请参阅[将电话号码转移到 Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，从而帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="e0f3e-133">**使用新号码的请求表单**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="e0f3e-134">有时 (你的国家/地区) 你将无法使用 Skype for Business 管理中心获取新服务号码，或者你需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="e0f3e-135">如果是这样，则需下载表单并将其发回给我们。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="e0f3e-136">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="e0f3e-137">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="e0f3e-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="e0f3e-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e0f3e-138"><a name="__top"> </a></span></span>

<span data-ttu-id="e0f3e-139">获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="e0f3e-140">将新的电话号码分配给音频会议网桥：</span><span class="sxs-lookup"><span data-stu-id="e0f3e-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="e0f3e-141">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="e0f3e-142">转到 **Microsoft 365 管理中心** > **管理中心** > **Teams** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="e0f3e-143">选择“**语音**” > “**电话号码**”。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="e0f3e-144">选择电话号码，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="e0f3e-145">有关详细信息，请参阅 [更改音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="e0f3e-146">第 5 步：设置会议网桥的默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="e0f3e-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="e0f3e-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e0f3e-147"><a name="__top"> </a></span></span>

<span data-ttu-id="e0f3e-148">接下来，你想要为音频[](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议设置自动助理语言，会议自动助理在呼叫者拨入音频会议的电话号码时，使用这些语言问候呼叫者。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="e0f3e-149">![显示 Microsoft Teams 徽标的图标](../images/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="e0f3e-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e0f3e-150">从仪表板中，转到 **会议** > **会议网桥**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e0f3e-151">选择会议网桥电话号码，单击“**编辑**”，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="e0f3e-152">![一个图标，显示Skype for Business ](../images/sfb-logo-30x30.png) **徽标使用Skype for Business管理中心：**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="e0f3e-153">转到管理中心>**管理Teams**  >    >  **旧门户 。**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="e0f3e-154">选择 **"音频会议**  >  **""Microsoft 网桥"。**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="e0f3e-155">选择会议网桥电话号码，选择 **"设置语言**"，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="e0f3e-156">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="e0f3e-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="e0f3e-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e0f3e-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="e0f3e-158">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="e0f3e-159">![显示 Microsoft Teams 徽标的图标](../images/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="e0f3e-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e0f3e-160">从仪表板中，转到 **会议** > **会议网桥**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e0f3e-161">选择“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-161">Select **Bridge settings**.</span></span> <span data-ttu-id="e0f3e-162">这将打开 **网桥设置** 窗格。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="e0f3e-163">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="e0f3e-164">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="e0f3e-165">转到 **Microsoft 365 管理中心** > **管理中心** > **Teams** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="e0f3e-166">选择 **"音频会议**  >  **""Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="e0f3e-167">这将打开 **Microsoft 网桥设置** 页。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="e0f3e-168">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="e0f3e-169">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="e0f3e-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="e0f3e-170">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="e0f3e-171">你需要为在组织中主持或安排会议的所有人员执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="e0f3e-172">![显示 Microsoft Teams 徽标的图标](../images/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**：</span><span class="sxs-lookup"><span data-stu-id="e0f3e-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e0f3e-173">在仪表板上，单击“**用户**”，从列表中选择用户，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="e0f3e-174">选择“**音频会议**”旁边的“**编辑**”，然后在“**音频会议**”窗格中，在“**收费电话号码**”和“**免费**”电话号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="e0f3e-175">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="e0f3e-176">转到旧版 **门户 Microsoft 365管理**  >  **Teams**  >  **中心。**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="e0f3e-177">选择 **"音频会议**  >  **用户**"，然后从列表中选择用户，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="e0f3e-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="e0f3e-178">如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="e0f3e-179">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="e0f3e-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="e0f3e-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e0f3e-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="e0f3e-181">为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="e0f3e-182">但是，如果需要也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="e0f3e-183">参见[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f3e-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="e0f3e-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="e0f3e-184">Related topics</span></span>

[<span data-ttu-id="e0f3e-185">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="e0f3e-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="e0f3e-186">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e0f3e-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="e0f3e-187">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="e0f3e-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="e0f3e-188">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="e0f3e-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
