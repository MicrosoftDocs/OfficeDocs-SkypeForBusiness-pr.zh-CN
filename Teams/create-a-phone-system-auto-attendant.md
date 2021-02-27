---
title: 为 Microsoft Teams 设置自动助理
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 了解如何为 Microsoft Teams 设置和测试自动助理。
ms.openlocfilehash: deb9bf013136bb8efd9171e5562de5e2ba1b631f
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347863"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="ed32b-103">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="ed32b-103">Set up an auto attendant</span></span>

<span data-ttu-id="ed32b-104">自动助理可让你的人呼叫你的组织并导航菜单系统，以与正确的部门、呼叫队列、人员或接线员通话。</span><span class="sxs-lookup"><span data-stu-id="ed32b-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="ed32b-105">可以使用 Microsoft Teams 管理中心或 PowerShell 为组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="ed32b-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="ed32b-106">在按照本文中的过程操作之前，请确保已阅读[Teams](plan-auto-attendant-call-queue.md)自动助理和[](plan-auto-attendant-call-queue.md#getting-started)呼叫队列的计划，并按照入门步骤操作。</span><span class="sxs-lookup"><span data-stu-id="ed32b-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="ed32b-107">自动助理可以基于呼叫者的输入将呼叫直接路由到以下目标之一： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="ed32b-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="ed32b-108">**运算符** - 为自动助理定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="ed32b-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="ed32b-109">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="ed32b-109">Defining an operator is optional.</span></span> <span data-ttu-id="ed32b-110">可以将运算符定义为此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="ed32b-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="ed32b-111">**组织成员** - 组织中可接收语音呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="ed32b-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="ed32b-112">这可以是联机用户，或者是使用 Skype for Business Server 在本地托管的用户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-112">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="ed32b-113">**语音应用** - 另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="ed32b-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="ed32b-114"> (选择此目标时，请选择与自动助理或呼叫队列关联的资源帐户) </span><span class="sxs-lookup"><span data-stu-id="ed32b-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="ed32b-115">**语音邮件** - 与指定的 Microsoft 365 组关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="ed32b-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="ed32b-116">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="ed32b-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="ed32b-117"> (外部[传输技术详细信息) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="ed32b-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="ed32b-118">**公告** - 播放音频文件。</span><span class="sxs-lookup"><span data-stu-id="ed32b-118">**Announcement** - Play an audio file.</span></span> <span data-ttu-id="ed32b-119">你上载的已录制公告消息，已另存为音频。WAV， .MP3 或 .WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="ed32b-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="ed32b-120">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="ed32b-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="ed32b-121">系统播放公告，然后返回到自动助理菜单。</span><span class="sxs-lookup"><span data-stu-id="ed32b-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="ed32b-122">**公告** - 键入消息。</span><span class="sxs-lookup"><span data-stu-id="ed32b-122">**Announcement** - Type in a message.</span></span> <span data-ttu-id="ed32b-123">希望系统阅读的文本。</span><span class="sxs-lookup"><span data-stu-id="ed32b-123">Text you want the system to read.</span></span> <span data-ttu-id="ed32b-124">可以输入最多 1000 个字符。</span><span class="sxs-lookup"><span data-stu-id="ed32b-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="ed32b-125">系统播放公告，然后返回到自动助理菜单。</span><span class="sxs-lookup"><span data-stu-id="ed32b-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="ed32b-126">设置自动助理时，系统会提示你选择不同阶段的其中一个选项。</span><span class="sxs-lookup"><span data-stu-id="ed32b-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="ed32b-127">若要设置自动助理，请在 Teams 管理中心展开 **"** 语音"，选择"自动助理"，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-127">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="ed32b-128">常规信息</span><span class="sxs-lookup"><span data-stu-id="ed32b-128">General info</span></span>

![姓名、接线员、时区、语言和语音输入的自动助理设置的屏幕截图](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="ed32b-130">在顶部的框中键入自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="ed32b-130">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="ed32b-131">如果要指定操作员，请指定对接线员的调用的目标。</span><span class="sxs-lookup"><span data-stu-id="ed32b-131">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="ed32b-132">此选项是可选的， (建议) 。</span><span class="sxs-lookup"><span data-stu-id="ed32b-132">This is optional (but recommended).</span></span> <span data-ttu-id="ed32b-133">您可以设置 **"接线员** "选项，以允许呼叫者离开菜单并与指定人员通话。</span><span class="sxs-lookup"><span data-stu-id="ed32b-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="ed32b-134">指定此自动助理的时区。</span><span class="sxs-lookup"><span data-stu-id="ed32b-134">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="ed32b-135">如果为营业时间创建单独的呼叫流，则时区 [用于计算营业时间](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="ed32b-135">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="ed32b-136">为此 [自动助理指定](create-a-phone-system-auto-attendant-languages.md) 支持的语言。</span><span class="sxs-lookup"><span data-stu-id="ed32b-136">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="ed32b-137">这是将用于系统生成的语音提示的语言。</span><span class="sxs-lookup"><span data-stu-id="ed32b-137">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="ed32b-138">选择是否要启用语音输入。</span><span class="sxs-lookup"><span data-stu-id="ed32b-138">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="ed32b-139">启用后，每个菜单选项的名称将成为语音识别关键字。</span><span class="sxs-lookup"><span data-stu-id="ed32b-139">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="ed32b-140">例如，呼叫者可以说"一"来选择映射到键 1 的菜单选项，也可以说"销售"以选择名为"销售"的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="ed32b-140">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="ed32b-141">如果在步骤 4 中选择不支持语音输入的语言，此选项将被禁用。</span><span class="sxs-lookup"><span data-stu-id="ed32b-141">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="ed32b-142">选择 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-142">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="ed32b-143">呼叫流</span><span class="sxs-lookup"><span data-stu-id="ed32b-143">Call flow</span></span>

![问候消息设置的屏幕截图](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="ed32b-145">选择当自动助理应答呼叫时是否要播放问候语。</span><span class="sxs-lookup"><span data-stu-id="ed32b-145">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="ed32b-146">如果选择"**播放音频文件"，** 可以使用"上传文件"按钮上传保存为音频的录制问候消息。WAV， .MP3 或 .WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="ed32b-146">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="ed32b-147">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="ed32b-147">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="ed32b-148">如果选择"键入问候语"消息，系统将在自动助理应答呼叫时 (最多 1000 个字符) 您键入的文本。</span><span class="sxs-lookup"><span data-stu-id="ed32b-148">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![呼叫路由设置的屏幕截图](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="ed32b-150">选择要如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="ed32b-150">Choose how you want to route the call.</span></span>

<span data-ttu-id="ed32b-151">如果选择" **断开连接"，** 自动助理将挂断呼叫。</span><span class="sxs-lookup"><span data-stu-id="ed32b-151">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="ed32b-152">如果选择" **重定向呼叫"，** 可以选择其中一个呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="ed32b-152">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="ed32b-153">如果选择"**播放"菜单选项**，可以选择播放音频文件或键入问候语，然后在菜单选项和目录搜索之间选择。</span><span class="sxs-lookup"><span data-stu-id="ed32b-153">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="ed32b-154">菜单选项</span><span class="sxs-lookup"><span data-stu-id="ed32b-154">Menu options</span></span>

![拨号键选项的屏幕截图](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="ed32b-156">对于拨号选项，可以将电话键盘上的 0-9 键分配给呼叫路由目标之一。</span><span class="sxs-lookup"><span data-stu-id="ed32b-156">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="ed32b-157"> (系统 (重复) 和 (后退) 键由系统保留，不能重新分配 \* \# 。) </span><span class="sxs-lookup"><span data-stu-id="ed32b-157">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="ed32b-158">键映射不必是连续的。</span><span class="sxs-lookup"><span data-stu-id="ed32b-158">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="ed32b-159">例如，可以创建一个菜单，其中键 0、1 和 3 映射到选项，而未使用这两个键。</span><span class="sxs-lookup"><span data-stu-id="ed32b-159">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the two key isn't used.</span></span>

<span data-ttu-id="ed32b-160">建议将零键映射到运算符（如果已配置）。</span><span class="sxs-lookup"><span data-stu-id="ed32b-160">We recommend mapping the zero key to the operator if you have configured one.</span></span> <span data-ttu-id="ed32b-161">如果接线员未设置为任何键，则语音命令"接线员"也将被禁用。</span><span class="sxs-lookup"><span data-stu-id="ed32b-161">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="ed32b-162">对于每个菜单选项，请指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="ed32b-162">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="ed32b-163">**拨号键** - 电话键盘上的按键，用于访问此选项。</span><span class="sxs-lookup"><span data-stu-id="ed32b-163">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="ed32b-164">如果语音输入可用，呼叫者也可以说出此号码来访问该选项。</span><span class="sxs-lookup"><span data-stu-id="ed32b-164">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="ed32b-165">**语音** 命令 - 定义呼叫者可以授予的语音命令来访问此选项（如果启用了语音输入）。</span><span class="sxs-lookup"><span data-stu-id="ed32b-165">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="ed32b-166">它可以包含多个字词，例如"客户服务"或"运营与订单"。</span><span class="sxs-lookup"><span data-stu-id="ed32b-166">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="ed32b-167">例如，调用方可以按 2、说"两个"或说"销售"以选择映射到两个键的选项。</span><span class="sxs-lookup"><span data-stu-id="ed32b-167">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two key.</span></span> <span data-ttu-id="ed32b-168">此文本还呈现为服务确认提示的文本转语音，该提示可能类似"将呼叫转接到销售"。</span><span class="sxs-lookup"><span data-stu-id="ed32b-168">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="ed32b-169">**重定向到** - 呼叫方选择此选项时使用的呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="ed32b-169">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="ed32b-170">如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-170">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="ed32b-171">目录搜索</span><span class="sxs-lookup"><span data-stu-id="ed32b-171">Directory search</span></span>

<span data-ttu-id="ed32b-172">如果将拨号键分配到目标，建议为"目录搜索 **"选择"无\*\*\*\*"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-172">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="ed32b-173">如果呼叫者尝试使用分配给特定目的地的键拨打名称或分机号码，则他们可能会意外路由到目标，然后他们完成输入姓名或分机号码。</span><span class="sxs-lookup"><span data-stu-id="ed32b-173">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="ed32b-174">建议为目录搜索创建单独的自动助理，通过拨号键将主要自动助理链接至它。</span><span class="sxs-lookup"><span data-stu-id="ed32b-174">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="ed32b-175">如果未分配拨号键，请为目录搜索 **选择一个选项**。</span><span class="sxs-lookup"><span data-stu-id="ed32b-175">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="ed32b-176">**按姓名** 拨叫 - 如果启用此选项，呼叫者可以说出用户的姓名或在电话键盘上键入。</span><span class="sxs-lookup"><span data-stu-id="ed32b-176">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="ed32b-177">任何在线用户或任何使用 Skype for Business Server 在本地托管的用户都是符合条件的用户，可以使用"按名字拨叫"找到。</span><span class="sxs-lookup"><span data-stu-id="ed32b-177">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="ed32b-178"> (你可以设置"拨号范围"页上的目录中包括和不包括 [哪些](#dial-scope) 人) </span><span class="sxs-lookup"><span data-stu-id="ed32b-178">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="ed32b-179">**按分机** 拨打 - 如果启用此选项，呼叫者可以通过拨打其电话分机来与贵组织的用户联系。</span><span class="sxs-lookup"><span data-stu-id="ed32b-179">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="ed32b-180">任何在线用户或任何使用 Skype for Business Server 在本地托管的用户都是符合条件的用户，可通过分机 **号拨叫找到**。</span><span class="sxs-lookup"><span data-stu-id="ed32b-180">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="ed32b-181"> (你可以设置"拨号范围"页上的目录中包括和不包括 [哪些](#dial-scope) 人) </span><span class="sxs-lookup"><span data-stu-id="ed32b-181">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="ed32b-182">要使其可用于"按分机拨号"的用户需要具有在 Active Directory 或 Azure Active Directory 中定义的以下电话属性之一的一部分指定的分机 (有关详细信息[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)，请参阅"单独或批量添加用户"。) </span><span class="sxs-lookup"><span data-stu-id="ed32b-182">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="ed32b-183">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="ed32b-183">OfficePhone</span></span>
- <span data-ttu-id="ed32b-184">HomePhone</span><span class="sxs-lookup"><span data-stu-id="ed32b-184">HomePhone</span></span>
- <span data-ttu-id="ed32b-185">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="ed32b-185">Mobile/MobilePhone</span></span>
- <span data-ttu-id="ed32b-186">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="ed32b-186">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="ed32b-187">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="ed32b-187">OtherTelephone</span></span>

<span data-ttu-id="ed32b-188">在用户电话号码字段中输入分机号码所需的格式为：</span><span class="sxs-lookup"><span data-stu-id="ed32b-188">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="ed32b-189">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="ed32b-189">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="ed32b-190">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="ed32b-190">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="ed32b-191">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="ed32b-191">*x\<extension>*</span></span>

- <span data-ttu-id="ed32b-192">示例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="ed32b-192">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="ed32b-193">示例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="ed32b-193">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="ed32b-194">示例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="ed32b-194">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="ed32b-195">可以在 [Microsoft 365](https://admin.microsoft.com/) 管理中心或 [Azure Active Directory](https://aad.portal.azure.com)管理中心设置扩展。</span><span class="sxs-lookup"><span data-stu-id="ed32b-195">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="ed32b-196">最多可能需要 12 小时才能对自动助理和呼叫队列进行更改。</span><span class="sxs-lookup"><span data-stu-id="ed32b-196">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="ed32b-197">如果要同时使用"按名字拨叫"和"按分机拨叫"功能，可以在主自动助理上分配拨号键，以联系为按名字拨叫启用的自动 **助理**。</span><span class="sxs-lookup"><span data-stu-id="ed32b-197">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="ed32b-198">在自动助理中，你可以分配 1 个键 (没有与之关联的字母) 分机 **自动** 助理。</span><span class="sxs-lookup"><span data-stu-id="ed32b-198">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="ed32b-199">选择目录 **搜索选项后**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-199">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="ed32b-200">营业时间的呼叫流</span><span class="sxs-lookup"><span data-stu-id="ed32b-200">Call flow for after hours</span></span>

!["工作时间"的"天"和"时间"设置的屏幕截图](media/auto-attendant-business-hours.png)

<span data-ttu-id="ed32b-202">可以针对每个自动助理设置营业时间。</span><span class="sxs-lookup"><span data-stu-id="ed32b-202">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="ed32b-203">如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。</span><span class="sxs-lookup"><span data-stu-id="ed32b-203">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="ed32b-204">可以设置营业时间，同时设置一天中的休息时间，所有未设置为营业时间的营业时间都被视为非营业时间。</span><span class="sxs-lookup"><span data-stu-id="ed32b-204">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="ed32b-205">您可以为非营业时间设置不同的传入呼叫处理选项和问候语。</span><span class="sxs-lookup"><span data-stu-id="ed32b-205">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="ed32b-206">根据自动助理和呼叫队列的配置方式，可能只需为具有直接电话号码的自动助理指定非营业时间呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="ed32b-206">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="ed32b-207">如果希望为非营业时间呼叫者单独进行呼叫路由，请指定每天的营业时间。</span><span class="sxs-lookup"><span data-stu-id="ed32b-207">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="ed32b-208">例如 **，选择"添加新** 时间"以指定给定日的多个小时集，以指定午餐休息时间。</span><span class="sxs-lookup"><span data-stu-id="ed32b-208">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="ed32b-209">指定营业时间后，选择营业时间的呼叫路由选项。</span><span class="sxs-lookup"><span data-stu-id="ed32b-209">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="ed32b-210">提供的选项与上面指定的营业时间呼叫路由相同。</span><span class="sxs-lookup"><span data-stu-id="ed32b-210">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="ed32b-211">完成后 **选择** "下一步"。</span><span class="sxs-lookup"><span data-stu-id="ed32b-211">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="ed32b-212">假日期间呼叫流</span><span class="sxs-lookup"><span data-stu-id="ed32b-212">Call flows during holidays</span></span>

![节日和节日问候语设置的屏幕截图](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="ed32b-214">自动助理可以针对你设置的每个假日 [设置呼叫流](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ed32b-214">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="ed32b-215">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="ed32b-215">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="ed32b-216">在假日呼叫设置页上，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-216">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="ed32b-217">键入此假日设置的名称。</span><span class="sxs-lookup"><span data-stu-id="ed32b-217">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="ed32b-218">从 **"假日** "下拉列表中，选择想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="ed32b-218">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="ed32b-219">选择想要使用的问候语类型。</span><span class="sxs-lookup"><span data-stu-id="ed32b-219">Choose the type of greeting that you want to use.</span></span>

    ![假日呼叫操作设置的屏幕截图](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="ed32b-221">选择是断开 **呼叫还是\*\*\*\*重定向** 呼叫。</span><span class="sxs-lookup"><span data-stu-id="ed32b-221">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="ed32b-222">如果选择重定向，请选择呼叫的呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="ed32b-222">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="ed32b-223">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-223">Select **Save**.</span></span>

![列出假日的假日设置的屏幕截图](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="ed32b-225">根据需要对每个额外的假日重复该过程。</span><span class="sxs-lookup"><span data-stu-id="ed32b-225">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="ed32b-226">添加所有假日后，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-226">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="ed32b-227">拨号范围</span><span class="sxs-lookup"><span data-stu-id="ed32b-227">Dial scope</span></span>

![拨号范围包括和排除选项的屏幕截图](media/auto-attendant-dial-scope.png)

<span data-ttu-id="ed32b-229">拨号 *范围* 定义当呼叫者使用按名称拨叫或按分机拨叫时，哪些用户在目录中可用。</span><span class="sxs-lookup"><span data-stu-id="ed32b-229">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="ed32b-230">默认情况下 **，"所有联机用户** "包括组织中使用 Skype for Business Server 联机用户或本地托管的所有用户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-230">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="ed32b-231">可以通过在"包括"或"排除"下选择"自定义"用户组并选择一个或多个 Microsoft 365 组、通讯组列表或安全组来包括或排除特定用户。 </span><span class="sxs-lookup"><span data-stu-id="ed32b-231">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="ed32b-232">例如，你可能希望从拨号目录中排除组织中高层。</span><span class="sxs-lookup"><span data-stu-id="ed32b-232">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="ed32b-233"> (如果用户同时位于这两个列表中，他们将被排除在 directory.) </span><span class="sxs-lookup"><span data-stu-id="ed32b-233">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="ed32b-234">新用户可能需要最多 36 小时才能在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="ed32b-234">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="ed32b-235">设置完拨号范围后，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-235">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="ed32b-236">资源帐户</span><span class="sxs-lookup"><span data-stu-id="ed32b-236">Resource accounts</span></span>

<span data-ttu-id="ed32b-237">所有自动助理必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="ed32b-238">一级自动助理至少需要一个具有关联服务编号的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-238">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="ed32b-239">如果需要，可以将多个资源帐户分配给自动助理，每个帐户都有单独的服务编号。</span><span class="sxs-lookup"><span data-stu-id="ed32b-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![资源帐户添加帐户面板的屏幕截图](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="ed32b-241">若要添加资源帐户，请选择 **"添加帐户** "，然后搜索要添加的帐户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-241">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="ed32b-242">选择 **"添加**"，然后选择"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="ed32b-242">Select **Add**, and then select **Add**.</span></span>

![显示具有已分配服务编号的资源帐户的资源帐户列表的屏幕截图](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="ed32b-244">添加完服务帐户后，选择 **"提交** "以完成自动助理配置。</span><span class="sxs-lookup"><span data-stu-id="ed32b-244">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="ed32b-245">外部电话号码转移 - 技术详细信息</span><span class="sxs-lookup"><span data-stu-id="ed32b-245">External phone number transfers - technical details</span></span>

<span data-ttu-id="ed32b-246">请参阅 [先决条件，](plan-auto-attendant-call-queue.md#prerequisites) 以便允许自动助理在外部转移呼叫。</span><span class="sxs-lookup"><span data-stu-id="ed32b-246">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="ed32b-247">另外：</span><span class="sxs-lookup"><span data-stu-id="ed32b-247">In addition:</span></span>

- <span data-ttu-id="ed32b-248">对于具有呼叫计划号码的资源[](calling-plans-for-office-365.md)帐户，必须以 E.164 格式输入外部转移电话号码 (+[国家/地区代码][区号][电话号码]) 。</span><span class="sxs-lookup"><span data-stu-id="ed32b-248">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="ed32b-249">对于具有直接路由号码的资源帐户，外部传输电话号码格式取决于会话边界控制器 ([SBC) ](direct-routing-connect-the-sbc.md) 设置。</span><span class="sxs-lookup"><span data-stu-id="ed32b-249">For a resource account with a Direct Routing number, the external transfer phone number format is dependent on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="ed32b-250">显示的出站电话号码按如下所示确定：</span><span class="sxs-lookup"><span data-stu-id="ed32b-250">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="ed32b-251">对于呼叫计划号码，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ed32b-251">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="ed32b-252">对于直接路由号码，发送的数字基于 SBC 上的 P-Asserted-Identity (PAI) 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed32b-252">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="ed32b-253">如果设置为"已禁用"，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ed32b-253">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="ed32b-254">这是默认设置，也是建议的设置。</span><span class="sxs-lookup"><span data-stu-id="ed32b-254">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="ed32b-255">如果设置为"已启用"，将显示资源帐户电话号码。</span><span class="sxs-lookup"><span data-stu-id="ed32b-255">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="ed32b-256">在 Skype for Business 混合环境中，若要将自动助理呼叫转接到 PSTN，请创建呼叫转接设置为 PSTN 号码的新本地用户。</span><span class="sxs-lookup"><span data-stu-id="ed32b-256">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="ed32b-257">必须为用户启用语音企业语音并分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="ed32b-257">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="ed32b-258">若要了解有关详细信息，请参阅"[自动助理呼叫转接到 PSTN"。](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="ed32b-258">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="ed32b-259">使用 PowerShell 创建自动助理</span><span class="sxs-lookup"><span data-stu-id="ed32b-259">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="ed32b-260">也可使用 PowerShell 创建和设置自动助理。</span><span class="sxs-lookup"><span data-stu-id="ed32b-260">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="ed32b-261">下面是管理自动助理所需的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed32b-261">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="ed32b-262">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ed32b-262">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="ed32b-263">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ed32b-263">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="ed32b-264">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ed32b-264">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="ed32b-265">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="ed32b-265">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="ed32b-266">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ed32b-266">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="ed32b-267">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="ed32b-267">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="ed32b-268">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="ed32b-268">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="ed32b-269">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="ed32b-269">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="ed32b-270">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="ed32b-270">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="ed32b-271">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="ed32b-271">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="ed32b-272">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="ed32b-272">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="ed32b-273">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="ed32b-273">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="ed32b-274">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="ed32b-274">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="ed32b-275">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="ed32b-275">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="ed32b-276">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="ed32b-276">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="ed32b-277">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="ed32b-277">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="ed32b-278">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="ed32b-278">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="ed32b-279">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed32b-279">Related topics</span></span>

[<span data-ttu-id="ed32b-280">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="ed32b-280">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="ed32b-281">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="ed32b-281">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="ed32b-282">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="ed32b-282">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="ed32b-283">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="ed32b-283">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
