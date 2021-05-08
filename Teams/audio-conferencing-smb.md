---
title: 中小型企业设置音频会议
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
description: '了解如何在中小型企业中为需要使用电话呼叫加入会议的人设置音频会议。 '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122346"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="7b560-103">中小型企业设置音频会议</span><span class="sxs-lookup"><span data-stu-id="7b560-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="7b560-104">使用音频会议，用户可以使用电话Teams会议，而不是使用Teams或计算机中的音频会议应用。</span><span class="sxs-lookup"><span data-stu-id="7b560-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="7b560-105">如果你是一家拥有多达 300 名用户的小型企业或中型企业，并且当前没有任何音频会议许可证，你可以免费获得音频会议一年。</span><span class="sxs-lookup"><span data-stu-id="7b560-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="7b560-106">此免费产品/服务从 2020 年 10 月 1 日起提供。</span><span class="sxs-lookup"><span data-stu-id="7b560-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="7b560-107">音频会议附加许可证可应用于具有 Microsoft 365 商业基础版、Business Standard、Business 高级版、Enterprise E1 或 Enterprise E3 许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="7b560-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="7b560-108">有关详细信息，请参阅Teams[附加许可证](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="7b560-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="7b560-109">如果你拥有Enterprise E5 或 Microsoft 365 商务语音，你将不能使用免费的音频会议优惠，因为这些许可证已包含音频会议。</span><span class="sxs-lookup"><span data-stu-id="7b560-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="7b560-110">本文将介绍如何设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="7b560-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="7b560-111">你只需为打算安排或主持会议的人设置音频会议。</span><span class="sxs-lookup"><span data-stu-id="7b560-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="7b560-112">呼叫参加会议的会议与会者不需要许可证或其他设置。</span><span class="sxs-lookup"><span data-stu-id="7b560-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="7b560-113">若要了解有关详细信息，请参阅 [音频会议](audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7b560-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="7b560-114">设置音频会议</span><span class="sxs-lookup"><span data-stu-id="7b560-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="7b560-115">设置音频会议时，电话号码会自动分配给会议网桥，以便可用于会议邀请。</span><span class="sxs-lookup"><span data-stu-id="7b560-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="7b560-116">被分配为会议网桥默认号码的电话号码将是你组织的一个或多个国家/地区的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="7b560-117">此电话号码是收费电话号码，可能会收取长途费用。</span><span class="sxs-lookup"><span data-stu-id="7b560-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="7b560-118">您也可以使用免费电话号码，这需要额外的几个步骤。</span><span class="sxs-lookup"><span data-stu-id="7b560-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="7b560-119">若要详细了解会议网桥的电话号码 [，请参阅本文](#audio-conferencing-phone-numbers) 稍后的音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="7b560-120">步骤 1：获取音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="7b560-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="7b560-121">为将引导会议的每个人获取一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="7b560-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="7b560-122">使用Microsoft 365管理中心进行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b560-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="7b560-123">在Microsoft 365管理中心，转到"**计费** 购买服务"，然后在页面底部选择"  >  **附加内容"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="7b560-124">选择 **Microsoft 365音频会议采用促销**  >  **详细信息"，** 然后选择"**现在获取"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="7b560-125">输入会议组织者所需的许可证数，然后完成订单。</span><span class="sxs-lookup"><span data-stu-id="7b560-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="音频会议采用促销许可证的屏幕截图":::

    > [!NOTE]
    > <span data-ttu-id="7b560-127">清除或选择 **"自动分配给** 没有许可证的所有用户"，具体取决于是否要自动向没有此许可证的所有用户分配音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="7b560-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="7b560-128">步骤 2：向引导会议的用户分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="7b560-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="7b560-129">为将参加会议的每个人分配许可证。</span><span class="sxs-lookup"><span data-stu-id="7b560-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="7b560-130">使用Microsoft 365管理中心进行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b560-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="7b560-131">向一个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="7b560-131">Assign a license to one user</span></span>

1. <span data-ttu-id="7b560-132">在Microsoft 365中心，转到"用户  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="7b560-133">选择要为其分配许可证的用户的行，然后在窗格中选择"许可证 **和应用"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="7b560-134">选中 **"Microsoft 365音频会议**"复选框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="7b560-135">向多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="7b560-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="7b560-136">在Microsoft 365中心，转到"用户  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="7b560-137">选择要为其分配许可证的用户旁边的圆圈，然后选择"**管理产品许可证"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="7b560-138">在"**管理产品许可证"窗格中**，选择"**分配更多"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="7b560-139">选中 **"Microsoft 365音频会议**"复选框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="7b560-140">在 Teams 中安排Outlook</span><span class="sxs-lookup"><span data-stu-id="7b560-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="7b560-141">现在，会议组织者可以在会议中安排Outlook。</span><span class="sxs-lookup"><span data-stu-id="7b560-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="7b560-142">在Outlook中，转到 **"日历"，** 然后选择"新建Teams **会议**"按钮。</span><span class="sxs-lookup"><span data-stu-id="7b560-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="7b560-143">会议拨入号码和会议 ID 将自动添加到发送给会议与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="7b560-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="7b560-144">若要了解有关详细信息，请参阅[在 Outlook 中安排Teams会议](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。</span><span class="sxs-lookup"><span data-stu-id="7b560-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="7b560-145">如果需要，可以自定义会议邀请以添加公司徽标、指向支持网站和法律免责声明的链接以及纯文本页脚。</span><span class="sxs-lookup"><span data-stu-id="7b560-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="7b560-146">有关详细信息，请参阅 [自定义会议邀请](meeting-settings-in-teams.md#customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="7b560-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="7b560-147">音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="7b560-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="7b560-148">有两种类型的号码可用于会议网桥。</span><span class="sxs-lookup"><span data-stu-id="7b560-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="7b560-149">你可以 **像本文前面** (音频会议"部分一样使用 [](#set-up-audio-conferencing)共享号码或) **号码**。</span><span class="sxs-lookup"><span data-stu-id="7b560-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="7b560-150">下面是有关每个项的更多信息。</span><span class="sxs-lookup"><span data-stu-id="7b560-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="7b560-151">共享号码</span><span class="sxs-lookup"><span data-stu-id="7b560-151">Shared numbers</span></span>

<span data-ttu-id="7b560-152">共享号码是在所有组织中共享的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="7b560-153">共享号码是收费号码，在设置音频会议时会自动分配。</span><span class="sxs-lookup"><span data-stu-id="7b560-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="7b560-154">若要查看分配给会议网桥的默认号码，在 Microsoft Teams 管理中心的左侧导航中，转到"会议网桥"，然后找到离你最近位置  >  **的** 号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="7b560-155">专用号码</span><span class="sxs-lookup"><span data-stu-id="7b560-155">Dedicated numbers</span></span>

<span data-ttu-id="7b560-156">专用号码是一个仅可供用户使用的号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="7b560-157">专用号码可以是收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="7b560-158">要使用专用号码，您必须首先获取号码，将其分配给会议网桥，然后将号码分配给将参加会议的每个人。</span><span class="sxs-lookup"><span data-stu-id="7b560-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="7b560-159">有多种方式可以获取专用号码。</span><span class="sxs-lookup"><span data-stu-id="7b560-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="7b560-160">可以从 Microsoft 获取号码， (将) 现有号码转移到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7b560-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="7b560-161">若要详细了解如何执行此操作，请参阅获取 [服务编号](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="7b560-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="7b560-162">请记住，如果使用免费电话号码，则首先需要向将参加会议的每个人分配通信信用额度许可证。</span><span class="sxs-lookup"><span data-stu-id="7b560-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="7b560-163">有关详细信息，请参阅 [为组织设置通信信用额度](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="7b560-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="7b560-164">获得号码后，将其分配给会议网桥。</span><span class="sxs-lookup"><span data-stu-id="7b560-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="7b560-165">使用Microsoft Teams管理中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b560-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="7b560-166">在管理中心左侧导航Microsoft Teams，转到 **"会议**  >  **会议网桥"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="7b560-167">选择 **"添加**"，然后选择"**收费电话号码**"或 **"免费电话号码"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="7b560-168">在"**添加电话号码"窗格中**，选择号码，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="7b560-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="7b560-169">然后，将号码分配给将参加会议的每个人。</span><span class="sxs-lookup"><span data-stu-id="7b560-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="7b560-170">使用Microsoft Teams管理中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b560-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="7b560-171">在管理中心的左侧导航Microsoft Teams，选择"用户"，单击显示名称，然后选择"编辑 **"。** </span><span class="sxs-lookup"><span data-stu-id="7b560-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="7b560-172">选择 **"** 音频会议"**旁边的**"编辑"，然后在"音频会议"窗格中，在"收费电话号码"或"免费电话号码"列表中选择一个数字，然后选择"应用 **"。** </span><span class="sxs-lookup"><span data-stu-id="7b560-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b560-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b560-173">Related topics</span></span>

- [<span data-ttu-id="7b560-174">音频会议</span><span class="sxs-lookup"><span data-stu-id="7b560-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="7b560-175">为会议设置音频Teams</span><span class="sxs-lookup"><span data-stu-id="7b560-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="7b560-176">音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="7b560-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="7b560-177">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="7b560-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="7b560-178">获取服务编号</span><span class="sxs-lookup"><span data-stu-id="7b560-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="7b560-179">Teams 附加许可许可证</span><span class="sxs-lookup"><span data-stu-id="7b560-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="7b560-180">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="7b560-180">Assign licenses to users</span></span>](/microsoft-365/admin/manage/assign-licenses-to-users)