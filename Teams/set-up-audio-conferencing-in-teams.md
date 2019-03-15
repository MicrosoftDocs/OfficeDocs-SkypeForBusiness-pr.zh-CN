---
title: 设置 Microsoft 团队的音频会议
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '了解如何设置电话拨入式或音频会议的人员在您的业务需要使用电话加入电话会议。 '
ms.openlocfilehash: c5925677889d9a81e15ccb15494163fd28c14639
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30635518"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="d8a0f-103">设置 Microsoft 团队的音频会议</span><span class="sxs-lookup"><span data-stu-id="d8a0f-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="d8a0f-104">有时您的组织中的人员将需要使用电话呼入会议。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="d8a0f-105">Microsoft 团队包括刚这种情况下的音频会议功能 ！</span><span class="sxs-lookup"><span data-stu-id="d8a0f-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="d8a0f-106">人员可以使用电话，而不在移动设备或 PC 上使用团队应用程序的团队会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="d8a0f-107">你只需为打算安排或主持会议的人设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="d8a0f-108">拨入会议与会者不需要分配给他们或其他安装程序的许可证。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="d8a0f-109">有关音频会议的常见问题，请参阅 [音频会议的常见问题](audio-conferencing-common-questions.md) 。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="d8a0f-110">第 1 步：了解音频会议在你所在国家/地区是否可用</span><span class="sxs-lookup"><span data-stu-id="d8a0f-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="d8a0f-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d8a0f-111"></span></span>

<span data-ttu-id="d8a0f-112">转到[音频会议和通话套餐国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)并选择你所在国家或地区，获取有关音频会议的可用性信息以及有关电话系统、通话套餐、收费和免费号码和通信点数等信息。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="d8a0f-113">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="d8a0f-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="d8a0f-114">针对音频会议，需要为将设置电话拨入式会议的每个用户购买一个许可证。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="d8a0f-115">若要了解您需要音频会议和它们将成本是多少购买的许可证，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="d8a0f-116">包含在 Office 365 企业 E5 许可证和作为音频会议。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="d8a0f-117">购买的音频会议许可证后，你需要将其分配给组织中打算安排或主持会议的那些人员。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-117">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="d8a0f-118">请参阅[分配对业务的 Office 365 中的用户的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)购买了您的组织中转到安排或负责人会议的人员。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="d8a0f-119">我们还建议你将通信点数许可证（它们不值什么钱）分配给你在上一步骤中分配到许可证的相同人员。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="d8a0f-120">若要了解如何设置 Communications 字幕式，请参阅[设置为您的组织的通信字幕式](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d8a0f-121">您还可以设置[付薪每分钟音频会议](audio-conferencing-pay-per-minute.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="d8a0f-122">第 3 步：获取会议网桥服务号码</span><span class="sxs-lookup"><span data-stu-id="d8a0f-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="d8a0f-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d8a0f-123"></span></span>

<span data-ttu-id="d8a0f-124">针对音频会议，你不能使用用户电话号码；你需要获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="d8a0f-125">你可以获取会议网桥的收费或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="d8a0f-126">有三种获取收费和免费电话服务号码的方法：</span><span class="sxs-lookup"><span data-stu-id="d8a0f-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="d8a0f-127">**使用 Microsoft 团队管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="d8a0f-128">某些国家/地区内，您可以获取您使用的 Microsoft 团队管理中心的会议桥服务号码。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="d8a0f-129">请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-129">See [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>
    
- <span data-ttu-id="d8a0f-130">**端口您现有的服务号码**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="d8a0f-131">将当前服务提供商或电话运营商提供的现有号码转网或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="d8a0f-132">有关详细信息，请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md) 或[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，从而帮助你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-132">You can see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="d8a0f-133">**使用新的号码的请求窗体**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="d8a0f-134">有时 （根据您的国家/地区） 您将无法获取您使用的 Microsoft 团队管理中心的新服务号码，或需要特定的电话号码或区域代码。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="d8a0f-135">如果是这样，你需要下载表单并将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="d8a0f-136">有关详细信息，请参阅[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="d8a0f-137">第 4 步：将服务号码分配给会议网桥</span><span class="sxs-lookup"><span data-stu-id="d8a0f-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="d8a0f-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d8a0f-138"></span></span>

<span data-ttu-id="d8a0f-139">获取后收费和/或免费电话号码的会议桥，您需要分配的号码，以便可以在会议邀请中使用。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="d8a0f-140">按照这些 stesps 分配给音频的会议桥的新的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-140">Follow these stesps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="d8a0f-141">![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **业务管理中心的使用 Skype:**</span><span class="sxs-lookup"><span data-stu-id="d8a0f-141">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="d8a0f-142">转到**Microsoft 365 管理中心** > **管理中心** > **团队** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="d8a0f-143">选择**语音** > **电话号码**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="d8a0f-144">选择电话号码，然后单击**分配**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="d8a0f-145">有关详细信息，请参阅[Change 音频会议网桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="d8a0f-146">第 5 步：设置会议网桥的默认和备用语言</span><span class="sxs-lookup"><span data-stu-id="d8a0f-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="d8a0f-147"><a name="__top"></a>接下来，您需要[设置自动助理语言中的 Microsoft 团队的音频会议](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的会议自动助理使用它们拨入电话号码的音频会议时问候呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="d8a0f-148">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d8a0f-148">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d8a0f-149">从仪表板中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d8a0f-150">选择的会议桥接电话号码，单击**编辑**，然后选择的默认语言。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="d8a0f-151">第 6 步：设置你的会议网桥设置</span><span class="sxs-lookup"><span data-stu-id="d8a0f-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="d8a0f-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d8a0f-152"></span></span>
    
<span data-ttu-id="d8a0f-153">设置你的会议网桥之后，请验证默认设置，如进入/退出通知和 PIN 长度是想要使用；如果不是，你可以更改它们。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="d8a0f-154">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d8a0f-154">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d8a0f-155">从仪表板中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="d8a0f-156">选择**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-156">Select **Bridge settings**.</span></span> <span data-ttu-id="d8a0f-157">这将打开**网桥设置**窗格。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="d8a0f-158">有关详细信息，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="d8a0f-159">第 7 步：给主持会议的用户分配电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="d8a0f-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="d8a0f-160">在创建音频会议网桥后，你需要为你的用户设置收费和免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="d8a0f-161">你需要为在组织中主持或安排会议的所有人员执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="d8a0f-162">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**：</span><span class="sxs-lookup"><span data-stu-id="d8a0f-162">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="d8a0f-163">在仪表板中，单击**用户**，从列表中，选择用户以及选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="d8a0f-164">选择**音频会议**，旁边的**编辑**，然后在**音频会议**窗格中，选择**收费电话号码**和**免费电话**号码列表中的一个数字。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="d8a0f-165">如果需要更多详细信息，请参阅[将 Microsoft 指定为音频会议提供商](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="d8a0f-166">第 8 步：设置会议邀请（可选）</span><span class="sxs-lookup"><span data-stu-id="d8a0f-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="d8a0f-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="d8a0f-167"></span></span>
 
<span data-ttu-id="d8a0f-168">为用户设置的电话拨入式号码将自动添加到发送给会议与会者的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="d8a0f-169">但是，您可以添加您自己的帮助和法律链接、 短信和小公司图形，如果您希望。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="d8a0f-170">请参阅[自定义会议邀请](customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a0f-170">See [Customize meeting invitations](customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="d8a0f-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="d8a0f-171">Related topics</span></span>

[<span data-ttu-id="d8a0f-172">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="d8a0f-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="d8a0f-173">Microsoft Teams 中用于音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="d8a0f-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="d8a0f-174">设置在线会议和会议电话的选项</span><span class="sxs-lookup"><span data-stu-id="d8a0f-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
