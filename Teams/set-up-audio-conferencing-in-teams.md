---
title: 设置 Microsoft Teams 的音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何为业务中需要使用电话加入电话会议的人员设置拨号或音频会议。 '
ms.openlocfilehash: d1596a650507938e8dc3e87fb02dec68e415f6d6
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031418"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="ef8a0-103">设置 Microsoft Teams 的音频会议</span><span class="sxs-lookup"><span data-stu-id="ef8a0-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="ef8a0-104">有时组织中的人员会需要使用电话呼入会议。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="ef8a0-105">Microsoft Teams 包含了正是针对此种情况的音频会议功能。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="ef8a0-106">人们可以使用电话呼入 Teams 会议，而无需使用移动设备或电脑上的 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="ef8a0-107">你只需为打算安排或主持会议的人设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="ef8a0-108">拨入会议与会者不需要分配给他们或其他安装程序的许可证。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="ef8a0-109">有关音频会议的常见问题，请参阅 [音频会议的常见问题](audio-conferencing-common-questions.md) 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="ef8a0-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="ef8a0-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="ef8a0-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ef8a0-111"><a name="__top"> </a></span></span>

<span data-ttu-id="ef8a0-112">转到[音频会议和通话套餐国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="ef8a0-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="ef8a0-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="ef8a0-114">针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="ef8a0-115">若想了解需要为电话音频会议购买哪些许可证以及它们的价格，请参阅 [Microsoft Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="ef8a0-116">Office 365 企业版 E5 许可证中包含音频会议，并用作加载项。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="ef8a0-117">购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="ef8a0-118">请参阅向组织中的 [365 365 用户分配许可证，将许可证分配](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 给您的组织中要安排或领导会议的人员。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-118">See [Assign licenses to users in Microsoft 365 or Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="ef8a0-119">我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="ef8a0-120">若要了解如何设置通信点数，请参阅[为你的组织设置通信点数](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef8a0-121">你还可以设置[按分钟付费的音频会议](audio-conferencing-pay-per-minute.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="ef8a0-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="ef8a0-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="ef8a0-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ef8a0-123"><a name="__top"> </a></span></span>

<span data-ttu-id="ef8a0-124">针对音频会议，你不能使用用户电话号码；你需要获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="ef8a0-125">你可以获取会议网桥的收费或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="ef8a0-126">有三种获取收费和免费电话服务号码的方法：</span><span class="sxs-lookup"><span data-stu-id="ef8a0-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="ef8a0-127">**使用 Microsoft Teams 管理中心** 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="ef8a0-128">某些国家/地区内，你可以使用 Microsoft Teams 管理中心获取会议网桥服务号码。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="ef8a0-129">参见[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="ef8a0-130">**转网现有服务号码** 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="ef8a0-131">将当前服务提供商或电话运营商的现有号码移植或转移到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ef8a0-132">有关详细信息，请参阅[将电话号码转移到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，从而帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="ef8a0-133">**使用新号码的请求表单** 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="ef8a0-134">有时（具体取决于你的国家/地区），你无法使用 Microsoft Teams 管理中心获取新服务号码，或你需要特定的电话号码或区号。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="ef8a0-135">如果是这样，则需下载表单并将其发回给我们。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="ef8a0-136">有关详细信息，请参阅[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="ef8a0-137">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="ef8a0-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="ef8a0-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ef8a0-138"><a name="__top"> </a></span></span>

<span data-ttu-id="ef8a0-139">获取会议网桥的收费和/或免费电话号码后，你需要分配号码，以便它们可以在会议邀请上使用。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="ef8a0-140">按照下列步骤将新的电话号码分配给音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="ef8a0-141">![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png) **使用 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="ef8a0-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="ef8a0-142">转到 **Microsoft 365 管理中心** > **管理中心** > **Teams** > **旧版门户** 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="ef8a0-143">选择“ **语音** ” > “ **电话号码** ”。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="ef8a0-144">选择电话号码，然后单击“ **分配** ”。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="ef8a0-145">有关详细信息，参见[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="ef8a0-146">步骤 5：为会议桥设置默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="ef8a0-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="ef8a0-147"><a name="__top"> </a> 接下来，需要[在 Microsoft 团队中为音频会议设置自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)， 会议自动助理在拨入电话号码进行音频会议时欢迎主叫方。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="ef8a0-148">![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心** ：</span><span class="sxs-lookup"><span data-stu-id="ef8a0-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center** :</span></span>

1. <span data-ttu-id="ef8a0-149">从仪表板中，转到 **会议** > **会议网桥** 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ef8a0-150">选择会议网桥电话号码，单击“ **编辑** ”，然后选择默认语言。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-150">Select the conferencing bridge phone number, click **Edit** , and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="ef8a0-151">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="ef8a0-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="ef8a0-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ef8a0-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="ef8a0-153">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="ef8a0-154">![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心** ：</span><span class="sxs-lookup"><span data-stu-id="ef8a0-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center** :</span></span>

1. <span data-ttu-id="ef8a0-155">从仪表板中，转到 **会议** > **会议网桥** 。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ef8a0-156">选择“ **网桥设置** ”。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-156">Select **Bridge settings**.</span></span> <span data-ttu-id="ef8a0-157">这将打开 **网桥设置** 窗格。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="ef8a0-158">有关详细信息，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="ef8a0-159">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="ef8a0-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="ef8a0-160">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="ef8a0-161">你需要为在组织中主持或安排会议的所有人员执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="ef8a0-162">![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心** ：</span><span class="sxs-lookup"><span data-stu-id="ef8a0-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center** :</span></span>

1. <span data-ttu-id="ef8a0-163">在仪表板上，单击“ **用户** ”，从列表中选择用户，然后选择“ **编辑** ”。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-163">From the Dashboard, click **Users** , select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="ef8a0-164">选择“ **音频会议** ”旁边的“ **编辑** ”，然后在“ **音频会议** ”窗格中，在“ **收费电话号码** ”和“ **免费** ”电话号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-164">Select **Edit** next to **Audio Conferencing** , and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="ef8a0-165">如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="ef8a0-166">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="ef8a0-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="ef8a0-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ef8a0-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="ef8a0-168">为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="ef8a0-169">但是，如果需要也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="ef8a0-170">参见[自定义会议邀请](meeting-settings-in-teams.md#customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="ef8a0-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="ef8a0-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="ef8a0-171">Related topics</span></span>

[<span data-ttu-id="ef8a0-172">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="ef8a0-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="ef8a0-173">Microsoft Teams 中用于音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="ef8a0-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="ef8a0-174">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="ef8a0-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
