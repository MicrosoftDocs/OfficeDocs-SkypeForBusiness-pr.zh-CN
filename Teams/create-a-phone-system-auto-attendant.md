---
title: 设置云自动助理
ms.author: kenwith
author: kenwith
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 了解如何为 Microsoft 团队设置和测试云自动助理。
ms.openlocfilehash: 0b4b654a8e6d0eedd9d80cf5bf3bed8e9ee74115
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44047387"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="10f8a-103">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="10f8a-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="10f8a-104">自动助理允许用户呼叫你的组织，并导航菜单系统以与右部门通话、呼叫队列、人员或操作员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="10f8a-105">你可以通过 Microsoft 团队管理中心或通过 Powershell 为你的组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="10f8a-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with Powershell.</span></span> <span data-ttu-id="10f8a-106">若要创建自动助理，请在左侧导航中转到 "**语音**"，然后选择 "**自动助理** > **新增**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-106">To create an auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="10f8a-107">如果想要了解有关自动助理的详细信息，请参阅[什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="10f8a-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="10f8a-108">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="10f8a-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

<span data-ttu-id="10f8a-109">电话号码不会直接分配给自动助理，而是分配给与自动助理相关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="10f8a-109">Phone numbers are not directly assigned to the auto attendant, but rather to a [resource account](manage-resource-accounts.md) that is associated to the auto attendant.</span></span>

<span data-ttu-id="10f8a-110">自动助理实现通常涉及多个自动助理。</span><span class="sxs-lookup"><span data-stu-id="10f8a-110">Auto attendant implementations often involve several auto attendants.</span></span> <span data-ttu-id="10f8a-111">*第一级*自动助理通常有一个分配有电话号码的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-111">A *first-level* auto attendant usually has a resource account with an assigned phone number.</span></span> <span data-ttu-id="10f8a-112">嵌套的自动助理用作第*一级*自动助理作为呼叫连接的二级菜单。</span><span class="sxs-lookup"><span data-stu-id="10f8a-112">A nested auto attendant is used as a second-level menu that the *first-level* auto attendant connects  as call to.</span></span> <span data-ttu-id="10f8a-113">将电话号码分配给其资源帐户时，不需要*嵌套*的自动助理。</span><span class="sxs-lookup"><span data-stu-id="10f8a-113">A *nested* auto attendant isn't required to  have a phone number assigned to its resource account.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="10f8a-114">步骤 1-入门</span><span class="sxs-lookup"><span data-stu-id="10f8a-114">Step 1 — Get started</span></span>

- <span data-ttu-id="10f8a-115">必须具有自动助理才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-115">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="10f8a-116">有关资源帐户和所需的所有许可证的详细信息，请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="10f8a-116">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span> 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> <span data-ttu-id="10f8a-117">要将呼叫重定向到使用电话系统许可证的联机用户的操作员或菜单选项，您需要为企业语音启用它们。</span><span class="sxs-lookup"><span data-stu-id="10f8a-117">To redirect calls to an operator or a menu option that is an Online user with a Phone System license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="10f8a-118">请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队附加设备许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="10f8a-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="10f8a-119">你还可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="10f8a-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="10f8a-120">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="10f8a-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-auto-attendants"></a><span data-ttu-id="10f8a-121">步骤 2-创建自动助理</span><span class="sxs-lookup"><span data-stu-id="10f8a-121">Step 2 — Create auto attendants</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10f8a-122">每个自动助理都必须具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="10f8a-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="10f8a-123">必须先创建资源帐户，然后才能将其关联到自动助理。</span><span class="sxs-lookup"><span data-stu-id="10f8a-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="with-the-microsoft-teams-admin-center"></a><span data-ttu-id="10f8a-124">Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="10f8a-124">With the Microsoft Teams admin center</span></span>

<span data-ttu-id="10f8a-125">在 " **Microsoft 团队管理中心**" 中，单击 "**语音** > **自动助理**"，然后单击 " **+ 添加**"：</span><span class="sxs-lookup"><span data-stu-id="10f8a-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ Add**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="10f8a-126">常规信息页面</span><span class="sxs-lookup"><span data-stu-id="10f8a-126">General info page</span></span>

!["我的自动助理" 页面的屏幕截图](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

<span data-ttu-id="10f8a-128">![数字1的图标，上一个屏幕截图](media/teamscallout1.png)
**名称**中的标注输入自动助理的显示名称。</span><span class="sxs-lookup"><span data-stu-id="10f8a-128">![Icon of the number 1, a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a display name for your auto attendant.</span></span> <span data-ttu-id="10f8a-129">此名称为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="10f8a-129">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="10f8a-130">此处指定的**名称**列在 "**自动助理**" 选项卡上的列中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-130">The **Name** you designate here is listed in a column on the **Auto attendants** tab.</span></span>

<span data-ttu-id="10f8a-131"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-131"><a name="phonenumber"> </a></span></span>

* * *

<span data-ttu-id="10f8a-132">![数字2的图标，上一个屏幕截图](media/teamscallout2.png)
 <a name="operator"> </a> 
**运算符**中的标注这是可选的（但建议使用）。</span><span class="sxs-lookup"><span data-stu-id="10f8a-132">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png)
<a name="operator"> </a>
**Operator** This is optional (but recommended).</span></span> <span data-ttu-id="10f8a-133">你可以将 "**操作员**" 选项设置为允许呼叫者跳出菜单，并向指定的人讲话。</span><span class="sxs-lookup"><span data-stu-id="10f8a-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

<span data-ttu-id="10f8a-134">默认情况下，0键分配给操作员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-134">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="10f8a-135">如果您设置了一个操作员，请在 "**调用流**" 页面上的 "**编辑菜单选项**" 中告诉他们有关该选项的信息。</span><span class="sxs-lookup"><span data-stu-id="10f8a-135">If you set an Operator, tell people who call about the option in **Edit menu options** on the **Call flow** page.</span></span> <span data-ttu-id="10f8a-136">如果你在自动助理上设置了操作员，则在**呼叫者将听到**box 或将音频文件更改为包含此选项的情况下，输入相应的提示文本。</span><span class="sxs-lookup"><span data-stu-id="10f8a-136">If you set an operator on your auto attendant, you enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="10f8a-137">例如，"如需接线员，请按零"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-137">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="10f8a-138">可通过多种方法设置操作员：</span><span class="sxs-lookup"><span data-stu-id="10f8a-138">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="10f8a-139">**No 运算符**禁用 "operator" 和 "按 0" 选项。</span><span class="sxs-lookup"><span data-stu-id="10f8a-139">**No operator** disables the "Operator" and "Press 0" options.</span></span> <span data-ttu-id="10f8a-140">这是当前默认值。</span><span class="sxs-lookup"><span data-stu-id="10f8a-140">This is the current default.</span></span>
- <span data-ttu-id="10f8a-141">**您的组织中的人员**为 Office 365 中的企业语音或分配的呼叫计划分配了电话系统许可证的人员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-141">**Person in your organization** assigns a person with a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="10f8a-142">您也可以对其进行设置，以便呼叫者发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="10f8a-142">You can also set it up so the caller is sent to voicemail.</span></span> <span data-ttu-id="10f8a-143">若要将呼叫者发送到语音邮件，请选择**您的组织中的人员**，并将该帐户的设置设置为直接将呼叫发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="10f8a-143">To send a caller to voicemail, select **Person in your organization** and set that account's settings to send calls directly to voicemail.</span></span>

     > [!Note]
     > <span data-ttu-id="10f8a-144">**组织中的人员**可以是联机用户，也可以是使用 Skype For business 服务器内部托管的用户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-144">**Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

- <span data-ttu-id="10f8a-145">**语音应用** 选择链接到已创建的自动助理或通话队列的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="10f8a-145">**Voice app**  Select the name of the resource account linked to an auto attendant or call queue that has already been created.</span></span> <span data-ttu-id="10f8a-146">请求操作员的调用方将被重定向。</span><span class="sxs-lookup"><span data-stu-id="10f8a-146">Callers that request an operator are redirected there.</span></span>  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<span data-ttu-id="10f8a-147"><a name="timezone"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-147"><a name="timezone"> </a></span></span>

<span data-ttu-id="10f8a-148">![数字3的图标（上一个屏幕截图](media/teamscallout3.png) **时区**中的标注）您需要为自动助理设置时区。</span><span class="sxs-lookup"><span data-stu-id="10f8a-148">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Time zone** You are required to set the time zone for your auto attendant.</span></span> <span data-ttu-id="10f8a-149">该设置可以与为你的组织列出的主地址或不同时区的主地址的时区相同。</span><span class="sxs-lookup"><span data-stu-id="10f8a-149">The setting can be the same as the time zone of the main address listed for your organization, or a different time zone.</span></span> <span data-ttu-id="10f8a-150">每个自动助理都可以具有不同的时区。</span><span class="sxs-lookup"><span data-stu-id="10f8a-150">Each auto attendant can have a different time zone.</span></span> <span data-ttu-id="10f8a-151">为自动助理设置的 "营业时间" 还使用 "时区"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-151">The business hours set for the auto attendant also use this time zone.</span></span> <span data-ttu-id="10f8a-152">请确保设置正确的时区以避免工作时间差异，因为并非所有地区都有夏时制。</span><span class="sxs-lookup"><span data-stu-id="10f8a-152">Make sure to set the right timezone to avoid business-hours discrepancies since not all regions have Daylight Saving.</span></span> 

* * *

<span data-ttu-id="10f8a-153">![数字4的图标，上一个屏幕截图](media/teamscallout4.png)
 <a name="language"> </a> 
**语言**中的标注选择要用于自动助理的语言。</span><span class="sxs-lookup"><span data-stu-id="10f8a-153">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)
<a name="language"> </a>
**Language** Select the language that you want to use for your auto attendant.</span></span> <span data-ttu-id="10f8a-154">自动助理将该语言与呼叫者配合使用，并以这种语言播放所有系统提示。</span><span class="sxs-lookup"><span data-stu-id="10f8a-154">The auto attendant uses that language with callers, and all system prompts are played in this language.</span></span>

 * * *

<span data-ttu-id="10f8a-155">![数字5的图标，如果选择此选项，则上](media/teamscallout5.png)
一个屏幕截图中的标注将**启用语音输入**语音识别。</span><span class="sxs-lookup"><span data-stu-id="10f8a-155">![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png)
**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="10f8a-156">呼叫者可以使用[您设置的语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中的语音输入。</span><span class="sxs-lookup"><span data-stu-id="10f8a-156">Callers can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="10f8a-157">如果您希望仅让用户使用其电话键盘进行选择，您可以将语音识别设置为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-157">If you want to only let people use their phone keypad to make selections, you can leave speech recognition set to **Off**.</span></span>

* * *  

<span data-ttu-id="10f8a-158">完成选择后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-158">When you finish with your selections, click **Next**.</span></span>

#### <a name="call-flow"></a><span data-ttu-id="10f8a-159">通话流</span><span class="sxs-lookup"><span data-stu-id="10f8a-159">Call flow</span></span>

<span data-ttu-id="10f8a-160"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-160"><a name="greetingsandrouting"> </a></span></span>

> [!TIP]
> <span data-ttu-id="10f8a-161">您可以选择设置自定义的工作时间计划，并在工作时间内和之后使用不同的通话流行为。</span><span class="sxs-lookup"><span data-stu-id="10f8a-161">You can choose to set up a custom business hours schedule, with different call flow behaviors during and after business hours.</span></span> <span data-ttu-id="10f8a-162">若要设置自定义日程安排，请设置[在下班后的可选通话流程](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="10f8a-162">To set a custom schedule, set the optional [Call flow for after hours](#call-flow-for-after-hours).</span></span> <span data-ttu-id="10f8a-163">默认情况下，自动助理使用营业时间通话流。</span><span class="sxs-lookup"><span data-stu-id="10f8a-163">By default, an auto attendant uses business hours call flows.</span></span>

<span data-ttu-id="10f8a-164">您可以设置自定义的问候语、提示和菜单，以便用户在到达您的自动助理时听到。</span><span class="sxs-lookup"><span data-stu-id="10f8a-164">You can set up customized greetings, prompts, and menus that people hear when they reach your auto attendant.</span></span>

![屏幕截图：呼叫处理页面问候语部分](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

<span data-ttu-id="10f8a-166">**第一条播放问候语**问候语是可选的，可以设置为 "**无问候语**"、"**播放音频文件**" 或 "**键入问候语**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-166">**First play a greeting message** A greeting is optional and can be set to **No greeting**, **Play an audio file**, or **Type a greeting message**.</span></span>

> [!NOTE]
> <span data-ttu-id="10f8a-167">对于第一级别的自动助理，问候语非常有用。</span><span class="sxs-lookup"><span data-stu-id="10f8a-167">A greeting is most valuable for a first-level auto attendant.</span></span> <span data-ttu-id="10f8a-168">嵌套的自动助理通常不需要问候语。</span><span class="sxs-lookup"><span data-stu-id="10f8a-168">A nested auto attendant often doesn't need a greeting.</span></span>

<span data-ttu-id="10f8a-169">![数字1的图标，上一屏幕截图](media/teamscallout1.png)中的标注如果选择 "**无问候语**"，则呼叫者在您稍后选择的其中一个操作处理之前，不会听到消息或问候语。</span><span class="sxs-lookup"><span data-stu-id="10f8a-169">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) If you select **No Greeting**, the caller doesn't hear a message or greeting before the call is handled by one of the actions you select later.</span></span> 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

<span data-ttu-id="10f8a-170">![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注如果选择 "**播放音频文件**"，则可以使用 "**上传文件**" 按钮上载另存为音频的录制问候语消息。WAV，。MP3 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="10f8a-170">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="10f8a-171">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="10f8a-171">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="10f8a-172">![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注**键入问候消息**如果选择此选项，请在提供的字段中输入希望系统读取的文本（最多1000个字符）。</span><span class="sxs-lookup"><span data-stu-id="10f8a-172">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="10f8a-173">例如，输入 "欢迎使用 Contoso。</span><span class="sxs-lookup"><span data-stu-id="10f8a-173">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="10f8a-174">您的呼叫对我们非常重要。"</span><span class="sxs-lookup"><span data-stu-id="10f8a-174">Your call is important to us."</span></span> <span data-ttu-id="10f8a-175">输出由文本到语音软件创建。</span><span class="sxs-lookup"><span data-stu-id="10f8a-175">Output is created by text-to-voice software.</span></span>

* * *

<span data-ttu-id="10f8a-176">您可以从 "**发送呼叫**" 部分中选择 "呼叫" 下的 "呼叫" 旁边的内容。</span><span class="sxs-lookup"><span data-stu-id="10f8a-176">You can select what happens next to calls from the following actions in the  **Then route the call** section.</span></span> <span data-ttu-id="10f8a-177">设置为 "**断开连接**"、"**重定向呼叫**" 或 "**播放菜单" 选项**。</span><span class="sxs-lookup"><span data-stu-id="10f8a-177">Settings are **Disconnect**, **Redirect call**, or **Play menu options**.</span></span>

<span data-ttu-id="10f8a-178">如果您选择 "**断开连接**"，则呼叫者在问候语播放后将断开连接。</span><span class="sxs-lookup"><span data-stu-id="10f8a-178">If you select **Disconnect**, the caller is disconnected after the greeting plays.</span></span> 

<span data-ttu-id="10f8a-179"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-179"><a name="redirectcalls"> </a></span></span>

<span data-ttu-id="10f8a-180">![数字4的图标，上一个屏幕截图](media/teamscallout4.png)中的标注**重定向呼叫**会将呼叫者发送到所选目的地，而无需选择 "从选项"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-180">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png) **Redirect call** sends the caller to the chosen destination without choosing from options.</span></span> <span data-ttu-id="10f8a-181">可能的设置包括：</span><span class="sxs-lookup"><span data-stu-id="10f8a-181">The possible settings are:</span></span>

  - <span data-ttu-id="10f8a-182">**组织中的人员**您选择的帐户必须具有为企业语音启用的电话系统许可证或在 Office 365 中分配了呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="10f8a-182">**Person in organization** The account you choose must have a Phone System license enabled for Enterprise Voice or have an assigned Calling Plan in Office 365.</span></span> <span data-ttu-id="10f8a-183">您可以对其进行设置，以便呼叫者可以发送到语音邮件：选择**组织中的人员**，并将该帐户设置为将呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="10f8a-183">You can set it up so the caller can be sent to voicemail: select **Person in organization** and set that account to have calls forwarded directly to voicemail.</span></span>

  > [!Note]
  > <span data-ttu-id="10f8a-184">**组织中的人员**可以是联机用户，也可以是使用 Skype For business 服务器内部托管的用户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-184">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span>

  - <span data-ttu-id="10f8a-185">**语音应用**选择已设置的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="10f8a-185">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="10f8a-186">按与服务关联的资源帐户的名称搜索自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="10f8a-186">You search for the auto attendant or call queue by the name of the resource account associated with the service.</span></span>
  - <span data-ttu-id="10f8a-187">**语音邮件**选择包含组织中需要访问此自动助理接收的语音邮件的用户的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-187">**Voicemail** Select the Office 365 Group that contains the users in your organization that need to access voicemail received by this auto attendant.</span></span> <span data-ttu-id="10f8a-188">语音邮件将发送到您指定的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-188">Voicemail messages are sent to the Office 365 group you specified.</span></span> <span data-ttu-id="10f8a-189">若要访问语音邮件，组成员可以通过导航到 Outlook 中的组来打开它们。</span><span class="sxs-lookup"><span data-stu-id="10f8a-189">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

      <span data-ttu-id="10f8a-190">切换**到** **"打开"** 以支持语音语音语音消息。</span><span class="sxs-lookup"><span data-stu-id="10f8a-190">Switch **Transcription** to **on** to enable voice-to-text transcription of voicemail messages.</span></span>

 * * *

![屏幕截图： "调用处理页面操作" 部分](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

<span data-ttu-id="10f8a-192">![数字1的图标，当你选择 "**播放菜单**"](media/teamscallout1.png)选项时，上一个屏幕截图中的标注，你可以选择是使用音频文件，还是输入将呈现为文本到语音的文本，以向调用方提供拨号键盘菜单选项。</span><span class="sxs-lookup"><span data-stu-id="10f8a-192">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) When you select **Play menu options** You can select whether to use an audio file or enter text that will be rendered as text to speech to give dialpad menu options to callers.</span></span> <span data-ttu-id="10f8a-193">选择此项，而不是 "**重定向**" 或 "**断开连接**" 选项。</span><span class="sxs-lookup"><span data-stu-id="10f8a-193">Select this instead of the **Redirect call to** or **Disconnect** options.</span></span>


<span data-ttu-id="10f8a-194">![数字2的图标，上一屏幕截图](media/teamscallout2.png)中的标注**播放音频文件**，你可以为呼叫者设置提示和选项以供呼叫者选择。</span><span class="sxs-lookup"><span data-stu-id="10f8a-194">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Play an audio file** lets you set up a prompts and options for the caller to choose.</span></span> 
- <span data-ttu-id="10f8a-195">如果选择 "**播放音频文件**"，你可以使用 "**上传文件**" 按钮上载另存为音频的录制问候语消息。WAV，。MP3 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="10f8a-195">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="10f8a-196">录制内容不能大于 5 MB。</span><span class="sxs-lookup"><span data-stu-id="10f8a-196">The recording can be no larger than 5 MB.</span></span>

- <span data-ttu-id="10f8a-197">**键入问候消息**如果选择此选项，请在提供的字段中输入希望系统读取的文本（最多1000个字符）。</span><span class="sxs-lookup"><span data-stu-id="10f8a-197">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="10f8a-198">例如，输入 "欢迎使用 Contoso。</span><span class="sxs-lookup"><span data-stu-id="10f8a-198">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="10f8a-199">您的呼叫对我们非常重要。"</span><span class="sxs-lookup"><span data-stu-id="10f8a-199">Your call is important to us."</span></span> <span data-ttu-id="10f8a-200">输出由文本到语音软件创建。</span><span class="sxs-lookup"><span data-stu-id="10f8a-200">Output is created by text-to-voice software.</span></span>

<span data-ttu-id="10f8a-201">**设置菜单选项**可以在此对话框中添加或删除电话键盘或语音命令。</span><span class="sxs-lookup"><span data-stu-id="10f8a-201">**Set menu options** Telephone keypad or voice commands can be added or removed in this dialog.</span></span> <span data-ttu-id="10f8a-202">若要删除菜单选项，请删除语音命令条目，然后将 "**重定向**" 设置为 "返回" 以**选择**。</span><span class="sxs-lookup"><span data-stu-id="10f8a-202">To delete a menu option, remove the voice command entry and set **Redirect to** back to **Select**.</span></span>

> [!TIP]
> <span data-ttu-id="10f8a-203">当删除选项时，更新菜单提示文本或重新录制音频提示。</span><span class="sxs-lookup"><span data-stu-id="10f8a-203">Update menu prompt text or re-record the audio prompts when you remove options.</span></span> <span data-ttu-id="10f8a-204">为呼叫者播放的菜单提示不会自动更新。</span><span class="sxs-lookup"><span data-stu-id="10f8a-204">The menu prompt played for callers isn't automatically updated.</span></span>  
>
> <span data-ttu-id="10f8a-205">可以按任意顺序添加和删除任何菜单选项，并且键映射不必是连续的。</span><span class="sxs-lookup"><span data-stu-id="10f8a-205">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="10f8a-206">例如，可以创建一个映射到选项的键为0、1和3的菜单，而不使用键2。</span><span class="sxs-lookup"><span data-stu-id="10f8a-206">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="10f8a-207">键\* （重复）和\# （后退）由系统保留，无法重新分配。</span><span class="sxs-lookup"><span data-stu-id="10f8a-207">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="10f8a-208">如果启用语音识别，按 \* 将与 "重复" 对应，并且 # 将与 "后退" 语音命令对应。</span><span class="sxs-lookup"><span data-stu-id="10f8a-208">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="10f8a-209">![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注若要设置菜单选项，请单击 "按 **+ 分配拨号键**"，然后输入以下选项的信息：</span><span class="sxs-lookup"><span data-stu-id="10f8a-209">![Icon of the number 3, a callout in the previous screenshot](media/teamscallout3.png) To set up a menu option, click on the  **+Assign a dial key** and enter information for the following options:</span></span>

<span data-ttu-id="10f8a-210">![数字4的图标，上一个屏幕截图](media/teamscallout4.png)的 "**语音命令**" 列中的标注长度最多可为64个字符，并且可以包含多个词语，如 "客户服务" 或 "操作和共线"。  </span><span class="sxs-lookup"><span data-stu-id="10f8a-210">![Icon of the number 4, a callout in the previous screenshot](media/teamscallout4.png)  **Voice command** column for an option can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="10f8a-211">如果启用语音识别，将自动识别名称，并且呼叫者可以按3、说 "三" 或说出 "客户服务" 以选择映射到键3的选项。</span><span class="sxs-lookup"><span data-stu-id="10f8a-211">If speech recognition is enabled, the name is automatically recognized, and the caller is able to press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span> <span data-ttu-id="10f8a-212">此文本还会由用于服务确认提示的文本（如 "将你的呼叫转移到操作员"）呈现为语音。</span><span class="sxs-lookup"><span data-stu-id="10f8a-212">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to the Operator."</span></span>

<span data-ttu-id="10f8a-213">![数字5的图标，上一个屏幕截图](media/teamscallout5.png)中的标注。如果按下相应的键，或者使用语音识别选择选项，则调用将转到该选项集的 "**重定向到**" 选项集。</span><span class="sxs-lookup"><span data-stu-id="10f8a-213">![Icon of the number 5, a callout in the previous screenshot](media/teamscallout5.png)  The **Redirect to** option sets where the call goes if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="10f8a-214">可以将呼叫发送至：</span><span class="sxs-lookup"><span data-stu-id="10f8a-214">The call can be sent to:</span></span>

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- <span data-ttu-id="10f8a-215">**运算符**如果已设置操作员，则该选项将自动映射到 key 0，但也可以删除或重新分配给其他密钥。</span><span class="sxs-lookup"><span data-stu-id="10f8a-215">**Operator** If an operator is already set up, the option is automatically mapped to key 0, but can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="10f8a-216">选择此选项的呼叫者将被发送到指定的操作员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-216">The caller who selects this option is sent to the designated Operator.</span></span> <span data-ttu-id="10f8a-217">如果运算符未设置为任何键，则语音命令 "Operator" 也会被禁用。</span><span class="sxs-lookup"><span data-stu-id="10f8a-217">If Operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 
- <span data-ttu-id="10f8a-218">**组织中的人员**可以是联机用户，也可以是使用 Skype For business 服务器内部托管的用户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-218">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="10f8a-219">用户必须具有在 Office 365 中启用企业语音或已分配呼叫计划的电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="10f8a-219">The user must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="10f8a-220">在 "**按名称搜索**" 字段中搜索人员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-220">Search for the person in the **Search by name** field.</span></span>

- <span data-ttu-id="10f8a-221">**语音应用**选择已设置的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="10f8a-221">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="10f8a-222">按与应用程序关联的资源帐户的名称搜索自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="10f8a-222">You search for the auto attendant or call queue by the name of the resource account associated with the application.</span></span>

- <span data-ttu-id="10f8a-223">**语音邮件**选择包含组织中需要访问此自动助理接收的语音邮件的用户的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-223">**Voicemail** Select the Office 365 Group that contains the users in your organization that need to access voicemail received by this auto attendant.</span></span> <span data-ttu-id="10f8a-224">语音邮件将发送到您指定的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-224">Voicemail messages are sent to the Office 365 group you specified.</span></span> <span data-ttu-id="10f8a-225">若要访问语音邮件，组成员可以通过导航到 Outlook 中的组来打开它们。</span><span class="sxs-lookup"><span data-stu-id="10f8a-225">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

    <span data-ttu-id="10f8a-226">切换**到** **"打开"** 以支持语音语音语音消息。</span><span class="sxs-lookup"><span data-stu-id="10f8a-226">Switch **Transcription** to **on** to enable voice-to-text transcription of voicemail messages.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

<span data-ttu-id="10f8a-227">![数字6的图标（上一个屏幕截图](media/teamscallout6.png)  **目录**中的标注）在此部分中搜索，您可以启用 "**按姓名拨号**" 和 "自动助理的**分机**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-227">![Icon of the number 6, a callout in the previous screenshot](media/teamscallout6.png)  **Directory search** In this section, you can enable **Dial by name** and **Dial by Extension** for the auto attendant.</span></span> <span data-ttu-id="10f8a-228">可以在 "可选拨号作用域" 页面设置这些服务中和不包含的人员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-228">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="10f8a-229">默认情况下，目录搜索设置为 "**无**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-229">Directory search is set to **None** by default.</span></span>

<span data-ttu-id="10f8a-230">**按名称拨号**如果启用此选项，则呼叫者可以使用 "**按名称拨号**" 搜索组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-230">**Dial by name** If you enable this option, callers can search for people in your organization using **Dial by name**.</span></span> <span data-ttu-id="10f8a-231">他们说出用户的姓名和语音识别将其与用户相匹配。</span><span class="sxs-lookup"><span data-stu-id="10f8a-231">They say the user's name and voice recognition matches them to a user.</span></span> <span data-ttu-id="10f8a-232">可以在 "可选拨号作用域" 页面设置这些服务中和不包含的人员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-232">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="10f8a-233">任何带电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，可通过 "按名称拨号" 找到。</span><span class="sxs-lookup"><span data-stu-id="10f8a-233">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span>


<span data-ttu-id="10f8a-234">**通过分机号码拨号**如果启用此选项，则呼叫者可以通过输入其电话分机连接到您的组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-234">**Dial by extension** If you enable this option, callers can connect with users in your organization by entering their phone extension.</span></span> <span data-ttu-id="10f8a-235">你可以在 "可选拨号作用域" 页面中选择列为 "可供**拨号**" 或 "不可用" 的用户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-235">You can select which users are listed as available or not available for **Dial by extension** in the optional Dial Scope page.</span></span> <span data-ttu-id="10f8a-236">任何具有电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，并且可以通过 "通过分机拨入" 找到。</span><span class="sxs-lookup"><span data-stu-id="10f8a-236">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by extension.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10f8a-237">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="10f8a-237">Please observe the following:</span></span>
>- <span data-ttu-id="10f8a-238">希望可供拨号使用的用户需要将扩展指定为在 Active Directory 或 Azure Active Directory [Microsoft 365 管理中心](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users)中定义的以下某个电话属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="10f8a-238">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users).</span></span>
>    - <span data-ttu-id="10f8a-239">HomePhone</span><span class="sxs-lookup"><span data-stu-id="10f8a-239">HomePhone</span></span>
>    - <span data-ttu-id="10f8a-240">手机/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="10f8a-240">Mobile/MobilePhone</span></span>
>    - <span data-ttu-id="10f8a-241">TelephoneNumber/电话号码</span><span class="sxs-lookup"><span data-stu-id="10f8a-241">TelephoneNumber/PhoneNumber</span></span>
>    - <span data-ttu-id="10f8a-242">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="10f8a-242">OtherTelephone</span></span>
>- <span data-ttu-id="10f8a-243">在 "用户电话号码" 字段中输入扩展名所需的格式是`+<phonenumber>;ext=<extension>` " `x<extension>`或"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-243">The required format to enter the extension in the user phone number field is either `+<phonenumber>;ext=<extension>` or `x<extension>`.</span></span>
>- <span data-ttu-id="10f8a-244">当前不支持在团队管理中心中分配扩展。</span><span class="sxs-lookup"><span data-stu-id="10f8a-244">Assigning an extension in Teams Admin center is not currently supported.</span></span> <span data-ttu-id="10f8a-245">你必须使用[MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) PowerShell 命令或 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="10f8a-245">You must either use the [Set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) PowerShell command or the Microsoft 365 admin center.</span></span>
>- <span data-ttu-id="10f8a-246">在对 AAD 电话号码和 MobilePhone 属性的更改可用之前，最多可能需要12小时。</span><span class="sxs-lookup"><span data-stu-id="10f8a-246">It can take up to 12 hours before changes to the AAD PhoneNumber and MobilePhone attributes are available.</span></span>
>- <span data-ttu-id="10f8a-247">请不要为用户的 LineUri 定义扩展名。</span><span class="sxs-lookup"><span data-stu-id="10f8a-247">Please do NOT define an extension for the LineUri of a user.</span></span> <span data-ttu-id="10f8a-248">目前不支持这种情况。</span><span class="sxs-lookup"><span data-stu-id="10f8a-248">This is  not supported currently.</span></span>
>- <span data-ttu-id="10f8a-249">自动助理可配置为通过名称拨号或通过分机号码拨号，但不能同时进行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="10f8a-249">An auto attendant can be configured for either dial by name or dial by extension, but not both.</span></span>

> [!NOTE]
> <span data-ttu-id="10f8a-250">如果想要同时使用 "**按姓名**拨号" 和 "**按分机号码拨号**" 功能，您可以创建主自动助理（**按名称进行拨号**），如果用户知道用户的扩展名，则会提示呼叫者选择菜单选项，并将该选项设置为将呼叫转移到启用了 "通过分机拨号" 的自动助理。</span><span class="sxs-lookup"><span data-stu-id="10f8a-250">If you want to use both the **Dial by name** and **Dial by extension** features, you can create  main auto attendant (enabled for **Dial by name**) that prompts callers to choose a menu option if they know the extension of the user, and set that option to transfer the call to an auto attendant enabled for Dial by extension.</span></span>

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

<span data-ttu-id="10f8a-251">完成选择后，如果要更改高级设置，可以单击 "**下一步**"，如果要使用以下内容的默认设置，请单击 "**提交**"：</span><span class="sxs-lookup"><span data-stu-id="10f8a-251">When you are finished with your selections, you can click **Next** if you want to change advanced settings, or click **Submit** if you want to use default settings for things like:</span></span>
- <span data-ttu-id="10f8a-252">下班后的通话流程</span><span class="sxs-lookup"><span data-stu-id="10f8a-252">Call flow for after hours</span></span>
- <span data-ttu-id="10f8a-253">假期的通话流程</span><span class="sxs-lookup"><span data-stu-id="10f8a-253">Call flow for holidays</span></span>
- <span data-ttu-id="10f8a-254">拨号作用域</span><span class="sxs-lookup"><span data-stu-id="10f8a-254">Dial Scope</span></span>
- <span data-ttu-id="10f8a-255">资源帐户</span><span class="sxs-lookup"><span data-stu-id="10f8a-255">Resource accounts</span></span>

<span data-ttu-id="10f8a-256">由于自动助理需要拥有资源帐户，因此你可以选择继续到 "**资源帐户**" 页面并关联已配置的资源帐户，或者创建资源帐户并将其与自动助理相关联，如 "[管理 Microsoft 团队中的资源帐户](manage-resource-accounts.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="10f8a-256">Since your auto attendant is required to have a resource account, you have a choice of proceeding to the **Resource account** page and associating a resource account you've already configured, or creating a resource account and associating it to the auto attendant as described in [Manage resource accounts in Microsoft Teams](manage-resource-accounts.md).</span></span> <span data-ttu-id="10f8a-257">您将无法使用此自动助理，直到它已与资源帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="10f8a-257">You won't be able to use this auto attendant until it has been associated to a resource account.</span></span> <span data-ttu-id="10f8a-258">若要执行此操作，请单击屏幕底部的 "**下一步**" 按钮，然后单击左侧导航中的 "**资源帐户**" 以直接转到 "资源帐户" 页面，并将自动助理与资源帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="10f8a-258">to do this, click the **Next** button at the bottom of the screen and then click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="advanced-settings-optional"></a><span data-ttu-id="10f8a-259">高级设置（可选）</span><span class="sxs-lookup"><span data-stu-id="10f8a-259">Advanced settings (optional)</span></span>

<span data-ttu-id="10f8a-260">你可以配置其他四个屏幕，也可以在你选择的情况中保留默认值。</span><span class="sxs-lookup"><span data-stu-id="10f8a-260">There are four additional screens that you can configure or leave at defaults as you choose.</span></span>

##### <a name="call-flow-for-after-hours"></a><span data-ttu-id="10f8a-261">下班后的通话流程</span><span class="sxs-lookup"><span data-stu-id="10f8a-261">Call flow for after hours</span></span>

<span data-ttu-id="10f8a-262">默认情况下，自动助理的工作时间设置为上午9点，星期一到星期五</span><span class="sxs-lookup"><span data-stu-id="10f8a-262">By default, an auto attendant's business hours are set to 9am-5pm, Monday to Friday</span></span>  <!--24/7--><span data-ttu-id="10f8a-263">，并且将禁用*小时通话后*的呼叫流选项，因为所有小时都被视为 "*营业时间*"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-263">, and the call flow options for *after hours* calls are disabled because all hours are considered *business hours*.</span></span> <span data-ttu-id="10f8a-264">选择 "**设置自定义工作时间**" 选项时，"**时间段后的呼叫流程**" 页面将配置自动助理在下班后使用的呼叫处理规则。</span><span class="sxs-lookup"><span data-stu-id="10f8a-264">When you select the **Setup custom business hours** option, the **Call flow for after hours** page configures the call handling rules used by the auto attendant after hours.</span></span> <span data-ttu-id="10f8a-265">可用的选项是相同的，区别在于为不同的菜单和行为设置计划的能力。</span><span class="sxs-lookup"><span data-stu-id="10f8a-265">The options available are the same, the difference is the ability to set a schedule for different menus and behaviors.</span></span>

<span data-ttu-id="10f8a-266">自动助理的系统可能仅需要设置为第一级自动助理的小时调用处理行为。</span><span class="sxs-lookup"><span data-stu-id="10f8a-266">A system of auto attendants may only need to set after hours call handling behavior for the first-level auto attendant.</span></span> <span data-ttu-id="10f8a-267">嵌套的自动助理甚至可能无法由第一级自动助理调用，但系统可以为其使用的每个自动助理定义小时的行为。</span><span class="sxs-lookup"><span data-stu-id="10f8a-267">Nested auto attendants may not even be called by the first-level auto attendant, but alternately the system can define after-hours behavior for each auto attendant it uses.</span></span>

<span data-ttu-id="10f8a-268">最初，营业时间定义为从 12:00 am 开始，到星期日到星期六的 12:00 pm 结束。</span><span class="sxs-lookup"><span data-stu-id="10f8a-268">Initially, the business hours are defined to start at 12:00 am and end at 12:00 pm, Sunday through Saturday.</span></span> <span data-ttu-id="10f8a-269">工作时间后的所有小时数均被视为*时间*。</span><span class="sxs-lookup"><span data-stu-id="10f8a-269">All hours that aren't during business hours are considered *after hours*.</span></span>


![下班后通话流设置的屏幕截图](media/aa-afterhour.png)
 * * *

<span data-ttu-id="10f8a-271">![数字1（前一个屏幕截图](media/teamscallout1.png)中的标注）的图标，您可以单击 "**选择 24/7** " 以使该自动助理的所有工时为工作时间。</span><span class="sxs-lookup"><span data-stu-id="10f8a-271">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) You can click **Select 24/7** to make all hours business hours for this auto attendant.</span></span>

<span data-ttu-id="10f8a-272">![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注选择 "**重置为默认值**" 选项以还原计划中的所有更改，并返回到星期五上午 9:00 am 到 5:00 pm 的默认工作时间定义为 am。</span><span class="sxs-lookup"><span data-stu-id="10f8a-272">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) Select the **Reset to default** option to revert all changes in the schedule and return to the default definition of business hours as 9:00 am to 5:00 pm Monday to Friday.</span></span>

<span data-ttu-id="10f8a-273">![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注选择 "**清除所有小时**" 以完全清除该计划。</span><span class="sxs-lookup"><span data-stu-id="10f8a-273">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) Select **Clear all hours** to completely clear the schedule.</span></span> <span data-ttu-id="10f8a-274">不建议选择此项并保留未设置的小时，因此，仅当你想要完全恢复你的工作时间时，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="10f8a-274">Selecting this and leaving the hours unset is not recommended, so use this option only if you want to completely redo your business hours.</span></span>

<span data-ttu-id="10f8a-275">![数字4的图标，第4个屏幕截图](media/teamscallout4.png)![图标中的标注，第一个屏幕截图](media/teamscallout5.png)中的标注自定义一周中某一天的开始或结束时间，单击要重置的 "**开始**" 或 "结束" 时间，然后从显示的列表中选择新时间。 **End at**  </span><span class="sxs-lookup"><span data-stu-id="10f8a-275">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)  ![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png) To customize start or end time for a day of the week, click on **Start at** or **End at** time you wish to reset and select the new time from the list that appears.</span></span> <span data-ttu-id="10f8a-276">该列表允许你按15分钟的间隔选择营业时间，你在此处选择的工作时间基于你在 "**常规信息**" 页面上设置的时区。</span><span class="sxs-lookup"><span data-stu-id="10f8a-276">The list allows you to select business hours in 15-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span>

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

<span data-ttu-id="10f8a-277">![数字6的图标，上一屏幕截图](media/teamscallout6.png)中的标注设置工间休息（例如，午餐休息时间），选择 "为一周的某一天**添加新时间**" 以创建新的表行，然后选择 "新开始时间" 和 "结束时间"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-277">![Icon of the number 6,  a callout in the previous screenshot](media/teamscallout6.png)  To set up a break (a lunch break, for example), select **Add new time** for that day of the week to create a new table row, and select new start and end times.</span></span> <span data-ttu-id="10f8a-278">您可以在营业时间内设置多个工间休息。</span><span class="sxs-lookup"><span data-stu-id="10f8a-278">You can set multiple breaks within business hours.</span></span>

<span data-ttu-id="10f8a-279">小时后可用的[通话流](#call-flow)选项与工作时间内可用的选项相同。</span><span class="sxs-lookup"><span data-stu-id="10f8a-279">The [Call flow](#call-flow) options available after hours are the same as the options available during business hours.</span></span> <span data-ttu-id="10f8a-280">在 "信息输入" 页面上向下滚动以设置时间呼叫流选项。</span><span class="sxs-lookup"><span data-stu-id="10f8a-280">Scroll down on the information entry page to set after hours call flow options.</span></span>

* * *

<span data-ttu-id="10f8a-281">完成选择后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-281">When you are finished with your selections, click **Next**.</span></span> <span data-ttu-id="10f8a-282">您也可以单击左侧导航中的 "**资源帐户**" 直接转到 "资源帐户" 页面，并将自动助理与资源帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="10f8a-282">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

##### <a name="call-flow-during-holidays"></a><span data-ttu-id="10f8a-283">假期期间的通话流</span><span class="sxs-lookup"><span data-stu-id="10f8a-283">Call flow during holidays</span></span>

<span data-ttu-id="10f8a-284"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-284"><a name="holidaygreetings"> </a></span></span>

<span data-ttu-id="10f8a-285">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="10f8a-285">You can add up to 20 scheduled holidays to each auto attendant.</span></span> <span data-ttu-id="10f8a-286">您的组织可能已经定义了假日，如在[Microsoft 团队中设置假日](set-up-holidays-in-teams.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="10f8a-286">Your organization may already have defined holidays as described in [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="10f8a-287">如果不是，您将看到以下屏幕：</span><span class="sxs-lookup"><span data-stu-id="10f8a-287">If not you will see the following screen:</span></span> 

![屏幕截图：未配置任何假日](media/aa-no-holidays.png)

<span data-ttu-id="10f8a-289">![数字1的图标，以前的屏幕截图](media/teamscallout1.png)中的标注若要为自动助理上的假日设置自定义调用流，请单击 " **+ 添加**" "查看**新假日呼叫流程**" 屏幕。</span><span class="sxs-lookup"><span data-stu-id="10f8a-289">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To set a custom call flow for a holiday on the auto attendant, click **+ Add** the see the **New holiday call flow** screen.</span></span>
> [!TIP]
> <span data-ttu-id="10f8a-290">若要创建假日，您可以在**组织范围设置** > 的**假日**内转到屏幕。</span><span class="sxs-lookup"><span data-stu-id="10f8a-290">To create Holidays you can  go to the screen at **Org-wide settings** > **Holidays**.</span></span>  



![屏幕截图：添加呼叫处理程序](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

<span data-ttu-id="10f8a-292">![数字1的图标，上一个屏幕截图](media/teamscallout1.png)中的标注为新的调用流输入**名称**。</span><span class="sxs-lookup"><span data-stu-id="10f8a-292">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png)  Enter a **Name** for your new call flow.</span></span>

<span data-ttu-id="10f8a-293">![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注如果你已创建了假日，则会在 "**假日**" 下拉菜单中看到它们，并且可以选择它们。</span><span class="sxs-lookup"><span data-stu-id="10f8a-293">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you've already created holidays, you'll see them in the **Holiday** pull-down menu and can select them.</span></span> <span data-ttu-id="10f8a-294">你可能会看到一个未使用的选项，你可以根据需要进行编辑。</span><span class="sxs-lookup"><span data-stu-id="10f8a-294">You might see an unused option that you can edit into what you need.</span></span> <span data-ttu-id="10f8a-295">如果不是，请单击下拉列表底部的 "**添加**" 以创建新的假日。</span><span class="sxs-lookup"><span data-stu-id="10f8a-295">If not, click on **Add** at the bottom of the pull-down list to create a new Holiday.</span></span>  <span data-ttu-id="10f8a-296">有关用于创建假日的步骤，请参阅[在 Microsoft 团队中设置假日](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="10f8a-296">See [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md) for the steps used to create a holiday.</span></span> 

<span data-ttu-id="10f8a-297">假日通话流名称最长可以为64个字符，并且对于组织必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="10f8a-297">A holiday call flow name can be up to 64 characters long and must be unique for the organization.</span></span> <span data-ttu-id="10f8a-298">例如，在同一个组织中，您不能有两个假期通话流，名为 "感恩节"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-298">For example, you can't have two holiday call flows named "Thanksgiving" in the same organization.</span></span> <span data-ttu-id="10f8a-299">您的自动助理可以为您设置的每个假日都有一个呼叫流，但您可能希望具有计划的一组通用的行为，而不是自定义的问候语。</span><span class="sxs-lookup"><span data-stu-id="10f8a-299">Your auto attendant can have a call flow for each Holiday you've set up, but you might want to have a common set of behaviors planned other than a customized greeting.</span></span>

<span data-ttu-id="10f8a-300">![数字3的图标，上一个屏幕截图](media/teamscallout3.png)中的标注。可用于假日呼叫流的[问候语](#call-flow)选项与工作时间内可用的选项相同。</span><span class="sxs-lookup"><span data-stu-id="10f8a-300">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) The [Greetings](#call-flow) options available for a holiday call flow are the same as the options available during business hours.</span></span> <span data-ttu-id="10f8a-301">在播放问候语后执行的**操作**也类似，不同之处在于仅有的可用操作是 "**断开连接** **" 或 "重**定向到" 选项，并且当选择 "**重定向到**" 选项时，操作员不是可用选项之一。</span><span class="sxs-lookup"><span data-stu-id="10f8a-301">The **Actions** performed after the greeting plays is also similar, except that the only available actions are to **Disconnect** or **Redirect to**, and when choosing the **Redirect to** option the Operator is not one of the available choices.</span></span> <span data-ttu-id="10f8a-302">您不能设置特定于节日流的菜单。</span><span class="sxs-lookup"><span data-stu-id="10f8a-302">You can't set up a menu specific to a Holiday flow.</span></span>

> [!NOTE]
> <span data-ttu-id="10f8a-303">默认情况下，节假日期间收到的所有通话均设置为在问候语后**断开**（如果有），因此，如果需要自定义行为，则必须指定重定向。</span><span class="sxs-lookup"><span data-stu-id="10f8a-303">By default, all calls received during a holiday period are set to **Disconnect** after the greeting (if any), so you must specify a redirect if you want a custom behavior.</span></span>

!["假日" 页面期间的通话流的屏幕截图](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

<span data-ttu-id="10f8a-305">单击 "保存" 以完成假日呼叫流程的创建。</span><span class="sxs-lookup"><span data-stu-id="10f8a-305">Click on Save to finish creating the Holiday call flow.</span></span> <span data-ttu-id="10f8a-306">创建假期呼叫流程后，它将显示在 "假日" 屏幕的 "**呼叫流程" 中**。</span><span class="sxs-lookup"><span data-stu-id="10f8a-306">Once you have created a Holiday call flow, it will show up on the **Call Flows during holidays** screen.</span></span>

<span data-ttu-id="10f8a-307">单击 "设置拨号作用域"，**返回**到 **"在小时**后进行更改"，然后**提交**（如果已完成）。</span><span class="sxs-lookup"><span data-stu-id="10f8a-307">Click on **Next** to set Dial scope, **Back** to make changes to after hour call flows, and **Submit** if you are finished.</span></span> <span data-ttu-id="10f8a-308">您也可以单击左侧导航中的 "**资源帐户**" 直接转到 "资源帐户" 页面，并将自动助理与资源帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="10f8a-308">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="dial-scope"></a><span data-ttu-id="10f8a-309">拨号作用域</span><span class="sxs-lookup"><span data-stu-id="10f8a-309">Dial scope</span></span>

<span data-ttu-id="10f8a-310"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-310"><a name="dialscope"> </a></span></span>

![显示 "拨号作用域" 页面的屏幕截图](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

<span data-ttu-id="10f8a-312">在此页面上，您可以设置在您的目录中列出的人员，并可在某人呼叫您的组织时使用 "按名称拨号"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-312">On this page, you can set who is listed in your directory and available for Dial by Name when a person calls your organization.</span></span> <span data-ttu-id="10f8a-313">在以前的屏幕中，按名称拨号将默认设置为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-313">Dial by name is set to **Off** by default in an earlier screen.</span></span> <span data-ttu-id="10f8a-314">如果之前选择了 "**按分机拨号**"，则所有具有分机的用户都将可用。</span><span class="sxs-lookup"><span data-stu-id="10f8a-314">All users with an extension will be available if **Dial by extension** was selected earlier.</span></span>

<span data-ttu-id="10f8a-315">![数字 1](media/teamscallout1.png)的图标，上一个屏幕截图中的标注**包括**本部分中的选项是**所有联机用户**或**自定义用户组**</span><span class="sxs-lookup"><span data-stu-id="10f8a-315">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) **Include** The options in this section are either **All online users** or **Custom user groups**</span></span>

<span data-ttu-id="10f8a-316">如果选择 "**所有联机用户**"，则所有符合条件的用户都将包含在目录搜索中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-316">If you select **All online users**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="10f8a-317">**自定义用户组**此选项允许你搜索并选择已在你的组织中创建的 Office 365 组、通讯组列表或安全组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-317">**Custom user groups** This option lets you search for and select an Office 365 Group, distribution list, or security group already created in your organization.</span></span> <span data-ttu-id="10f8a-318">如果用户在所选的 Office 365 组、通讯组列表或安全组中，并且它们是使用**电话系统许可证的在线用户**，或者是使用 Skype For business 服务器内部托管的，则会将用户添加到目录中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-318">Users are added to the directory if they are in the chosen Office 365 Group, distribution list, or security group and they are **Online users with a Phone System license** or hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="10f8a-319">你可以将多个 Microsoft 365 组、通讯组列表和安全组添加到目录中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-319">You can add multiple Microsoft 365 Groups, distribution lists, and security groups to the directory.</span></span>

<span data-ttu-id="10f8a-320"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="10f8a-320"><a name="dialscope"> </a></span></span>

<span data-ttu-id="10f8a-321">在此页面上，你可以设置你的组织中的哪些用户将在你的目录中列出，并且当呼叫加入你的组织的人员可以使用名称进行拨号。</span><span class="sxs-lookup"><span data-stu-id="10f8a-321">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

<span data-ttu-id="10f8a-322">![数字2的图标，上一个屏幕截图](media/teamscallout2.png)中的标注将**排除**本部分中的选项，使您可以从组织的目录中排除特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-322">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Exclude** The options in this section let you exclude specific users or groups of users from the organization's directory.</span></span>

<span data-ttu-id="10f8a-323">如果您选择 "**无**"，则所有符合条件的用户都将包含在目录搜索中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-323">If you select **None**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="10f8a-324">**自定义用户组**你可以搜索在你的组织中创建的 Office 365 组、通讯组列表或安全组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-324">**Custom user group** You can search for an Office 365 Group, distribution list, or security group that has been created in your organization.</span></span> <span data-ttu-id="10f8a-325">将从目录搜索中排除该组中的用户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-325">Users in that group are excluded from directory search.</span></span> <span data-ttu-id="10f8a-326">你可以添加多个 Microsoft 365 组、通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="10f8a-326">You can add multiple Microsoft 365 Groups, distribution lists, and security groups.</span></span>


<span data-ttu-id="10f8a-327">如果启用 "按名称拨号" 时保留默认设置，则所有符合条件的用户都将包含在目录搜索中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-327">If you leave settings at their default when Dial by Name is enabled, all eligible users are included in directory search.</span></span>

> [!NOTE]
> <span data-ttu-id="10f8a-328">新用户可能需要长达36小时才能在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="10f8a-328">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span> <span data-ttu-id="10f8a-329">当有人通过语音识别按名称使用 "拨号" 时，新帐户可能不能用于此功能。</span><span class="sxs-lookup"><span data-stu-id="10f8a-329">When someone uses Dial by Name with speech recognition, new accounts may not be available for this feature.</span></span>

<span data-ttu-id="10f8a-330">输入所有必填字段并设置呼叫处理菜单和选项后，单击 "**下一步**" 以继续关联资源帐户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-330">After you enter all the required fields and set up call handling menus and options, click **Next** to proceed to associating a resource account.</span></span>

#### <a name="resource-accounts"></a><span data-ttu-id="10f8a-331">资源帐户</span><span class="sxs-lookup"><span data-stu-id="10f8a-331">Resource accounts</span></span>

<span data-ttu-id="10f8a-332">所有自动助理都必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-332">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="10f8a-333">第一级自动助理绝对需要至少一个具有关联服务号码的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="10f8a-333">First level auto attendants will definitely need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="10f8a-334">如果需要，您可以将多个资源帐户分配给自动助理，每个帐户都有一个单独的服务编号。</span><span class="sxs-lookup"><span data-stu-id="10f8a-334">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="10f8a-335">如果尚未将资源帐户配置为自动助理，您将看到以下屏幕：</span><span class="sxs-lookup"><span data-stu-id="10f8a-335">If you haven't already configured a resource account to your auto attendant, you would see the following screen:</span></span> 

![屏幕截图：可选的资源帐户管理](media/aa-ra-optional.png) 

<span data-ttu-id="10f8a-337">![数字1的图标，上一个屏幕截图](media/teamscallout1.png)中的标注要将一个或多个现有和未分配的资源帐户添加到自动助理，请单击 "**添加帐户**" 和 "搜索"，然后从提供的对话框中选择它们。</span><span class="sxs-lookup"><span data-stu-id="10f8a-337">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add one or more existing and unassigned resource accounts to the auto attendant, click **Add accounts** and search and select them from the provided dialogs.</span></span>

![新的 "助理摘要" 视图的屏幕截图](media/aa-assigned.png)

<span data-ttu-id="10f8a-339">![数字1的图标，上一个屏幕截图](media/teamscallout1.png)中的标注若要添加其他资源帐户，请单击 " **+ 添加帐户**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-339">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add an additional resource account, click on **+ Add account**.</span></span>

![数字2的图标，上一个屏幕截图中的标注](media/teamscallout2.png) <span data-ttu-id="10f8a-341">分配给此自动助理的资源帐户或帐户显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="10f8a-341">The resource account or accounts assigned to this auto attendant are shown in a list.</span></span>

## <a name="edit-auto-attendants"></a><span data-ttu-id="10f8a-342">编辑自动助理</span><span class="sxs-lookup"><span data-stu-id="10f8a-342">Edit auto attendants</span></span>

<span data-ttu-id="10f8a-343">保存新的自动助理后，它将列在 "**自动助理**" 页面上。</span><span class="sxs-lookup"><span data-stu-id="10f8a-343">After you save your new auto attendant, it is listed on the **Auto attendants** page.</span></span> <span data-ttu-id="10f8a-344">该页面允许你快速查看已设置的某些选项，包括名称、关联的资源帐户、语言和已分配的操作员。</span><span class="sxs-lookup"><span data-stu-id="10f8a-344">That page allows you to quickly see some of the options that you have set up, including the name, associated resource account, language, and assigned Operator.</span></span>

![助理列表的屏幕截图](media/aa-list.png)

<span data-ttu-id="10f8a-346">如果要更改自动助理设置，请选择 "自动助理"，然后在 "操作" 窗格中单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="10f8a-346">If you want to change auto attendant settings, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="10f8a-347">使用 Powershell 创建自动助理</span><span class="sxs-lookup"><span data-stu-id="10f8a-347">Create an auto attendant with Powershell</span></span>

<span data-ttu-id="10f8a-348">您也可以使用 PowerShell 创建和设置自动助理。</span><span class="sxs-lookup"><span data-stu-id="10f8a-348">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="10f8a-349">下面是管理自动助理所需的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="10f8a-349">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="10f8a-350">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="10f8a-350">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="10f8a-351">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="10f8a-351">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="10f8a-352">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="10f8a-352">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="10f8a-353">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="10f8a-353">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="10f8a-354">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="10f8a-354">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="10f8a-355">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="10f8a-355">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="10f8a-356">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="10f8a-356">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="10f8a-357">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="10f8a-357">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="10f8a-358">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="10f8a-358">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="10f8a-359">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="10f8a-359">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="10f8a-360">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="10f8a-360">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="10f8a-361">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="10f8a-361">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="10f8a-362">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="10f8a-362">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="10f8a-363">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="10f8a-363">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="10f8a-364">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="10f8a-364">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="10f8a-365">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="10f8a-365">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="10f8a-366">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="10f8a-366">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="10f8a-367">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="10f8a-367">More about Windows PowerShell</span></span>

- <span data-ttu-id="10f8a-368">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="10f8a-368">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="10f8a-369">使用 Windows PowerShell，您可以从单个管理点管理 Office 365 和 Microsoft 团队，从而简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="10f8a-369">With Windows PowerShell, you can manage Office 365 and Microsoft Teams from a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="10f8a-370">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="10f8a-370">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="10f8a-371">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="10f8a-371">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="10f8a-372">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="10f8a-372">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="10f8a-373">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如为多个用户同时进行设置更改。</span><span class="sxs-lookup"><span data-stu-id="10f8a-373">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as making setting changes for many users at once.</span></span> <span data-ttu-id="10f8a-374">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="10f8a-374">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="10f8a-375">通过 Office 365 PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="10f8a-375">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="10f8a-376">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="10f8a-376">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="10f8a-377">相关主题</span><span class="sxs-lookup"><span data-stu-id="10f8a-377">Related topics</span></span>

[<span data-ttu-id="10f8a-378">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="10f8a-378">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="10f8a-379">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="10f8a-379">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="10f8a-380">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="10f8a-380">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="10f8a-381">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="10f8a-381">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="10f8a-382">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="10f8a-382">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="10f8a-383">小型企业版示例-设置自动助理</span><span class="sxs-lookup"><span data-stu-id="10f8a-383">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
