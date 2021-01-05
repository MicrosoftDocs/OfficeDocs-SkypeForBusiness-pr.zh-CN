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
ms.openlocfilehash: 361122f4411f6aa3621d030a7a0569b438a86c27
ms.sourcegitcommit: 7c6a9e851d2fbf055d15e681e367d9dceee0b917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2021
ms.locfileid: "49751786"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="ad59e-103">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="ad59e-103">Set up an auto attendant</span></span>

<span data-ttu-id="ad59e-104">自动助理可让你的人呼叫你的组织并导航菜单系统以与正确的部门、呼叫队列、人员或接线员通话。</span><span class="sxs-lookup"><span data-stu-id="ad59e-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="ad59e-105">可以使用 Microsoft Teams 管理中心或 PowerShell 为组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="ad59e-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="ad59e-106">在按照本文中的过程操作之前，请确保已阅读["Teams](plan-auto-attendant-call-queue.md)自动助理计划[](plan-auto-attendant-call-queue.md#getting-started)"和"呼叫队列"，并遵循了入门步骤。</span><span class="sxs-lookup"><span data-stu-id="ad59e-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="ad59e-107">自动助理可以基于呼叫者的输入将呼叫直接路由到以下目标之一： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="ad59e-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="ad59e-108">**组织中的人** - 组织中能够接收语音呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="ad59e-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="ad59e-109">这可以是联机用户，或者是使用 Skype for Business Server 在本地托管的用户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="ad59e-110">**语音应用** - 另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="ad59e-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="ad59e-111"> (选择此目标时与自动助理或呼叫队列关联的资源帐户。) </span><span class="sxs-lookup"><span data-stu-id="ad59e-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="ad59e-112">**外部电话号码** - 任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad59e-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="ad59e-113"> (外部[传输技术详细信息) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="ad59e-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="ad59e-114">**语音邮件** - 与指定的 Microsoft 365 组关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="ad59e-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="ad59e-115">**运算符** - 为自动助理定义的接线员。</span><span class="sxs-lookup"><span data-stu-id="ad59e-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="ad59e-116">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="ad59e-116">Defining an operator is optional.</span></span> <span data-ttu-id="ad59e-117">可以将运算符定义为此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="ad59e-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="ad59e-118">设置自动助理时，系统会提示你选择各个阶段中的其中一个选项。</span><span class="sxs-lookup"><span data-stu-id="ad59e-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="ad59e-119">若要设置自动助理，请在 Teams 管理中心展开 **"** 语音"，单击"自动助理"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="ad59e-120">常规信息</span><span class="sxs-lookup"><span data-stu-id="ad59e-120">General info</span></span>

![姓名、接线员、时区、语言和语音输入的自动助理设置的屏幕截图](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="ad59e-122">在顶部的框中键入自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="ad59e-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="ad59e-123">如果要指定一个运算符，请指定调用该运算符的目标。</span><span class="sxs-lookup"><span data-stu-id="ad59e-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="ad59e-124">这是可选的 (，但建议) 。</span><span class="sxs-lookup"><span data-stu-id="ad59e-124">This is optional (but recommended).</span></span> <span data-ttu-id="ad59e-125">你可以设置 **"接线** 员"选项，允许呼叫者离开菜单并联系指定的人员。</span><span class="sxs-lookup"><span data-stu-id="ad59e-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="ad59e-126">指定此自动助理的时区。</span><span class="sxs-lookup"><span data-stu-id="ad59e-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="ad59e-127">如果为营业时间创建单独的呼叫流，则时区用于 [计算营业时间](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="ad59e-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="ad59e-128">为此自动助理指定语言。</span><span class="sxs-lookup"><span data-stu-id="ad59e-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="ad59e-129">此语言将用于系统生成的语音提示。</span><span class="sxs-lookup"><span data-stu-id="ad59e-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="ad59e-130">选择是否要启用语音输入。</span><span class="sxs-lookup"><span data-stu-id="ad59e-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="ad59e-131">启用后，每个菜单选项的名称将成为语音识别关键字。</span><span class="sxs-lookup"><span data-stu-id="ad59e-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="ad59e-132">例如，呼叫者可以说"一"来选择映射到键 1 的菜单选项，也可以说"销售"以选择名为"销售"的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="ad59e-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="ad59e-133">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ad59e-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="ad59e-134">呼叫流</span><span class="sxs-lookup"><span data-stu-id="ad59e-134">Call flow</span></span>

![问候消息设置的屏幕截图](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="ad59e-136">选择当自动助理应答呼叫时是否要播放问候语。</span><span class="sxs-lookup"><span data-stu-id="ad59e-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="ad59e-137">如果选择"**播放音频文件"，** 可以使用"上传文件"按钮上传保存为音频的录制问候消息。WAV， .MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="ad59e-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="ad59e-138">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="ad59e-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="ad59e-139">如果选择"键入问候语"消息，系统将在自动助理应答呼叫时朗读你键入 (最多 1000) 的文本。</span><span class="sxs-lookup"><span data-stu-id="ad59e-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![呼叫路由设置的屏幕截图](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="ad59e-141">选择要如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad59e-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="ad59e-142">如果选择" **断开连接"，** 自动助理将挂断呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad59e-142">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="ad59e-143">如果选择" **重定向呼叫"，** 可以选择其中一个呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="ad59e-143">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="ad59e-144">如果选择"**播放"菜单选项**，可选择"播放音频文件"或"键入问候语"，然后在菜单选项和目录搜索之间选择。</span><span class="sxs-lookup"><span data-stu-id="ad59e-144">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="ad59e-145">菜单选项</span><span class="sxs-lookup"><span data-stu-id="ad59e-145">Menu options</span></span>

![拨号键选项的屏幕截图](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="ad59e-147">对于拨号选项，可以将电话键盘上的 0-9 键分配给呼叫路由目标之一。</span><span class="sxs-lookup"><span data-stu-id="ad59e-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="ad59e-148"> (系统 (重复)  (后退) 键由系统保留，不能重新分配 \* \# 。) </span><span class="sxs-lookup"><span data-stu-id="ad59e-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="ad59e-149">键映射不必是连续的。</span><span class="sxs-lookup"><span data-stu-id="ad59e-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="ad59e-150">例如，可以创建将键 0、1 和 3 映射到选项的菜单，而使用 2 键。</span><span class="sxs-lookup"><span data-stu-id="ad59e-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="ad59e-151">如果已配置 0 密钥，建议将 0 密钥映射到操作员。</span><span class="sxs-lookup"><span data-stu-id="ad59e-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="ad59e-152">如果接线员未设置为任何键，则语音命令"接线员"也将被禁用。</span><span class="sxs-lookup"><span data-stu-id="ad59e-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="ad59e-153">对于每个菜单选项，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="ad59e-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="ad59e-154">**拨号键** - 电话键盘上的按键，用于访问此选项。</span><span class="sxs-lookup"><span data-stu-id="ad59e-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="ad59e-155">如果语音输入可用，呼叫者也可以说出此号码来访问该选项。</span><span class="sxs-lookup"><span data-stu-id="ad59e-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="ad59e-156">**语音** 命令 - 定义呼叫者可以授予用于访问此选项的语音命令（如果启用了语音输入）。</span><span class="sxs-lookup"><span data-stu-id="ad59e-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="ad59e-157">它可以包含多个单词，例如"客户服务"或"运营与企业"。</span><span class="sxs-lookup"><span data-stu-id="ad59e-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="ad59e-158">例如，调用方可以按 2，说"两"或说"销售"以选择映射到 2 键的选项。</span><span class="sxs-lookup"><span data-stu-id="ad59e-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="ad59e-159">此文本还通过文本转语音呈现，供服务确认提示使用，该提示可能类似"将呼叫转接到销售"。</span><span class="sxs-lookup"><span data-stu-id="ad59e-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="ad59e-160">**重定向到** - 呼叫方选择此选项时使用的呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="ad59e-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="ad59e-161">如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="ad59e-162">目录搜索</span><span class="sxs-lookup"><span data-stu-id="ad59e-162">Directory search</span></span>

<span data-ttu-id="ad59e-163">如果将拨号键分配给目标，建议为"目录搜索"选择"**无"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="ad59e-164">如果呼叫者尝试使用分配给特定目的地的键拨打名称或分机号码，他们可能会意外地路由到目标，然后他们完成输入姓名或分机号码。</span><span class="sxs-lookup"><span data-stu-id="ad59e-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="ad59e-165">建议为目录搜索创建单独的自动助理，然后通过拨号键将主要自动助理链接至该助理。</span><span class="sxs-lookup"><span data-stu-id="ad59e-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="ad59e-166">如果未分配拨号键，请选择用于 **目录搜索的选项**。</span><span class="sxs-lookup"><span data-stu-id="ad59e-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="ad59e-167">**按名称拨** 叫 - 如果启用此选项，呼叫者可以说出用户的姓名或在电话键盘上键入它。</span><span class="sxs-lookup"><span data-stu-id="ad59e-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="ad59e-168">任何联机用户或任何使用 Skype for Business Server 在本地托管的用户都是符合条件的用户，可通过按名字拨叫找到。</span><span class="sxs-lookup"><span data-stu-id="ad59e-168">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="ad59e-169"> (你可以设置"拨号范围"页上的目录中包括和不包括[哪些人) ](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="ad59e-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="ad59e-170">**按分机拨号** - 如果启用此选项，呼叫者可以通过拨打其电话分机来与贵组织的用户联系。</span><span class="sxs-lookup"><span data-stu-id="ad59e-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="ad59e-171">任何联机用户或任何使用 Skype for Business Server 在本地托管的用户都是符合条件的用户，可通过分机 **号拨叫找到**。</span><span class="sxs-lookup"><span data-stu-id="ad59e-171">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="ad59e-172"> (你可以设置"拨号范围"页上的目录中包括和不包括[哪些人) ](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="ad59e-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="ad59e-173">要使其可用于"按分机拨号"的用户需要具有一个指定为 Active Directory 或 Azure Active Directory 中定义的以下电话属性之一的一部分的扩展 ([](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)请参阅"单独或批量添加用户"了解详细信息。) </span><span class="sxs-lookup"><span data-stu-id="ad59e-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="ad59e-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="ad59e-174">OfficePhone</span></span>
- <span data-ttu-id="ad59e-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="ad59e-175">HomePhone</span></span>
- <span data-ttu-id="ad59e-176">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="ad59e-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="ad59e-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="ad59e-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="ad59e-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="ad59e-178">OtherTelephone</span></span>

<span data-ttu-id="ad59e-179">在"用户电话号码"字段中输入分机号码所需的格式为：</span><span class="sxs-lookup"><span data-stu-id="ad59e-179">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="ad59e-180">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="ad59e-180">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="ad59e-181">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="ad59e-181">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="ad59e-182">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="ad59e-182">*x\<extension>*</span></span>

- <span data-ttu-id="ad59e-183">示例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="ad59e-183">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="ad59e-184">示例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="ad59e-184">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="ad59e-185">示例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="ad59e-185">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="ad59e-186">可以在 [Microsoft 365](https://admin.microsoft.com/) 管理中心或 [Azure Active Directory](https://aad.portal.azure.com)管理中心设置扩展。</span><span class="sxs-lookup"><span data-stu-id="ad59e-186">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="ad59e-187">最多可能需要 12 小时，更改才可供自动助理和呼叫队列使用。</span><span class="sxs-lookup"><span data-stu-id="ad59e-187">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="ad59e-188">如果要同时使用按名字拨叫和按分机拨叫功能，可以在主自动助理上分配拨号键，以联系为按名字拨叫启用的自动 **助理**。</span><span class="sxs-lookup"><span data-stu-id="ad59e-188">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="ad59e-189">在此自动助理中，你可以分配 1 个键 (没有与之关联的字母，) 通过分机自动助理联系拨号。 </span><span class="sxs-lookup"><span data-stu-id="ad59e-189">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="ad59e-190">选择目录 **搜索选项后**，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-190">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="ad59e-191">营业时间的呼叫流</span><span class="sxs-lookup"><span data-stu-id="ad59e-191">Call flow for after hours</span></span>

!["小时之后"的"天"和"时间"设置的屏幕截图](media/auto-attendant-business-hours.png)

<span data-ttu-id="ad59e-193">可以针对每个自动助理设置营业时间。</span><span class="sxs-lookup"><span data-stu-id="ad59e-193">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="ad59e-194">如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。</span><span class="sxs-lookup"><span data-stu-id="ad59e-194">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="ad59e-195">可以设置营业时间，同时设置一天中的休息时间，所有未设置为营业时间的营业时间均视为非工作时间。</span><span class="sxs-lookup"><span data-stu-id="ad59e-195">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="ad59e-196">您可以为非营业时间设置不同的传入呼叫处理选项和问候语。</span><span class="sxs-lookup"><span data-stu-id="ad59e-196">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="ad59e-197">根据自动助理和呼叫队列的配置方式，可能只需为具有直接电话号码的自动助理指定非营业时间呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="ad59e-197">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="ad59e-198">如果希望为非营业时间呼叫者单独路由呼叫，请指定每天的营业时间。</span><span class="sxs-lookup"><span data-stu-id="ad59e-198">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="ad59e-199">例如 **，单击"** 添加新时间"以指定给定天的多个小时数集，以指定午餐休息时间。</span><span class="sxs-lookup"><span data-stu-id="ad59e-199">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="ad59e-200">指定营业时间后，请选择数小时的呼叫路由选项。</span><span class="sxs-lookup"><span data-stu-id="ad59e-200">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="ad59e-201">提供的选项与上面指定的营业时间呼叫路由相同。</span><span class="sxs-lookup"><span data-stu-id="ad59e-201">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="ad59e-202">完成后 **单击** "下一步"。</span><span class="sxs-lookup"><span data-stu-id="ad59e-202">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="ad59e-203">假日期间呼叫流</span><span class="sxs-lookup"><span data-stu-id="ad59e-203">Call flows during holidays</span></span>

![节日和节日问候语设置的屏幕截图](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="ad59e-205">自动助理可以针对你设置的每个假日 [设置呼叫流](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ad59e-205">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="ad59e-206">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="ad59e-206">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="ad59e-207">在"假日呼叫设置"页上，单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-207">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="ad59e-208">键入此假日设置的名称。</span><span class="sxs-lookup"><span data-stu-id="ad59e-208">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="ad59e-209">从 **"假日** "下拉列表中，选择想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="ad59e-209">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="ad59e-210">选择想要使用的问候语类型。</span><span class="sxs-lookup"><span data-stu-id="ad59e-210">Choose the type of greeting that you want to use.</span></span>

    ![节日呼叫操作设置的屏幕截图](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="ad59e-212">选择是否要断开连接 **或\*\*\*\*重定向** 呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad59e-212">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="ad59e-213">如果选择重定向，请选择呼叫的呼叫路由目标。</span><span class="sxs-lookup"><span data-stu-id="ad59e-213">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="ad59e-214">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ad59e-214">Click **Save**.</span></span>

![假日设置的屏幕截图，其中列出了假日](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="ad59e-216">根据需要对每个额外的假日重复该过程。</span><span class="sxs-lookup"><span data-stu-id="ad59e-216">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="ad59e-217">添加所有假日后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-217">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="ad59e-218">拨号范围</span><span class="sxs-lookup"><span data-stu-id="ad59e-218">Dial scope</span></span>

![拨号范围包括和排除选项的屏幕截图](media/auto-attendant-dial-scope.png)

<span data-ttu-id="ad59e-220">拨号 *范围* 定义当呼叫者使用按名字拨叫或按分机拨叫时，哪些用户在目录中可用。</span><span class="sxs-lookup"><span data-stu-id="ad59e-220">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="ad59e-221">默认情况下 **，"所有联机用户** "包括组织中使用 Skype for Business Server 联机用户或本地托管的所有用户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-221">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="ad59e-222">可以通过在"包括"或"排除"下选择"自定义用户组"并选择一个或多个 Microsoft 365 组、通讯组列表或安全组来包括或排除特定用户。 </span><span class="sxs-lookup"><span data-stu-id="ad59e-222">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="ad59e-223">例如，你可能希望从拨号目录中排除贵组织的高层。</span><span class="sxs-lookup"><span data-stu-id="ad59e-223">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="ad59e-224"> (如果用户同时在两个列表中，则他们将被排除在 directory.) </span><span class="sxs-lookup"><span data-stu-id="ad59e-224">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="ad59e-225">新用户可能需要最多 36 小时才能在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="ad59e-225">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="ad59e-226">设置完拨号范围后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-226">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="ad59e-227">资源帐户</span><span class="sxs-lookup"><span data-stu-id="ad59e-227">Resource accounts</span></span>

<span data-ttu-id="ad59e-228">所有自动助理必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-228">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="ad59e-229">第一级自动助理至少需要一个具有关联服务编号的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-229">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="ad59e-230">如果需要，可以将多个资源帐户分配给自动助理，每个帐户都有单独的服务编号。</span><span class="sxs-lookup"><span data-stu-id="ad59e-230">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![资源帐户"添加帐户"面板的屏幕截图](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="ad59e-232">若要添加资源帐户，请单击 **"添加帐户** "并搜索要添加的帐户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-232">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="ad59e-233">单击 **"添加**"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-233">Click **Add**, and then click **Add**.</span></span>

![显示具有已分配服务编号的资源帐户的资源帐户列表的屏幕截图](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="ad59e-235">添加完服务帐户后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="ad59e-235">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="ad59e-236">这会完成自动助理配置。</span><span class="sxs-lookup"><span data-stu-id="ad59e-236">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="ad59e-237">外部电话号码转移 - 技术详细信息</span><span class="sxs-lookup"><span data-stu-id="ad59e-237">External phone number transfers - technical details</span></span>

<span data-ttu-id="ad59e-238">请参阅先决条件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以便自动助理在外部转接呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad59e-238">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="ad59e-239">另外：</span><span class="sxs-lookup"><span data-stu-id="ad59e-239">In addition:</span></span>

- <span data-ttu-id="ad59e-240">对于具有呼叫计划号码的资源[](calling-plans-for-office-365.md)帐户，必须以 E.164 格式输入外部转移电话号码 (+[国家/地区代码][区号][电话号码]) 。</span><span class="sxs-lookup"><span data-stu-id="ad59e-240">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="ad59e-241">对于具有直接路由号码的资源帐户，外部传输电话号码格式依赖于会话边界控制器 ([SBC) ](direct-routing-connect-the-sbc.md) 设置。</span><span class="sxs-lookup"><span data-stu-id="ad59e-241">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="ad59e-242">显示的出站电话号码按如下所示确定：</span><span class="sxs-lookup"><span data-stu-id="ad59e-242">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="ad59e-243">对于呼叫计划号码，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad59e-243">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="ad59e-244">对于直接路由号码，发送的数字基于 SBC 上的 P-Asserted-Identity (PAI) 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad59e-244">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="ad59e-245">如果设置为"禁用"，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad59e-245">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="ad59e-246">这是默认的推荐设置。</span><span class="sxs-lookup"><span data-stu-id="ad59e-246">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="ad59e-247">如果设置为"已启用"，将显示资源帐户电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad59e-247">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="ad59e-248">在 Skype for Business 混合环境中，若要将自动助理呼叫转接到 PSTN，请创建呼叫转接设置为 PSTN 号码的新本地用户。</span><span class="sxs-lookup"><span data-stu-id="ad59e-248">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="ad59e-249">必须为用户启用语音企业语音并分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="ad59e-249">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="ad59e-250">若要了解有关详细信息，请参阅"[自动助理呼叫转接到 PSTN"。](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="ad59e-250">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="ad59e-251">使用 PowerShell 创建自动助理</span><span class="sxs-lookup"><span data-stu-id="ad59e-251">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="ad59e-252">也可使用 PowerShell 创建和设置自动助理。</span><span class="sxs-lookup"><span data-stu-id="ad59e-252">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="ad59e-253">下面是管理自动助理所需的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ad59e-253">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="ad59e-254">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ad59e-254">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="ad59e-255">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ad59e-255">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="ad59e-256">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ad59e-256">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="ad59e-257">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="ad59e-257">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="ad59e-258">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="ad59e-258">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="ad59e-259">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="ad59e-259">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="ad59e-260">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="ad59e-260">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="ad59e-261">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="ad59e-261">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="ad59e-262">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="ad59e-262">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="ad59e-263">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="ad59e-263">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="ad59e-264">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="ad59e-264">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="ad59e-265">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="ad59e-265">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="ad59e-266">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="ad59e-266">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="ad59e-267">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="ad59e-267">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="ad59e-268">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="ad59e-268">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="ad59e-269">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="ad59e-269">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="ad59e-270">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="ad59e-270">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="ad59e-271">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad59e-271">Related topics</span></span>

[<span data-ttu-id="ad59e-272">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="ad59e-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="ad59e-273">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="ad59e-273">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="ad59e-274">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="ad59e-274">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="ad59e-275">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="ad59e-275">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="ad59e-276">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="ad59e-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
