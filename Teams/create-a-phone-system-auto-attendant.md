---
title: 为 Microsoft 团队设置自动助理
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
description: 了解如何为 Microsoft 团队设置和测试自动助理。
ms.openlocfilehash: 1d19483fe458c38d01a9c46c982101eeab6546c2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033020"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="7fcf3-103">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="7fcf3-103">Set up an auto attendant</span></span>

<span data-ttu-id="7fcf3-104">自动助理允许用户呼叫你的组织，并导航菜单系统以与右部门通话、呼叫队列、人员或操作员。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="7fcf3-105">你可以通过 Microsoft 团队管理中心或通过 PowerShell 为你的组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="7fcf3-106">请确保你拥有 [团队自动助理和呼叫队列](plan-auto-attendant-call-queue.md) 的阅读计划，然后按照本文中的步骤操作，然后按照 [入门步骤](plan-auto-attendant-call-queue.md#getting-started) 操作。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="7fcf3-107">自动助理可根据呼叫者的输入将呼叫定向到以下目的地之一： <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="7fcf3-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="7fcf3-108">**组织中的人员** -您的组织中能够接收语音呼叫的人员。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="7fcf3-109">这可以是联机用户，也可以是使用 Skype for Business 服务器内部托管的用户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="7fcf3-110">**语音应用** -另一个自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="7fcf3-111"> (选择 "选择此目标时与自动助理或呼叫队列相关联的资源帐户"。 ) </span><span class="sxs-lookup"><span data-stu-id="7fcf3-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="7fcf3-112">**外部电话号码** -任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="7fcf3-113"> (参阅 [外部转接技术详细信息](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)) 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="7fcf3-114">**语音邮件** -与你指定的 Microsoft 365 组相关联的语音邮箱。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="7fcf3-115">**Operator** -为自动助理定义的操作员。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="7fcf3-116">定义运算符是可选的。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-116">Defining an operator is optional.</span></span> <span data-ttu-id="7fcf3-117">操作员可以定义为此列表中的任何其他目标。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="7fcf3-118">设置自动助理时，系统会提示你在各个阶段选择其中一个选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="7fcf3-119">若要设置自动助理，请在 "团队管理中心" 中，展开 " **语音** "，单击 " **自动助理** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-119">To set up an auto attendant, in the Teams admin center, expand **Voice** , click **Auto attendants** , and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="7fcf3-120">常规信息</span><span class="sxs-lookup"><span data-stu-id="7fcf3-120">General info</span></span>

![名称、操作员、时区、语言和语音输入的自动助理设置的屏幕截图](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="7fcf3-122">在顶部的框中键入自动助理的名称。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="7fcf3-123">如果要指定一个运算符，请指定调用该操作员的目标。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="7fcf3-124">这是可选的 (但建议) 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-124">This is optional (but recommended).</span></span> <span data-ttu-id="7fcf3-125">你可以将 " **操作员** " 选项设置为允许呼叫者跳出菜单，并向指定的人讲话。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="7fcf3-126">指定此自动助理的时区。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="7fcf3-127">如果您在 [下班后创建单独的通话流](#call-flow-for-after-hours)，则会使用时区计算营业时间。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="7fcf3-128">指定此自动助理的语言。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="7fcf3-129">此语言将用于系统生成的语音提示。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="7fcf3-130">选择是否要启用语音输入。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="7fcf3-131">启用后，每个菜单选项的名称将变为语音识别关键字。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="7fcf3-132">例如，呼叫者可以说 "One" 以选择映射到键1的菜单选项，或者说 "销售额" 以选择名为 "Sales" 的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="7fcf3-133">单击" **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="7fcf3-134">通话流</span><span class="sxs-lookup"><span data-stu-id="7fcf3-134">Call flow</span></span>

![问候邮件设置的屏幕截图](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="7fcf3-136">选择在自动助理接听呼叫时是否要播放问候语。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="7fcf3-137">如果选择 " **播放音频文件** "，你可以使用 " **上传文件** " 按钮上载另存为音频的录制问候语消息。WAV，。MP3 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="7fcf3-138">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="7fcf3-139">如果选择 " **键入问候语** "，系统将在自动助理接听呼叫时，读取您键入的文本 (最多为1000个字符的文本) 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![呼叫路由设置的屏幕截图](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="7fcf3-141">选择您希望路由呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="7fcf3-142">如果您选择 " **断开连接** "，自动助理将挂起呼叫。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-142">If you select **Disconnect** , the auto attendant will hang up the call.</span></span>

<span data-ttu-id="7fcf3-143">如果选择 " **重定向呼叫** "，则可以选择其中一个呼叫传送目的地。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-143">If you select **Redirect call** , you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="7fcf3-144">如果选择 " **播放菜单" 选项** ，则可以选择 **播放音频文件** 或 **键入问候语** ，然后在菜单选项和目录搜索之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-144">If you select **Play menu options** , you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="7fcf3-145">菜单选项</span><span class="sxs-lookup"><span data-stu-id="7fcf3-145">Menu options</span></span>

![拨号键选项的屏幕截图](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="7fcf3-147">对于拨号选项，您可以将电话键盘上的0-9 键分配给其中一个呼叫传送目的地。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="7fcf3-148"> (键 \* (重复) ， \# (后) 由系统保留，并且不能重新分配。 ) </span><span class="sxs-lookup"><span data-stu-id="7fcf3-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="7fcf3-149">键映射不必是连续的。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="7fcf3-150">例如，可以创建一个映射到选项的键为0、1和3的菜单，而不使用2键。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="7fcf3-151">如果已配置，我们建议将0键映射到操作员。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="7fcf3-152">如果运算符未设置为任何键，则语音命令 "Operator" 也会被禁用。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="7fcf3-153">对于每个菜单选项，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="7fcf3-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="7fcf3-154">" **拨号键** "-电话键盘上的键以访问此选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="7fcf3-155">如果语音输入可用，呼叫方还可以使用此号码访问该选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="7fcf3-156">**语音命令** -定义当语音输入已启用时，呼叫者可以提供的语音命令来访问此选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="7fcf3-157">它可以包含多个词语，如 "客户服务" 或 "操作和用户"。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="7fcf3-158">例如，呼叫者可以按2、说出 "二" 或说 "销售额" 以选择映射到2键的选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="7fcf3-159">此文本还会由用于服务确认提示的文本（如 "将您的呼叫转移到销售人员"）呈现为语音。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="7fcf3-160">**重定向至** -呼叫路由目标，当呼叫方选择此选项时使用。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="7fcf3-161">如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="7fcf3-162">目录搜索</span><span class="sxs-lookup"><span data-stu-id="7fcf3-162">Directory search</span></span>

<span data-ttu-id="7fcf3-163">如果为目的地分配了拨号键，我们建议您选择 " **无** " 进行 **目录搜索** 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="7fcf3-164">如果呼叫者尝试使用分配给特定目的地的密钥来拨打名称或分机，则它们可能会在完成输入名称或扩展名之前意外地路由到目标。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="7fcf3-165">我们建议你为目录搜索创建单独的自动助理，并让你的主自动助理通过拨号键链接到它。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="7fcf3-166">如果您没有分配拨号键，请选择 **目录搜索** 选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="7fcf3-167">**按名称拨号** -如果启用此选项，呼叫者可以说出用户的姓名或在电话键盘上键入它。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="7fcf3-168">任何带电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，可通过 "按名称拨号" 找到。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="7fcf3-169"> (你可以设置 " [拨号作用域](#dial-scope) " 页面上的目录中和未包含的人员。 ) </span><span class="sxs-lookup"><span data-stu-id="7fcf3-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="7fcf3-170">**按分机号码拨号** -如果启用此选项，则呼叫者可以通过拨打电话分机与您的组织中的用户联系。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="7fcf3-171">任何具有电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，并且可以 **通过 "通过分机拨入** " 找到。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="7fcf3-172"> (你可以设置 " [拨号作用域](#dial-scope) " 页面上的目录中和未包含的人员。 ) </span><span class="sxs-lookup"><span data-stu-id="7fcf3-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="7fcf3-173">希望可供拨号使用的用户需要将扩展指定为在 Active Directory 或 Azure Active Directory 中定义的以下某个电话属性的一部分 (请参阅 [单独或批量添加用户](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 以了解详细信息。 ) </span><span class="sxs-lookup"><span data-stu-id="7fcf3-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="7fcf3-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="7fcf3-174">OfficePhone</span></span>
- <span data-ttu-id="7fcf3-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="7fcf3-175">HomePhone</span></span>
- <span data-ttu-id="7fcf3-176">手机/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="7fcf3-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="7fcf3-177">TelephoneNumber/电话号码</span><span class="sxs-lookup"><span data-stu-id="7fcf3-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="7fcf3-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="7fcf3-178">OtherTelephone</span></span>

<span data-ttu-id="7fcf3-179">在 "用户电话号码" 字段中输入扩展名所需的格式为 *+ \<phone number> ext = \<extension>* 或 *+ \<phone number> x \<extension>* 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-179">The required format to enter the extension in the user phone number field is either *+\<phone number>ext=\<extension>* or *+\<phone number>x\<extension>*.</span></span>

<span data-ttu-id="7fcf3-180">你可以在 [Microsoft 365 管理中心](https://admin.microsoft.com/) 或 [Azure Active Directory 管理中心](https://aad.portal.azure.com)中设置扩展。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-180">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="7fcf3-181">在自动助理和呼叫队列中进行更改前，最多可能需要12小时。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-181">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="7fcf3-182">如果想要同时使用 " **按姓名** 拨号" 和 " **按分机号码拨号** " 功能，您可以在您的主自动助理上分配一个拨号键，以到达启用 " **按名称拨号** " 的自动助理。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-182">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="7fcf3-183">在该自动助理中，你可以分配一个没有与之关联的字母 (的键) **通过分机** 自动助理到达拨号。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-183">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="7fcf3-184">选择 **目录搜索** 选项后，单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-184">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="7fcf3-185">下班后的通话流程</span><span class="sxs-lookup"><span data-stu-id="7fcf3-185">Call flow for after hours</span></span>

![小时数天和时间设置的屏幕截图](media/auto-attendant-business-hours.png)

<span data-ttu-id="7fcf3-187">可以为每个自动助理设置工作时间。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-187">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="7fcf3-188">如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-188">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="7fcf3-189">可以在一天内通过休息时间设置工作时间，并且未设置为工作时间的所有小时都将被认为是在小时后。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-189">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="7fcf3-190">你可以设置不同的传入呼叫处理选项和问候语。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-190">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="7fcf3-191">根据您配置的自动助理和呼叫队列的方式，您可能只需为带有直接电话号码的自动助理指定 "时间后的呼叫路由"。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-191">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="7fcf3-192">如果需要在下班后呼叫者单独呼叫路由，请指定每天的工作时间。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-192">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="7fcf3-193">单击 " **添加新时间** " 以指定给定日期的多个小时集，例如，指定午餐休息时间。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-193">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="7fcf3-194">一旦您指定了您的工作时间，请选择下班后的呼叫路线选项。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-194">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="7fcf3-195">相同的选项可用于您在上面指定的工作时间呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-195">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="7fcf3-196">完成后，单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-196">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="7fcf3-197">假期期间的通话流</span><span class="sxs-lookup"><span data-stu-id="7fcf3-197">Call flows during holidays</span></span>

![节日和节日问候设置的屏幕截图](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="7fcf3-199">您的自动助理可以为 [您设置](set-up-holidays-in-teams.md)的每个假日提供一个呼叫流。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-199">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="7fcf3-200">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-200">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="7fcf3-201">在 "假日呼叫设置" 页面上，单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-201">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="7fcf3-202">键入此假日设置的名称。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-202">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="7fcf3-203">从 " **假日** " 下拉列表中，选择要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-203">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="7fcf3-204">选择要使用的问候语类型。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-204">Choose the type of greeting that you want to use.</span></span>

    ![节日呼叫操作设置的屏幕截图](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="7fcf3-206">选择是否要 **断开连接** 或 **重定向** 呼叫。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-206">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="7fcf3-207">如果您选择重定向，请选择呼叫的呼叫传送目的地。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-207">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="7fcf3-208">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-208">Click **Save**.</span></span>

![已列出假日设置的假日设置的屏幕截图](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="7fcf3-210">根据需要为每个额外的假日重复该过程。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-210">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="7fcf3-211">添加完所有假日后，单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-211">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="7fcf3-212">拨号作用域</span><span class="sxs-lookup"><span data-stu-id="7fcf3-212">Dial scope</span></span>

![拨入范围包括和排除选项的屏幕截图](media/auto-attendant-dial-scope.png)

<span data-ttu-id="7fcf3-214">当呼叫者使用按名称拨号或按扩展方式拨号时， *拨号作用域* 定义哪些用户在目录中可用。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-214">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="7fcf3-215">**所有联机用户** 的默认值包括您的组织中的所有用户，这些用户是使用电话系统许可证的联机用户或使用 Skype For business 服务器内部托管的用户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-215">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="7fcf3-216">通过选择 " **包含** " 或 " **排除** " 下的 " **自定义用户组** "，然后选择一个或多个 Microsoft 365 组、通讯组列表或安全组，可以包含或排除特定用户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-216">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="7fcf3-217">例如，您可能希望从 "拨号目录" 中将组织中的主管排除在您的组织中。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-217">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="7fcf3-218"> (如果用户在两个列表中，则会将其从目录中排除。 ) </span><span class="sxs-lookup"><span data-stu-id="7fcf3-218">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="7fcf3-219">新用户可能需要长达36小时才能在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-219">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="7fcf3-220">设置完拨号作用域后，单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-220">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="7fcf3-221">资源帐户</span><span class="sxs-lookup"><span data-stu-id="7fcf3-221">Resource accounts</span></span>

<span data-ttu-id="7fcf3-222">所有自动助理都必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-222">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="7fcf3-223">第一级自动助理至少需要一个具有关联服务号码的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-223">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="7fcf3-224">如果需要，您可以将多个资源帐户分配给自动助理，每个帐户都有一个单独的服务编号。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-224">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![资源帐户 "添加帐户" 面板的屏幕截图](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="7fcf3-226">若要添加资源帐户，请单击 " **添加帐户** "，然后搜索要添加的帐户。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-226">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="7fcf3-227">单击 " **添加** "，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-227">Click **Add** , and then click **Add**.</span></span>

![资源帐户列表的屏幕截图，显示分配的服务号码的资源帐户](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="7fcf3-229">添加完服务帐户后，单击 " **提交** "。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-229">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="7fcf3-230">这将完成自动助理配置。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-230">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="7fcf3-231">外部电话号码传输-技术详细信息</span><span class="sxs-lookup"><span data-stu-id="7fcf3-231">External phone number transfers - technical details</span></span>

<span data-ttu-id="7fcf3-232">请参考 [先决条件](plan-auto-attendant-call-queue.md#prerequisites) ，以便允许自动助理在外部转移呼叫。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-232">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="7fcf3-233">另外：</span><span class="sxs-lookup"><span data-stu-id="7fcf3-233">In addition:</span></span>

- <span data-ttu-id="7fcf3-234">对于带有 [呼叫计划](calling-plans-for-office-365.md) 编号的资源帐户，必须使用 E：164格式输入外部转帐电话号码 (+ [国家代码] [区号] [电话号码] ) 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-234">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="7fcf3-235">对于具有直接路由号码的资源帐户，外部转移电话号码格式取决于 [ (SBC) 设置的会话边界控制器 ](direct-routing-connect-the-sbc.md) 。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-235">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="7fcf3-236">显示的出站电话号码按如下方式确定：</span><span class="sxs-lookup"><span data-stu-id="7fcf3-236">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="7fcf3-237">对于呼叫计划号码，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-237">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="7fcf3-238">对于直接路由号码，发送的号码基于 P 宣称的身份 (PAI 在 SBC 上) 设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7fcf3-238">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="7fcf3-239">如果设置为 "已禁用"，将显示原始呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-239">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="7fcf3-240">这是默认和推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-240">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="7fcf3-241">如果设置为 "启用"，则显示资源帐户电话号码。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-241">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="7fcf3-242">在 Skype for business 混合环境中，若要将自动助理呼叫转移到 PSTN，请创建一个新的本地用户，并将呼叫转接设置为 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-242">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="7fcf3-243">必须为用户启用企业语音并分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-243">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="7fcf3-244">若要了解详细信息，请参阅 [自动助理呼叫转接到 PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-244">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="7fcf3-245">使用 PowerShell 创建自动助理</span><span class="sxs-lookup"><span data-stu-id="7fcf3-245">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="7fcf3-246">您也可以使用 PowerShell 创建和设置自动助理。</span><span class="sxs-lookup"><span data-stu-id="7fcf3-246">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="7fcf3-247">下面是管理自动助理所需的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7fcf3-247">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="7fcf3-248">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7fcf3-248">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="7fcf3-249">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7fcf3-249">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="7fcf3-250">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7fcf3-250">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="7fcf3-251">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="7fcf3-251">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="7fcf3-252">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="7fcf3-252">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="7fcf3-253">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="7fcf3-253">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="7fcf3-254">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="7fcf3-254">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="7fcf3-255">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="7fcf3-255">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="7fcf3-256">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="7fcf3-256">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="7fcf3-257">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="7fcf3-257">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="7fcf3-258">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="7fcf3-258">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="7fcf3-259">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="7fcf3-259">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="7fcf3-260">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="7fcf3-260">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="7fcf3-261">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="7fcf3-261">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="7fcf3-262">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="7fcf3-262">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="7fcf3-263">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="7fcf3-263">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="7fcf3-264">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="7fcf3-264">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a><span data-ttu-id="7fcf3-265">相关主题</span><span class="sxs-lookup"><span data-stu-id="7fcf3-265">Related topics</span></span>

[<span data-ttu-id="7fcf3-266">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="7fcf3-266">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="7fcf3-267">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="7fcf3-267">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="7fcf3-268">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="7fcf3-268">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="7fcf3-269">小型企业版示例-设置自动助理</span><span class="sxs-lookup"><span data-stu-id="7fcf3-269">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="7fcf3-270">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="7fcf3-270">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
