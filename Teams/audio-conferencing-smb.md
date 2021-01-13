---
title: 为中小型企业设置音频会议
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
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
description: '了解如何在小型企业或中型企业中为需要使用电话呼叫加入会议的人设置音频会议。 '
ms.openlocfilehash: 80e372e62ffdac9907521eb9426b465c9d0b6e92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821282"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="da6cb-103">为中小型企业设置音频会议</span><span class="sxs-lookup"><span data-stu-id="da6cb-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="da6cb-104">使用音频会议，用户可以使用电话呼入 Teams 会议，而不是使用移动设备上或计算机中的 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="da6cb-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="da6cb-105">如果你是一家拥有多达 300 名用户的小型企业或中型企业，并且当前没有任何音频会议许可证，则你可以免费使用音频会议一年。</span><span class="sxs-lookup"><span data-stu-id="da6cb-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="da6cb-106">此免费产品/服务从 2020 年 10 月 1 日起提供。</span><span class="sxs-lookup"><span data-stu-id="da6cb-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="da6cb-107">音频会议附加许可证可应用于具有 Microsoft 365 商业版基本版、商业标准版、商业高级版、企业版 E1 或企业版 E3 许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="da6cb-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="da6cb-108">若要了解更多信息，请参阅 [Teams 附加许可证](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="da6cb-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="da6cb-109">如果你有企业版 E5 或 Microsoft 365 商业语音，你将不能使用免费的音频会议产品/服务，因为这些许可证已包含音频会议。</span><span class="sxs-lookup"><span data-stu-id="da6cb-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="da6cb-110">本文将演练如何设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="da6cb-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="da6cb-111">你只需为打算安排或主持会议的人设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="da6cb-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="da6cb-112">呼叫参加会议的与会者不需要许可证或其他设置。</span><span class="sxs-lookup"><span data-stu-id="da6cb-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="da6cb-113">若要了解有关详细信息，请参阅["音频会议"。](audio-conferencing-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="da6cb-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="da6cb-114">设置音频会议</span><span class="sxs-lookup"><span data-stu-id="da6cb-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="da6cb-115">设置音频会议时，电话号码将自动分配给你的会议网桥，以便它可以用于会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="da6cb-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="da6cb-116">分配为会议网桥默认号码的电话号码将是你组织的一个或多个国家/地区的电话号码。</span><span class="sxs-lookup"><span data-stu-id="da6cb-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="da6cb-117">此电话号码是收费电话号码，可能会收取远程费用。</span><span class="sxs-lookup"><span data-stu-id="da6cb-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="da6cb-118">您也可以使用免费电话号码，这需要额外的几个步骤。</span><span class="sxs-lookup"><span data-stu-id="da6cb-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="da6cb-119">若要详细了解会议网桥的电话号码，请参阅本文稍后的"音频会议[](#audio-conferencing-phone-numbers)"电话号码。</span><span class="sxs-lookup"><span data-stu-id="da6cb-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="da6cb-120">步骤 1：获取音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="da6cb-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="da6cb-121">为将参加会议的每个人获取一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="da6cb-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="da6cb-122">使用 Microsoft 365 管理中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="da6cb-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="da6cb-123">在 Microsoft 365 管理中心，转到"计费购买服务"，然后在页面底部选择  >  **"附加内容"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="da6cb-124">选择 **Microsoft 365 音频会议采用** 促销  >  **详细信息**，然后选择"获取 **"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="da6cb-125">输入会议组织者所需的许可证数，然后完成订单。</span><span class="sxs-lookup"><span data-stu-id="da6cb-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="音频会议采用促销许可证的屏幕截图":::

    > [!NOTE]
    > <span data-ttu-id="da6cb-127">清除或选择"自动分配给没有许可证的所有用户"，具体取决于是否要自动为没有此许可证的所有用户分配音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="da6cb-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="da6cb-128">步骤 2：向负责会议的用户分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="da6cb-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="da6cb-129">为将参加会议的每个人分配许可证。</span><span class="sxs-lookup"><span data-stu-id="da6cb-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="da6cb-130">使用 Microsoft 365 管理中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="da6cb-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="da6cb-131">向一个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="da6cb-131">Assign a license to one user</span></span>

1. <span data-ttu-id="da6cb-132">在 Microsoft 365 管理中心，转到 **"用户**  >  **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="da6cb-133">选择要为其分配许可证的用户的行，然后在窗格中选择"许可证 **和应用"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="da6cb-134">选中 **"Microsoft 365 音频会议**"复选框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="da6cb-135">向多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="da6cb-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="da6cb-136">在 Microsoft 365 管理中心，转到 **"用户**  >  **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="da6cb-137">选择要为其分配许可证的用户旁边的圆圈，然后选择"管理 **产品许可证"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="da6cb-138">在"**管理产品许可证"窗格中**，选择"**分配更多"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="da6cb-139">选中 **"Microsoft 365 音频会议**"复选框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="da6cb-140">在 Outlook 中安排 Teams 会议</span><span class="sxs-lookup"><span data-stu-id="da6cb-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="da6cb-141">现在，会议组织者可以在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="da6cb-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="da6cb-142">在 Outlook 中，转到 **"日历**"，然后选择" **新建 Teams 会议"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="da6cb-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="da6cb-143">会议拨入号码和会议 ID 将自动添加到发送给会议与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="da6cb-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="da6cb-144">若要了解有关详细信息，请参阅 [在 Outlook 中安排 Teams 会议](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。</span><span class="sxs-lookup"><span data-stu-id="da6cb-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="da6cb-145">如果需要，可以自定义会议邀请以添加公司徽标、指向支持网站的链接和法律免责声明以及纯文本页脚。</span><span class="sxs-lookup"><span data-stu-id="da6cb-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="da6cb-146">若要了解有关详细信息，请参阅"[自定义会议邀请"。](meeting-settings-in-teams.md#customize-meeting-invitations)</span><span class="sxs-lookup"><span data-stu-id="da6cb-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="da6cb-147">音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="da6cb-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="da6cb-148">有两种类型的号码可用于会议网桥。</span><span class="sxs-lookup"><span data-stu-id="da6cb-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="da6cb-149">你可以像本文前面 (音频会议部分一样使用共享 [](#set-up-audio-conferencing)号码或) **号码**。</span><span class="sxs-lookup"><span data-stu-id="da6cb-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="da6cb-150">下面是每个项的更多信息。</span><span class="sxs-lookup"><span data-stu-id="da6cb-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="da6cb-151">共享号码</span><span class="sxs-lookup"><span data-stu-id="da6cb-151">Shared numbers</span></span>

<span data-ttu-id="da6cb-152">共享号码是在所有组织之间共享的电话号码。</span><span class="sxs-lookup"><span data-stu-id="da6cb-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="da6cb-153">共享号码是收费号码，在设置音频会议时自动分配。</span><span class="sxs-lookup"><span data-stu-id="da6cb-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="da6cb-154">若要查看分配给会议网桥的默认号码，在 Microsoft Teams 管理中心的左侧导航栏中，转到"会议网桥"，然后找到离你最近的位置的号码。  >  </span><span class="sxs-lookup"><span data-stu-id="da6cb-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="da6cb-155">专用号码</span><span class="sxs-lookup"><span data-stu-id="da6cb-155">Dedicated numbers</span></span>

<span data-ttu-id="da6cb-156">专用号码是一个仅可供用户使用的号码。</span><span class="sxs-lookup"><span data-stu-id="da6cb-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="da6cb-157">专用号码可以是收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="da6cb-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="da6cb-158">要使用专用号码，您必须首先获取号码，将其分配给会议网桥，然后将号码分配给将参加会议的每个人。</span><span class="sxs-lookup"><span data-stu-id="da6cb-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="da6cb-159">有两种方法可以获取专用号码。</span><span class="sxs-lookup"><span data-stu-id="da6cb-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="da6cb-160">可以从 Microsoft 获取号码， (将) 现有号码从当前服务提供商转移到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="da6cb-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="da6cb-161">若要详细了解如何执行此操作，请参阅"获取[服务编号"。](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="da6cb-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="da6cb-162">请记住，如果使用免费电话号码，首先必须为每个将参加会议的人分配通信信用额度许可证。</span><span class="sxs-lookup"><span data-stu-id="da6cb-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="da6cb-163">若要了解有关详细信息，请参阅["为组织设置通信信用额度"。](set-up-communications-credits-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="da6cb-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="da6cb-164">获得号码后，将其分配给会议网桥。</span><span class="sxs-lookup"><span data-stu-id="da6cb-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="da6cb-165">使用 Microsoft Teams 管理中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="da6cb-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="da6cb-166">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **网桥"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="da6cb-167">选择 **"** 添加"，然后选择收费 **电话号码** 或 **免费电话号码**。</span><span class="sxs-lookup"><span data-stu-id="da6cb-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="da6cb-168">在"**添加电话号码"窗格中**，选择号码，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="da6cb-169">然后，将号码分配给将参加会议的每个人。</span><span class="sxs-lookup"><span data-stu-id="da6cb-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="da6cb-170">使用 Microsoft Teams 管理中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="da6cb-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="da6cb-171">在 Microsoft Teams 管理中心的左侧导航中，选择"用户"，单击显示名称，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="da6cb-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="da6cb-172">选择 **"** 音频会议"旁边的"编辑"，然后在"音频会议"窗格中，在收费号码或免费号码列表中选择一个数字，然后选择"应用 **"。** </span><span class="sxs-lookup"><span data-stu-id="da6cb-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da6cb-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="da6cb-173">Related topics</span></span>

- [<span data-ttu-id="da6cb-174">音频会议</span><span class="sxs-lookup"><span data-stu-id="da6cb-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="da6cb-175">为 Teams 设置音频会议</span><span class="sxs-lookup"><span data-stu-id="da6cb-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="da6cb-176">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="da6cb-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="da6cb-177">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="da6cb-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="da6cb-178">获取服务编号</span><span class="sxs-lookup"><span data-stu-id="da6cb-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="da6cb-179">Teams 附加许可证</span><span class="sxs-lookup"><span data-stu-id="da6cb-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="da6cb-180">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="da6cb-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
