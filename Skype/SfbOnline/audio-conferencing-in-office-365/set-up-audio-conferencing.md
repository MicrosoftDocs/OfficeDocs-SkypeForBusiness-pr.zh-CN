---
title: "设置音频会议 for Skype Business 和 Microsoft 团队"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 03/15/2018
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
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "了解如何设置拨入或音频会议的人员在您的业务需要加入会议呼叫使用电话。 "
ms.openlocfilehash: 4d82de668ec31f1664fb05202979dd6df94bda2b
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="338db-103">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="338db-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="338db-104">有时，组织中的用户需要使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="338db-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="338db-105">Skype 业务和 Microsoft 小组包括音频会议功能，只是这种情况 ！</span><span class="sxs-lookup"><span data-stu-id="338db-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="338db-106">人们可以在调用到 Skype 使用电话，而不使用 Skype 业务或 Microsoft 小组在移动设备或 PC 上的应用程序的业务或 Microsoft 小组会议。</span><span class="sxs-lookup"><span data-stu-id="338db-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="338db-107">您只需设置音频会议的计划安排或会导致会议的人员。</span><span class="sxs-lookup"><span data-stu-id="338db-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="338db-108">拨入的会议与会者无需分配给它们或其他设置的任何许可证。</span><span class="sxs-lookup"><span data-stu-id="338db-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="338db-109">常见问题及解答有关音频会议，请参阅[音频会议的常见问题的解决方案](audio-conferencing-common-questions.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="338db-110">步骤 1： 找出是否音频会议将在您的国家/地区</span><span class="sxs-lookup"><span data-stu-id="338db-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="338db-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="338db-111"></span></span>


<span data-ttu-id="338db-112">转到[音频会议和调用计划的国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择您的国家 / 地区，若要获取有关音频会议的可用性信息以及有关电话系统，调用计划，收费和免费的信息数字和通信的贷方。</span><span class="sxs-lookup"><span data-stu-id="338db-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="338db-113">第 2 步： 获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="338db-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="338db-114">对于音频会议，您需要为每个用户都将设置拨入会议许可证。</span><span class="sxs-lookup"><span data-stu-id="338db-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="338db-115">您需要购买音频会议和多少成本的许可证，请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
        
2. <span data-ttu-id="338db-116">购买的音频会议许可证后，您将结束将它们指派给您的组织中将安排或会导致会议的人员。</span><span class="sxs-lookup"><span data-stu-id="338db-116">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="338db-117">请参阅[分配或删除业务的 Office 365 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)您购买到您的组织中要发送到时间表或领导会议的人。</span><span class="sxs-lookup"><span data-stu-id="338db-117">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="338db-118">我们还建议您指定通信片尾许可证 （它们不收取任何费用） 许可证上一步中的分配给同一个人。</span><span class="sxs-lookup"><span data-stu-id="338db-118">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="338db-119">若要了解如何设置通讯片尾，请参阅[设置为您的组织的通信贷](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-119">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="338db-120">您还可以设置付薪每分钟音频会议。</span><span class="sxs-lookup"><span data-stu-id="338db-120">You can also set up pay-per-minute Audio Conferencing.</span></span> <span data-ttu-id="338db-121">转[此处](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md)以了解更多关于如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="338db-121">Go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) to find out more about how to use them.</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="338db-122">第 3 步： 获得的会议桥的服务数</span><span class="sxs-lookup"><span data-stu-id="338db-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="338db-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="338db-123"></span></span>

<span data-ttu-id="338db-124">对于音频会议，您不能使用电话号码用户;您将需要获得服务号码。</span><span class="sxs-lookup"><span data-stu-id="338db-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="338db-125">可以获取会议桥的收费或免费的服务号码。</span><span class="sxs-lookup"><span data-stu-id="338db-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="338db-126">有三种方式获取收费和免费电话服务号码：</span><span class="sxs-lookup"><span data-stu-id="338db-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="338db-127">**使用 Skype 业务管理中心。**</span><span class="sxs-lookup"><span data-stu-id="338db-127">**Use the Skype for Business admin center.**</span></span> <span data-ttu-id="338db-128">某些国家/地区，您可以获得您会议桥的业务管理中心使用 Skype 的服务数，请参阅[获得服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="338db-129">**您现有的服务编号的端口。**</span><span class="sxs-lookup"><span data-stu-id="338db-129">**Port your existing service numbers.**</span></span> <span data-ttu-id="338db-130">端口或从您的当前服务提供商或电话运营商的现有数字转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="338db-130">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="338db-131">您可以看到[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)或[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的详细信息可帮助您做到这一点。</span><span class="sxs-lookup"><span data-stu-id="338db-131">You can see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="338db-132">**使用新的号码请求窗体。**</span><span class="sxs-lookup"><span data-stu-id="338db-132">**Use a request form for new numbers.**</span></span> <span data-ttu-id="338db-133">有时 （具体取决于您的国家/地区） 将能够获得新业务管理中心，使用 Skype 服务数字或您需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="338db-133">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="338db-134">如果是这样，你需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="338db-134">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="338db-135">有关更多信息，请参见[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-135">See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="338db-136">步骤 4： 将服务号码分配给会议桥</span><span class="sxs-lookup"><span data-stu-id="338db-136">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="338db-137"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="338db-137"></span></span>

<span data-ttu-id="338db-138">一旦您获取会议桥收费和/或免费电话号码，您需要分配编号，以便可以在会议邀请中使用它们。</span><span class="sxs-lookup"><span data-stu-id="338db-138">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invites.</span></span>  

<span data-ttu-id="338db-139">要为音频会议桥新的电话号码，请转到**Office 365 管理中心** > **中心管理** > **业务的 Skype** > **语音** > **的电话号码**，选择电话编号，然后单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="338db-139">To assign a new phone number to your audio conferencing bridge, go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**, select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="338db-140">有关详细信息，请参阅[指派到音频会议桥的新电话号码](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-140">For more details, see [Assign a new phone number to your audio conferencing bridge](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="338db-141">步骤 5： 设置默认和备用语言会议桥</span><span class="sxs-lookup"><span data-stu-id="338db-141">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="338db-142"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="338db-142"></span></span>

<span data-ttu-id="338db-143">接下来，您需要[设置自动助理语言音频会议的](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)会议自动助理用来招呼呼叫者，当他们拨入电话号码的音频会议。</span><span class="sxs-lookup"><span data-stu-id="338db-143">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet a caller when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="338db-144">请转到**Office 365 管理中心** > **中心管理** > **Skype 业务** > **音频会议** > **Microsoft 网桥的设置**，选择会议桥的电话号码，然后再单击**设置语言**。</span><span class="sxs-lookup"><span data-stu-id="338db-144">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**,  select the conferencing bridge phone number, and then click **Set languages**.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="338db-145">第 6 步： 设置您的会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="338db-145">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="338db-146"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="338db-146"></span></span>
    
<span data-ttu-id="338db-147">设置会议桥后, 确认，如入口/出口通知和针长度的默认设置是您想要使用;如果他们不这样做，您可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="338db-147">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="338db-148">您可以转到**Office 365 管理中心** > **中心管理** > **业务的 Skype** > **音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="338db-148">You can go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="338db-149">这将打开**Microsoft 桥设置**页。</span><span class="sxs-lookup"><span data-stu-id="338db-149">This will open the **Microsoft bridge settings** page.</span></span> <span data-ttu-id="338db-150">有关详细信息，请参阅[更改音频会议桥的设置](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-150">For more details, see [Change the settings for an Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-the-audio-conferencing-provider-and-dial-in-phone-numbers"></a><span data-ttu-id="338db-151">第 7 步： 指定音频会议提供商和拨入电话号码</span><span class="sxs-lookup"><span data-stu-id="338db-151">Step 7: Assign the audio conferencing provider and dial-in phone numbers</span></span>

<span data-ttu-id="338db-152">现在，您需要确保 Microsoft 指定为该提供程序，并且为它们设置的收费和免费电话号码，在同一时间。</span><span class="sxs-lookup"><span data-stu-id="338db-152">Now you need to make sure that Microsoft is assigned as the provider, and set the toll and toll-free numbers for them at the same time.</span></span>

<span data-ttu-id="338db-153">将 Microsoft 作为提供程序分配给组织中的人员，领导或计划会议，请转到**Office 365 管理中心** > **业务的 Skype** > **音频会议** > **用户**，然后选择用户从列表，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="338db-153">Assign Microsoft as the provider to people in your organization who lead or schedule meetings, by going to **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> <span data-ttu-id="338db-154">如果您需要更多详细信息，请参阅[分配作为音频会议提供商](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-154">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>

<span data-ttu-id="338db-155">在设置提供程序时，您还可以设置收费和免费电话号码将被添加到会议，邀请该用户。</span><span class="sxs-lookup"><span data-stu-id="338db-155">When you are setting the provider, you can also set the toll and toll-free numbers that will be added to meeting invites for that user.</span></span> <span data-ttu-id="338db-156">只需从下拉列表中选择电话号码。</span><span class="sxs-lookup"><span data-stu-id="338db-156">Simply select the phone numbers from the drop-down lists.</span></span> <span data-ttu-id="338db-157">有关详细信息，请参阅[设置数字包括在邀请电话](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-157">For more details, see [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span> 


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="338db-158">第 8 步： 设置会议邀请 （可选）</span><span class="sxs-lookup"><span data-stu-id="338db-158">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="338db-159"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="338db-159"></span></span>
 
<span data-ttu-id="338db-160">为用户设置拨入号码将自动添加到向与会者发送会议邀请。</span><span class="sxs-lookup"><span data-stu-id="338db-160">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="338db-161">但是，您可以添加您自己的帮助和法律链接、 文本消息和小型公司图形如果希望。</span><span class="sxs-lookup"><span data-stu-id="338db-161">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="338db-162">请参阅[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="338db-162">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="338db-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="338db-163">Related topics</span></span>

[<span data-ttu-id="338db-164">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="338db-164">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="338db-165">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="338db-165">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="338db-166">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="338db-166">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="338db-167">设置选项用于联机会议和电话会议</span><span class="sxs-lookup"><span data-stu-id="338db-167">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
