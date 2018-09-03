---
title: 为 Skype for Business 和 Microsoft Teams 设置音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何为需要加入使用电话的电话会议的企业人员设置电话拨入式或音频会议。 '
ms.openlocfilehash: 02c04afa0a1079a53123ee56094dc6ddc764038c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780528"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="28036-103">为 Skype for Business 和 Microsoft Teams 设置音频会议</span><span class="sxs-lookup"><span data-stu-id="28036-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="28036-104">有时，组织中的人员需要使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="28036-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="28036-105">Skype for Business 和 Microsoft Teams 包括适用于这种情况的音频会议功能！</span><span class="sxs-lookup"><span data-stu-id="28036-105">Skype for Business and Microsoft Teams include the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="28036-106">人们可以使用电话拨入 Skype for Business 或 Microsoft Teams 会议，而无需使用移动设备或电脑上的 Skype for Business 或 Microsoft Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="28036-106">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="28036-107">你只需为计划要安排或主持会议的人员设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="28036-107">You only need to set up dial-in conferencing for users who plan to schedule or lead meetings.</span></span> <span data-ttu-id="28036-108">拨入会议与会者不需要分配给他们或其他安装程序的许可证。</span><span class="sxs-lookup"><span data-stu-id="28036-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="28036-109">有关音频会议的常见问题，请参阅[音频会议常见问题](/MicrosoftTeams/audio-conferencing-common-questions)。</span><span class="sxs-lookup"><span data-stu-id="28036-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="28036-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="28036-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="28036-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="28036-111"></span></span>


<span data-ttu-id="28036-112">转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="28036-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="28036-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="28036-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="28036-114">针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。</span><span class="sxs-lookup"><span data-stu-id="28036-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="28036-115">要想了解需要为音频会议购买哪些许可证以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="28036-115">To learn which licenses you need to buy for dial-in conferencing, and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
        
2. <span data-ttu-id="28036-116">购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。</span><span class="sxs-lookup"><span data-stu-id="28036-116">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="28036-117">请参阅[分配或删除 Office 365 for business 许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)你购买给组织中打算安排或主持会议的人员。</span><span class="sxs-lookup"><span data-stu-id="28036-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="28036-118">我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。</span><span class="sxs-lookup"><span data-stu-id="28036-118">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="28036-119">要了解如何设置通信点数，请参阅[为你的组织设置通信点数](/microsoftteams/set-up-communications-credits-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="28036-119">To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="28036-120">你还可以设置按分钟付费的音频会议。</span><span class="sxs-lookup"><span data-stu-id="28036-120">You can also set up pay-per-minute Audio Conferencing.</span></span> <span data-ttu-id="28036-121">转到[此处](/microsoftteams/audio-conferencing-pay-per-minute)查找有关如何使用的更多信息。</span><span class="sxs-lookup"><span data-stu-id="28036-121">Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="28036-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="28036-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="28036-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="28036-123"></span></span>

<span data-ttu-id="28036-124">针对音频会议，你不能使用用户电话号码；你需要获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="28036-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="28036-125">你可以获取会议网桥的收费或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="28036-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="28036-126">有三种获取收费和免费电话服务号码的方法：</span><span class="sxs-lookup"><span data-stu-id="28036-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="28036-127">**使用 Skype for Business 管理中心。**</span><span class="sxs-lookup"><span data-stu-id="28036-127">**Use the Skype for Business admin center**</span></span> <span data-ttu-id="28036-128">某些国家/地区内，你可以使用 Skype for Business 管理中心获取会议网桥服务号码，请参阅[获取服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="28036-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="28036-129">**转网现有的服务号码。**</span><span class="sxs-lookup"><span data-stu-id="28036-129">**** Port or transfer existing service numbers</span></span> <span data-ttu-id="28036-130">将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="28036-130">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="28036-131">有关详细信息，请参阅[将电话号码转移到 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) 或[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)，从而帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="28036-131">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="28036-132">**使用新号码的请求表单。**</span><span class="sxs-lookup"><span data-stu-id="28036-132">**Use a request form for new numbers.**</span></span> <span data-ttu-id="28036-133">有时（具体取决于你的国家/地区），你无法使用 Skype for Business 管理中心获取新服务号码，或你需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="28036-133">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="28036-134">如果是这样，你需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="28036-134">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="28036-135">有关详细信息，请参阅[管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="28036-135">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="28036-136">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="28036-136">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="28036-137"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="28036-137"></span></span>

<span data-ttu-id="28036-138">获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。</span><span class="sxs-lookup"><span data-stu-id="28036-138">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invites.</span></span>  

<span data-ttu-id="28036-139">将新的电话号码分配给音频会议网桥：</span><span class="sxs-lookup"><span data-stu-id="28036-139">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="28036-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

 <span data-ttu-id="28036-141">转到 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **语音** > **电话号码**，选择电话号码，然后单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="28036-141">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

<span data-ttu-id="28036-142">有关详细信息，请参阅 [更改音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="28036-142">For more information, see [Change the toll or toll-free numbers on your dial-in conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="28036-143">第 5 步：设置会议网桥的默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="28036-143">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="28036-144"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="28036-144"></span></span>

<span data-ttu-id="28036-145">接下来，你要[设置音频会议自动助理语言](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)，会议自动助理使用这些语言在致电者拨入音频会议电话号码时向其发出问候。</span><span class="sxs-lookup"><span data-stu-id="28036-145">[Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> 

<span data-ttu-id="28036-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="28036-147">从仪表板中，转到**会议** > **会议网桥**，选择会议网桥电话号码，单击**编辑**，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="28036-147">From the Dashboard, go to **Meetings** > **Conference bridges**, select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="28036-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="28036-149">转到 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议** > **Microsoft 网桥设置**，选择会议网桥电话号码，然后单击**设置语言**。</span><span class="sxs-lookup"><span data-stu-id="28036-149">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**,  select the conferencing bridge phone number, and then click **Set languages**.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="28036-150">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="28036-150">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="28036-151"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="28036-151"></span></span>
    
<span data-ttu-id="28036-152">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="28036-152">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="28036-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="28036-154">从仪表板中，转到**会议** > **会议网桥** > **网桥设置**。</span><span class="sxs-lookup"><span data-stu-id="28036-154">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**.</span></span> <span data-ttu-id="28036-155">这将打开**网桥设置**窗格。</span><span class="sxs-lookup"><span data-stu-id="28036-155">This will open the **Bridge settings** pane.</span></span> <span data-ttu-id="28036-156">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="28036-156">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="28036-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="28036-158">转到 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议** > **Microsoft 网桥设置**。</span><span class="sxs-lookup"><span data-stu-id="28036-158">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="28036-159">这将打开 **Microsoft 网桥设置** 页。</span><span class="sxs-lookup"><span data-stu-id="28036-159">This will open the **Microsoft bridge settings** page.</span></span> <span data-ttu-id="28036-160">有关详细信息，请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="28036-160">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="28036-161">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="28036-161">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="28036-162">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="28036-162">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="28036-163">你需要为在组织中主持或安排会议的所有人员执行此操作。</span><span class="sxs-lookup"><span data-stu-id="28036-163">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="28036-164">待办事项：</span><span class="sxs-lookup"><span data-stu-id="28036-164">To do this run:</span></span>

<span data-ttu-id="28036-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

<span data-ttu-id="28036-166">从仪表板中，单击**用户**，从列表中选择用户，单击**编辑**，单击**音频会议**旁边的**编辑**，然后在**音频会议**窗格中，在**收费电话号码**和**免费**电话号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="28036-166">From the Dashboard, click **Users**, select the user from the list, click **Edit**, click **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="28036-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="28036-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="28036-168">转到 **Office 365 管理中心** > **Skype for Business** > **音频会议** > **用户**，然后从列表中选择用户并单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="28036-168">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> <span data-ttu-id="28036-169">如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="28036-169">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="28036-170">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="28036-170">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="28036-171"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="28036-171"></span></span>
 
<span data-ttu-id="28036-172">为用户设置的电话拨入式号码将自动添加到要发送给与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="28036-172">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="28036-173">但是，如果你想要，你也可以添加自己的帮助和法律链接、文本消息和小公司图形。</span><span class="sxs-lookup"><span data-stu-id="28036-173">However, you can add your own help and legal links, a text message, and small company graphic.</span></span> <span data-ttu-id="28036-174">请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="28036-174">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md)</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="28036-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="28036-175">Related topics</span></span>

[<span data-ttu-id="28036-176">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="28036-176">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="28036-177">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="28036-177">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="28036-178">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="28036-178">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="28036-179">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="28036-179">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
