---
title: 设置音频会议 for Skype Business 和 Microsoft 团队
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
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何设置电话拨入式或音频会议的人员在您的业务需要加入使用电话的电话会议。 '
ms.openlocfilehash: e7621d98c68e5a3ce290a4d271e6700905e2344a
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753623"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="f065d-103">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f065d-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="f065d-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span><span class="sxs-lookup"><span data-stu-id="f065d-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="f065d-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="f065d-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="f065d-109">有关音频会议的常见问题，请参阅 [音频会议的常见问题](/MicrosoftTeams/audio-conferencing-common-questions) 。</span><span class="sxs-lookup"><span data-stu-id="f065d-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="f065d-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="f065d-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="f065d-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f065d-111"><a name="__top"> </a></span></span>


<span data-ttu-id="f065d-112">转到[音频会议和通话套餐国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="f065d-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="f065d-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="f065d-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="f065d-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f065d-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
        
2. <span data-ttu-id="f065d-p104">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span><span class="sxs-lookup"><span data-stu-id="f065d-p104">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="f065d-p105">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="f065d-p105">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f065d-p106">You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.</span><span class="sxs-lookup"><span data-stu-id="f065d-p106">You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="f065d-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="f065d-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="f065d-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f065d-123"><a name="__top"> </a></span></span>

<span data-ttu-id="f065d-p107">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers:</span><span class="sxs-lookup"><span data-stu-id="f065d-p107">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="f065d-p108">**Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="f065d-p108">**Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="f065d-p109">**Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span><span class="sxs-lookup"><span data-stu-id="f065d-p109">**Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="f065d-p110">**Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span><span class="sxs-lookup"><span data-stu-id="f065d-p110">**Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="f065d-136">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="f065d-136">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="f065d-137"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f065d-137"><a name="__top"> </a></span></span>

<span data-ttu-id="f065d-138">获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。</span><span class="sxs-lookup"><span data-stu-id="f065d-138">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invites.</span></span>  

<span data-ttu-id="f065d-139">将新的电话号码分配给音频会议网桥：</span><span class="sxs-lookup"><span data-stu-id="f065d-139">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="f065d-140">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="f065d-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 <span data-ttu-id="f065d-141">转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **语音** > **电话号码**，选择电话号码，然后单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="f065d-141">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**, select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="f065d-142">有关详细信息，请参阅[Change 音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="f065d-142">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="f065d-143">第 5 步：设置会议网桥的默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="f065d-143">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="f065d-144"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f065d-144"><a name="__top"> </a></span></span>

<span data-ttu-id="f065d-145">接下来，您要[进行音频会议自动助理语言设置](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议自动助理使用它们拨入电话号码的音频会议时问候呼叫者。</span><span class="sxs-lookup"><span data-stu-id="f065d-145">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet a caller when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="f065d-146">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="f065d-146">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

<span data-ttu-id="f065d-147">从仪表板中，转到**会议** > **会议网桥**，选择会议网桥电话号码，单击**编辑**，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="f065d-147">From the Dashboard, go to **Meetings** > **Conference bridges**, select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="f065d-148">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**:</span><span class="sxs-lookup"><span data-stu-id="f065d-148">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

<span data-ttu-id="f065d-149">转到**Office 365 管理中心** > **管理中心** > **for Business 的 Skype** > **音频会议** > **Microsoft 桥**，选择会议桥接电话号码，然后单击**设置语言**。</span><span class="sxs-lookup"><span data-stu-id="f065d-149">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge**,  select the conferencing bridge phone number, and then click **Set languages**.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="f065d-150">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="f065d-150">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="f065d-151"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f065d-151"><a name="__top"> </a></span></span>
    
<span data-ttu-id="f065d-152">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="f065d-152">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="f065d-153">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="f065d-153">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

<span data-ttu-id="f065d-p111">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="f065d-p111">From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="f065d-157">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="f065d-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="f065d-p112">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="f065d-p112">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="f065d-161">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="f065d-161">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="f065d-162">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="f065d-162">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="f065d-p113">You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:</span><span class="sxs-lookup"><span data-stu-id="f065d-p113">You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:</span></span>

<span data-ttu-id="f065d-165">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="f065d-165">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

<span data-ttu-id="f065d-166">从仪表板中，单击**用户**，从列表中选择用户，单击**编辑**，单击**音频会议**旁边的**编辑**，然后在**音频会议**窗格中，在**收费电话号码**和**免费**电话号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="f065d-166">From the Dashboard, click **Users**, select the user from the list, click **Edit**, click **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="f065d-167">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="f065d-167">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

<span data-ttu-id="f065d-p114">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f065d-p114">Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="f065d-170">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="f065d-170">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="f065d-171"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f065d-171"><a name="__top"> </a></span></span>
 
<span data-ttu-id="f065d-p115">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="f065d-p115">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="f065d-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="f065d-175">Related topics</span></span>

[<span data-ttu-id="f065d-176">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="f065d-176">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="f065d-177">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f065d-177">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="f065d-178">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="f065d-178">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="f065d-179">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="f065d-179">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
