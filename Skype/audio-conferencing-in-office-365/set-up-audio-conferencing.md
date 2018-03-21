---
title: "设置音频会议 for Skype Business 和 Microsoft 团队"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: fd427abf14d3d705bc9f846f32a27d9be62967e8
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="810d7-103">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="810d7-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="810d7-104">有时，组织中的用户需要使用电话拨入会议。</span><span class="sxs-lookup"><span data-stu-id="810d7-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="810d7-105">Skype 业务和 Microsoft 小组包括音频会议功能，只是这种情况 ！</span><span class="sxs-lookup"><span data-stu-id="810d7-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="810d7-106">人们可以在调用到 Skype 使用电话，而不使用 Skype 业务或 Microsoft 小组在移动设备或 PC 上的应用程序的业务或 Microsoft 小组会议。</span><span class="sxs-lookup"><span data-stu-id="810d7-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="810d7-107">您只需设置音频会议的计划安排或会导致会议的人员。</span><span class="sxs-lookup"><span data-stu-id="810d7-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="810d7-108">拨入的会议与会者无需分配给它们或其他设置的任何许可证。</span><span class="sxs-lookup"><span data-stu-id="810d7-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="810d7-109">常见问题及解答有关音频会议，请参阅[音频会议的常见问题的解决方案](audio-conferencing-common-questions.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="810d7-110">第 1 步：购买和分配许可证</span><span class="sxs-lookup"><span data-stu-id="810d7-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="810d7-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="810d7-111"></span></span>

<span data-ttu-id="810d7-112">您必须是[有关 Office 365 管理角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="810d7-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="810d7-113">查找 Office 365 中的音频会议是否提供您所在国家/地区。</span><span class="sxs-lookup"><span data-stu-id="810d7-113">Find out if Audio Conferencing in Office 365 is available in your country/region.</span></span> <span data-ttu-id="810d7-114">[音频会议和调用计划的国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-114">[Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="810d7-115">了解所需的音频会议，并且将花费多少购买的许可证。</span><span class="sxs-lookup"><span data-stu-id="810d7-115">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost.</span></span> <span data-ttu-id="810d7-116">请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)，并购买许可证。</span><span class="sxs-lookup"><span data-stu-id="810d7-116">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="810d7-117">[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)分配给贵组织中打算安排或主持会议的人。</span><span class="sxs-lookup"><span data-stu-id="810d7-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="810d7-118">如果您购买**音频会议**附加许可和通信片尾许可证，将太对它们进行分配。</span><span class="sxs-lookup"><span data-stu-id="810d7-118">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="810d7-119">有关说明，请参见[业务和 Microsoft 小组许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-119">For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="810d7-120">步骤 2： 确定您的音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="810d7-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="810d7-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="810d7-121"></span></span>

<span data-ttu-id="810d7-122">音频会议提供商提供*音频会议桥*。</span><span class="sxs-lookup"><span data-stu-id="810d7-122">An audio conferencing provider supplies an *audio conferencing bridge*.</span></span> <span data-ttu-id="810d7-123">会议桥设置您拨入电话号码、 针，并为会议的会议 Id。</span><span class="sxs-lookup"><span data-stu-id="810d7-123">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="810d7-124">决定是否使用 Microsoft 或第三方音频会议提供商：</span><span class="sxs-lookup"><span data-stu-id="810d7-124">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="810d7-125">Microsoft 小组用户用户的第三方音频会议提供商则不能。</span><span class="sxs-lookup"><span data-stu-id="810d7-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="810d7-126">**Microsoft 为您的音频会议提供商**： 如果希望将最简单的解决方案的音频会议，选择 Microsoft 为您的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="810d7-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="810d7-127">**第三方音频会议提供商为**： 如果您是在国家 Office 365 中的音频会议不可用，由于它的位置，服务质量不好或有现有的合同中，选择第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="810d7-127">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="810d7-128">若要查找提供程序，请转到[Microsoft 查明其](http://go.microsoft.com/fwlink/?LinkId=797530)。</span><span class="sxs-lookup"><span data-stu-id="810d7-128">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="810d7-129">在您的组织中，您可以使用 Microsoft 作为其音频会议提供商中，一些人和其他人使用第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="810d7-129">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="810d7-130">但这会为您设置和管理更加复杂。</span><span class="sxs-lookup"><span data-stu-id="810d7-130">But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="810d7-131">Microsoft 为您的音频提供商和第三方提供商之间的详细比较，请参见[比较音频会议提供商](compare-audio-conferencing-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="810d7-132">步骤 3： 将音频会议提供商分配给潜在客户或安排会议的人</span><span class="sxs-lookup"><span data-stu-id="810d7-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="810d7-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="810d7-133"></span></span>

<span data-ttu-id="810d7-134">既然您决定在您的音频会议提供商，您需要将该提供程序分配给组织中的人员，领导或安排会议。</span><span class="sxs-lookup"><span data-stu-id="810d7-134">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="810d7-135">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="810d7-135">Do one of the following:</span></span> 
  
- <span data-ttu-id="810d7-136">[作为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="810d7-137">[指定音频会议提供商作为第三方](assign-a-third-party-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="810d7-138">步骤 4： 设置会议邀请</span><span class="sxs-lookup"><span data-stu-id="810d7-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="810d7-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="810d7-139"></span></span>

<span data-ttu-id="810d7-140">以下步骤是**可选**的但大量的管理员要做这些：</span><span class="sxs-lookup"><span data-stu-id="810d7-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="810d7-141">[自定义会议邀请](../set-up-skype-for-business-online/customize-meeting-invitations.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-141">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span> <span data-ttu-id="810d7-142">为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="810d7-142">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="810d7-143">但是，您可以添加您自己的帮助和法律链接、 文本消息和小型公司的图形。</span><span class="sxs-lookup"><span data-stu-id="810d7-143">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="810d7-144">[音频会议电话号码为会议组织者邀请中包含的一组](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-144">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> <span data-ttu-id="810d7-145">这是由用户计划的会议中将会显示的电话号码。</span><span class="sxs-lookup"><span data-stu-id="810d7-145">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="810d7-146">[设置自动助理语言音频会议的](set-auto-attendant-languages-for-audio-conferencing.md)音频会议自动助理用来招呼呼叫者当他们到音频会议电话号码拨入。</span><span class="sxs-lookup"><span data-stu-id="810d7-146">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="810d7-147">如果您使用 Microsoft 为您的音频提供商，此步骤才适用。</span><span class="sxs-lookup"><span data-stu-id="810d7-147">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="810d7-148">[设置音频会议的会议的 PIN 的长度](set-the-pin-length-for-audio-conferencing-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="810d7-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="810d7-149">此功能尚未提供给客户使用 Office 365 由 21Vianet 在中国。</span><span class="sxs-lookup"><span data-stu-id="810d7-149">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="810d7-150">若要了解详细信息，请参阅[关于由 21Vianet Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。</span><span class="sxs-lookup"><span data-stu-id="810d7-150">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="810d7-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="810d7-151">Related topics</span></span>

[<span data-ttu-id="810d7-152">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="810d7-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="810d7-153">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="810d7-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="810d7-154">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="810d7-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="810d7-155">设置选项用于联机会议和电话会议</span><span class="sxs-lookup"><span data-stu-id="810d7-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

