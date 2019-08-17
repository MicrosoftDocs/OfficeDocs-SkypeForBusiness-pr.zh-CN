---
title: 设置云自动助理
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解如何为 Microsoft 团队设置和测试云自动助理。
ms.openlocfilehash: bd23262a3b8cd3c50cffbb4be6aa70317d209613
ms.sourcegitcommit: a0df7479662b3bea488c19722ad588981f58a5e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447937"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="f307d-103">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f307d-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="f307d-104">自动助理允许与你的组织进行通话的人员, 并导航到相应的菜单系统以将其转到相应的部门、呼叫队列、人员或运营商。</span><span class="sxs-lookup"><span data-stu-id="f307d-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="f307d-105">您可以使用 Microsoft 团队管理中心为您的组织创建自动助理。</span><span class="sxs-lookup"><span data-stu-id="f307d-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="f307d-106">若要创建新的自动助理, 请在左侧导航中转到 "**语音**", 然后选择 "**自动助理** > **新增**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="f307d-107">如果想要了解有关自动助理的详细信息, 请参阅[什么是云自动助理？](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="f307d-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="f307d-108">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="f307d-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="f307d-109">步骤 1-入门</span><span class="sxs-lookup"><span data-stu-id="f307d-109">Step 1 — Get started</span></span>

- <span data-ttu-id="f307d-110">必须具有自动助理才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f307d-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="f307d-111">有关资源帐户和所需的所有许可证的详细信息, 请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="f307d-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="f307d-112">要将呼叫重定向到使用**电话系统**许可证的联机用户的操作员或菜单选项, 您需要为企业语音启用它们。</span><span class="sxs-lookup"><span data-stu-id="f307d-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="f307d-113">请参阅[分配 Skype For business 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="f307d-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="f307d-114">你还可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f307d-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="f307d-115">例如, 运行:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f307d-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="f307d-116">步骤 2-创建新的自动助理</span><span class="sxs-lookup"><span data-stu-id="f307d-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f307d-117">每个自动助理都必须具有关联的[资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="f307d-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="f307d-118">必须先创建资源帐户, 然后才能将其关联到自动助理。</span><span class="sxs-lookup"><span data-stu-id="f307d-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f307d-119">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="f307d-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f307d-120">在 " **Microsoft 团队管理中心**" 中, 单击 "**语音** > **自动助理**", 然后单击 " **+ 新建**":</span><span class="sxs-lookup"><span data-stu-id="f307d-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="f307d-121">常规信息页面</span><span class="sxs-lookup"><span data-stu-id="f307d-121">General info page</span></span>

!["我的自动助理" 页面的屏幕截图](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="f307d-124">**名称**输入自动助理的描述性显示名称。</span><span class="sxs-lookup"><span data-stu-id="f307d-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="f307d-125">此名称为必填字段，最多可以包含 64 个字符，其中包括空格。</span><span class="sxs-lookup"><span data-stu-id="f307d-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="f307d-126">它列在 "**自动助理**" 选项卡上的 "**名称**" 列中。</span><span class="sxs-lookup"><span data-stu-id="f307d-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="f307d-128">**资源帐户**单击此按钮可选择一个或多个资源帐户以连接到新的自动助理。</span><span class="sxs-lookup"><span data-stu-id="f307d-128">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="f307d-129">所有自动助理都必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f307d-129">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="f307d-130">资源帐户可以有与帐户关联的电话号码, 但不要求电话号码。</span><span class="sxs-lookup"><span data-stu-id="f307d-130">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="f307d-131">顶级自动助理通常有一个分配有电话号码的资源帐户, 但嵌套的自动助理 (用作第一级自动助理连接到的第2级菜单) 可能没有分配给其资源帐户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f307d-131">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![数字3的图标, 引用上一个屏幕截图中的标注](media/sfbcallout3.png)

<span data-ttu-id="f307d-133">**时区** 必须为自动助理设置时区，但是此时区无需与组织的主要地址所在的时区对应。</span><span class="sxs-lookup"><span data-stu-id="f307d-133">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="f307d-134">每个自动助理都可以具有不同的时区, 并且基于您在此处选择的时区设置自动助理的 "营业时间" 设置。</span><span class="sxs-lookup"><span data-stu-id="f307d-134">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![数字4的图标, 引用上一个屏幕截图中的标注](media/sfbcallout4.png)

<span data-ttu-id="f307d-136">**语言** 从列出的可用语言列表中选择自动助理使用的语言。</span><span class="sxs-lookup"><span data-stu-id="f307d-136">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="f307d-137">您在此处设置的语言是自动助理用于与呼叫此自动助理的用户进行交互的语言, 并且所有系统提示均以这种语言播放。</span><span class="sxs-lookup"><span data-stu-id="f307d-137">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![数字5的图标, 引用上一个屏幕截图中的标注](media/sfbcallout5.png)

<span data-ttu-id="f307d-139">**运算符**这是可选的, 但你可以设置 "**运算符**" 选项, 以允许呼叫者跳出菜单并向某个人讲话。</span><span class="sxs-lookup"><span data-stu-id="f307d-139">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="f307d-140">默认情况下, 0 键分配给操作员。</span><span class="sxs-lookup"><span data-stu-id="f307d-140">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="f307d-141">如果您设置了一个操作员, 您还需要在 "**工作时间" 通话处理**页面上的 "**编辑" 菜单选项**中告诉他们有关该选项的信息。</span><span class="sxs-lookup"><span data-stu-id="f307d-141">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="f307d-142">如果您在自动助理上设置了操作员, 则需要在**呼叫者将听到**框中输入相应提示文本, 或将音频文件更改为包含此选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-142">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="f307d-143">例如，"如需接线员，请按零"。</span><span class="sxs-lookup"><span data-stu-id="f307d-143">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="f307d-144">可通过多种方法设置操作员:</span><span class="sxs-lookup"><span data-stu-id="f307d-144">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="f307d-145">拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。</span><span class="sxs-lookup"><span data-stu-id="f307d-145">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="f307d-146">**公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="f307d-146">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="f307d-147">**语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="f307d-147">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="f307d-148">您可以对其进行设置, 以便呼叫者将发送到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-148">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="f307d-149">若要执行此操作, 请选择**您的公司中的人员**, 并将此人的来电设置为直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-149">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![数字6的图标, 引用上一个屏幕截图中的标注](media/sfbcallout6.png)

<span data-ttu-id="f307d-151">**启用语音输入**如果选中此选项, 则可以使用语音识别。</span><span class="sxs-lookup"><span data-stu-id="f307d-151">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="f307d-152">拨入的人员可以使用[您设置的语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的语音输入。</span><span class="sxs-lookup"><span data-stu-id="f307d-152">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="f307d-153">如果您希望仅让用户使用其电话键盘, 则可以通过将语音识别设置为 "关闭" 来禁用语音识别。</span><span class="sxs-lookup"><span data-stu-id="f307d-153">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="f307d-154">完成选择后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-154">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="f307d-155">营业时间页面</span><span class="sxs-lookup"><span data-stu-id="f307d-155">Business hours page</span></span>

<span data-ttu-id="f307d-156">默认情况下, 营业时间设置为从星期一到星期五的 9:00 am 到 5:00 pm。</span><span class="sxs-lookup"><span data-stu-id="f307d-156">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="f307d-157">营业时间内未包括的所有小时都将在营业时间后考虑。</span><span class="sxs-lookup"><span data-stu-id="f307d-157">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="f307d-158">您可以单击 "**选择 24/7** " 以完成所有工时的工作时间。</span><span class="sxs-lookup"><span data-stu-id="f307d-158">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="f307d-159">除非选择 "**选择 24/7** " 选项, 否则将使用 "**在时间后的时间呼叫设置**" 页面来配置自动助理的工作时间后的呼叫处理规则。</span><span class="sxs-lookup"><span data-stu-id="f307d-159">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

!["营业时间" 页面的屏幕截图](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="f307d-162">默认情况下, "营业时间" 设置为 "星期一到星期五, 上午 9:00-5:00 pm"。</span><span class="sxs-lookup"><span data-stu-id="f307d-162">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="f307d-163">选择 "**清除所有小时**" 选项以取消选择计划中的所有小时。</span><span class="sxs-lookup"><span data-stu-id="f307d-163">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="f307d-164">当您选择 "**重置为默认值**" 时, 工作时间将重置为星期一到星期五 (即 9:00 am-5:00 pm)。</span><span class="sxs-lookup"><span data-stu-id="f307d-164">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="f307d-166">若要更改工作时间, 请突出显示要在日历中设置的营业时间。</span><span class="sxs-lookup"><span data-stu-id="f307d-166">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="f307d-167">日历允许你按30分钟的间隔选择营业时间, 你在此处选择的工作时间基于你在 "**常规信息**" 页面上设置的时区。</span><span class="sxs-lookup"><span data-stu-id="f307d-167">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="f307d-168">要设置休息时间（如午餐时间），请取消选择或通过拖动取消选择某段时间。</span><span class="sxs-lookup"><span data-stu-id="f307d-168">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="f307d-169">您可以在营业时间内设置多个工间休息。</span><span class="sxs-lookup"><span data-stu-id="f307d-169">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="f307d-170">完成选择后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-170">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="f307d-171">营业时间通话设置</span><span class="sxs-lookup"><span data-stu-id="f307d-171">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="f307d-172">如果你使用自定义工作时间计划, 你还需要在工作时间之后使用 "**下班后通话**" 页面设置呼叫处理页面, 该页面将提供与**工作时间通话设置**相同的选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-172">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="f307d-173">您可以设置问候语、提示和菜单, 以便用户在工作时间内呼叫与组织的自动助理关联的电话号码时听到。</span><span class="sxs-lookup"><span data-stu-id="f307d-173">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="f307d-174">![工作时间呼叫处理页面问候语部分](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![屏幕截图的屏幕截图 "营业时间呼叫处理页面操作" 部分的屏幕截图](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="f307d-174">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="f307d-176">**问候语**营业时间问候语是可选的, 并且可以设置为 "**无问候语**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-176">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="f307d-177">在这种情况下, 在你选择的其中一个操作处理呼叫之前, 呼叫者不会听到消息或问候语。</span><span class="sxs-lookup"><span data-stu-id="f307d-177">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="f307d-178">还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。</span><span class="sxs-lookup"><span data-stu-id="f307d-178">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="f307d-179">**上载音频文件**如果选择此项, 请录制问候语, 然后上载音频文件 (采用 .wav、mp3 或 .wma 格式)。</span><span class="sxs-lookup"><span data-stu-id="f307d-179">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="f307d-180">**键入问候消息**如果选择此选项, 请输入希望系统读取的文本 (最多为1000个字符)。</span><span class="sxs-lookup"><span data-stu-id="f307d-180">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="f307d-181">例如，可能会输入"欢迎来到 Contoso 。</span><span class="sxs-lookup"><span data-stu-id="f307d-181">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="f307d-182">您的呼叫对我们非常重要。"</span><span class="sxs-lookup"><span data-stu-id="f307d-182">Your call is important to us."</span></span> <span data-ttu-id="f307d-183">在 **呼叫者将听到** 框中。</span><span class="sxs-lookup"><span data-stu-id="f307d-183">in the **Callers will hear** box.</span></span>

* * *

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="f307d-185">你可以选择在营业时间内收到的通话所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="f307d-185">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="f307d-186">你可以从以下操作中进行选择:</span><span class="sxs-lookup"><span data-stu-id="f307d-186">You can chose from the following actions:</span></span>

- <span data-ttu-id="f307d-187">**断开连接**如果您选中它, 则在听到营业时间问候语后, 拨入的人员将断开连接。</span><span class="sxs-lookup"><span data-stu-id="f307d-187">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="f307d-188">**重定向呼叫** 这可用来将呼叫自动发送至：</span><span class="sxs-lookup"><span data-stu-id="f307d-188">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="f307d-189">**公司中**具有**电话系统**许可证的人员, 可在 Office 365 中启用企业语音或分配的呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="f307d-189">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="f307d-190">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-190">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="f307d-191">若要执行此操作, 请选择 "**公司中的人员**", 并将该用户设置为将呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-191">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="f307d-192">**公司中的人员**可以是联机用户, 也可以是使用 Skype For business server 2015 或 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="f307d-192">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="f307d-193">另一个**自动助理**</span><span class="sxs-lookup"><span data-stu-id="f307d-193">Another **Auto attendant**</span></span>

   <span data-ttu-id="f307d-194">可以使用现有的自动助理来创建包含子菜单的第二级菜单选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-194">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="f307d-195">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="f307d-195">These are called nested auto attendants.</span></span> <span data-ttu-id="f307d-196">若要将呼叫发送到嵌套的自动助理, 请选择 "**公司" 中**的 "人员", 然后分配一个已具有关联的自动助理的资源帐户, 或者在完成创建此自动助理后将与自动助理关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="f307d-196">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="f307d-197">"**播放" 菜单选项**也可用于设置要播放的提示。</span><span class="sxs-lookup"><span data-stu-id="f307d-197">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![数字3的图标, 引用上一个屏幕截图中的标注](media/sfbcallout3.png)

<span data-ttu-id="f307d-199">**菜单提示** 要创建主菜单提示，可以使用文本到语音转换或上载音频文件（.wav, .mp3 或 .wma）。</span><span class="sxs-lookup"><span data-stu-id="f307d-199">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="f307d-200">可以在 "设置呼叫者的**菜单导航**" 框中键入提示或录制音频文件, 例如: "用于销售额", 说或按下或说出 "1"。</span><span class="sxs-lookup"><span data-stu-id="f307d-200">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="f307d-201">如需服务，请按或报 2。</span><span class="sxs-lookup"><span data-stu-id="f307d-201">For Services, press or say 2.</span></span> <span data-ttu-id="f307d-202">如需客户支持，请按或报 3。</span><span class="sxs-lookup"><span data-stu-id="f307d-202">For Customer Support, press or say 3.</span></span> <span data-ttu-id="f307d-203">如需接线员，请按或报 0。</span><span class="sxs-lookup"><span data-stu-id="f307d-203">For the operator, press or say 0.</span></span> <span data-ttu-id="f307d-204">如需重听此菜单，请按星号键或报'重复'。</span><span class="sxs-lookup"><span data-stu-id="f307d-204">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="f307d-205">**键入问候消息**如果你选择此设置, 则应输入希望系统读取的文本 (最多为1000个字符)。</span><span class="sxs-lookup"><span data-stu-id="f307d-205">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="f307d-206">**上载音频文件** 如果选择此选项，则需要录制问候语并上载音频文件（.wav, .mp3 或 .wma 格式）。</span><span class="sxs-lookup"><span data-stu-id="f307d-206">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![数字4的图标, 引用上一个屏幕截图中的标注](media/sfbcallout4.png)

<span data-ttu-id="f307d-208">**菜单选项设置**可以添加或删除使用键盘上的键按钮的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-208">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="f307d-209">若要添加菜单选项, 请按 **+ 分配拨号键**。</span><span class="sxs-lookup"><span data-stu-id="f307d-209">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="f307d-210">相应的选项行如下所示。</span><span class="sxs-lookup"><span data-stu-id="f307d-210">A corresponding row of options will appear below.</span></span> <span data-ttu-id="f307d-211">若要删除菜单选项, 只需单击小键盘控件上对应键的左侧, 然后单击上面的 "删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="f307d-211">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="f307d-212">将移除按键映射行。</span><span class="sxs-lookup"><span data-stu-id="f307d-212">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="f307d-213">添加到删除选项时, 必须更新菜单提示文本或重新录制音频, 因为它不会针对现有菜单提示自动完成。</span><span class="sxs-lookup"><span data-stu-id="f307d-213">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="f307d-214">可以按任意顺序添加和删除任何菜单选项, 并且键映射不必是连续的。</span><span class="sxs-lookup"><span data-stu-id="f307d-214">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="f307d-215">例如, 可以创建一个映射到选项的键为0、1和3的菜单, 而不使用键2。</span><span class="sxs-lookup"><span data-stu-id="f307d-215">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="f307d-216">键\* (重复) 和\# (后退) 由系统保留, 无法重新分配。</span><span class="sxs-lookup"><span data-stu-id="f307d-216">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="f307d-217">如果启用语音识别, 按 \* 将与 "重复" 对应, 并且 # 将与 "后退" 语音命令对应。</span><span class="sxs-lookup"><span data-stu-id="f307d-217">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="f307d-218">若要设置菜单选项, 请在选择拨号键后, 您需要:</span><span class="sxs-lookup"><span data-stu-id="f307d-218">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="f307d-219">输入选项的 "**语音" 命令**。</span><span class="sxs-lookup"><span data-stu-id="f307d-219">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="f307d-220">此长度最多可包含64个字符, 并且可以包含多个词语, 如 "客户服务" 或 "操作和用户"。</span><span class="sxs-lookup"><span data-stu-id="f307d-220">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="f307d-221">如果启用语音识别, 将自动识别该名称, 并且呼叫者可以按3、说 "三" 或说出 "客户服务" 以选择映射到键3的选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-221">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="f307d-222">如果按下相应的键, 或者使用语音识别选中该选项, 请选择发送呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="f307d-222">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="f307d-223">可以将呼叫发送至：</span><span class="sxs-lookup"><span data-stu-id="f307d-223">The call can be sent to:</span></span>

  - <span data-ttu-id="f307d-224">**运算符**如果已设置操作员, 则它会自动映射到 key 0, 但也可以将其删除或重新分配给其他密钥。</span><span class="sxs-lookup"><span data-stu-id="f307d-224">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="f307d-225">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span><span class="sxs-lookup"><span data-stu-id="f307d-225">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="f307d-226">拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 **公司人员** 。</span><span class="sxs-lookup"><span data-stu-id="f307d-226">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="f307d-227">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-227">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="f307d-228">若要执行此操作, 请选择**您的公司中的人员**, 并将其呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-228">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="f307d-229">**公司中的人员**可以是联机用户, 也可以是使用 Skype For business Server 或 Lync server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="f307d-229">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>
    - <span data-ttu-id="f307d-230">另一个**自动助理**</span><span class="sxs-lookup"><span data-stu-id="f307d-230">Another **Auto attendant**</span></span>

       <span data-ttu-id="f307d-231">可以使用现有的自动助理来创建包含子菜单的第二级菜单选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-231">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="f307d-232">These are called nested auto attendants.</span><span class="sxs-lookup"><span data-stu-id="f307d-232">These are called nested auto attendants.</span></span> <span data-ttu-id="f307d-233">若要将呼叫发送到嵌套的自动助理, 请选择 "**公司" 中**的 "人员", 然后分配一个已具有关联的自动助理的资源帐户, 或者在完成创建此自动助理后将与自动助理关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="f307d-233">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="f307d-234">还将使用嵌套 (或二级) 自动助理的**工作时间**, 包括从已设置的其他自动助理发送的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f307d-234">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

       - <span data-ttu-id="f307d-235">**语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="f307d-235">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![数字5的图标, 引用上一个屏幕截图中的标注](media/sfbcallout5.png)

<span data-ttu-id="f307d-237">**按名称拨号**如果选择此选项, 将使使用目录搜索在你的组织中搜索人员的人员可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="f307d-237">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="f307d-238">在 **拨号范围** 页面上设置这些选项便可为“按名称拨号”选择哪些作为可选人列出或者哪些不作为可选人列出。</span><span class="sxs-lookup"><span data-stu-id="f307d-238">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="f307d-239">使用**电话系统**许可证的任何联机用户或任何使用 Skype For business 服务器或 Lync server 2013 的本地托管用户均可通过 "按名称拨号" 找到。</span><span class="sxs-lookup"><span data-stu-id="f307d-239">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="f307d-240">完成选择后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-240">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="f307d-241">假期呼叫设置</span><span class="sxs-lookup"><span data-stu-id="f307d-241">Holiday call settings</span></span>

<span data-ttu-id="f307d-242">可以为每个自动助理添加最多 20 个计划假日。</span><span class="sxs-lookup"><span data-stu-id="f307d-242">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="f307d-243">您可以在**组织范围的设置** > **假日**处转到 "创建假日" 的屏幕, 也可以创建新的调用处理程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="f307d-243">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

!["假日呼叫设置" 页面的屏幕截图](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="f307d-246">如果您已经创建了其他自动助理, 您可能会看到一个选项, 您可以在此列表中使用或编辑所需内容。</span><span class="sxs-lookup"><span data-stu-id="f307d-246">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="f307d-247">如果不是, 你将需要创建一个新的调用处理程序。</span><span class="sxs-lookup"><span data-stu-id="f307d-247">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="f307d-248">若要添加新的呼叫处理程序, 请单击 " **+ 新建呼叫处理程序**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-248">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![显示添加新呼叫处理程序的屏幕截图](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="f307d-251">在 "新建" 窗口中, 在屏幕顶部输入新呼叫处理程序的名称。</span><span class="sxs-lookup"><span data-stu-id="f307d-251">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="f307d-253">如果你的假日名称已存在于 "**假日**" 下拉列表中, 则可以使用它。</span><span class="sxs-lookup"><span data-stu-id="f307d-253">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="f307d-254">如果所需的假日名称尚不存在, 请在下拉列表中选择 "**创建新假日**", 然后在出现的新屏幕中为新假日分配名称和日期。</span><span class="sxs-lookup"><span data-stu-id="f307d-254">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="f307d-255">准备就绪后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-255">Click on **Save** when ready.</span></span>

<span data-ttu-id="f307d-256">假日名称可以包含最多 64 个字符，并且在同一自动助理中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f307d-256">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="f307d-257">例如，不能在同一自动助理中具有两个名为"感恩节"的假日。</span><span class="sxs-lookup"><span data-stu-id="f307d-257">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![数字3的图标, 引用上一个屏幕截图中的标注](media/sfbcallout3.png)

<span data-ttu-id="f307d-259">**问候语**问候语是可选的, 可以设置为 "**无问候语**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-259">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="f307d-260">在此情况下，在所选选项处理呼叫之前，呼叫者听不到消息或者问候语。</span><span class="sxs-lookup"><span data-stu-id="f307d-260">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="f307d-261">还可以上传音频文件 （ .wav、 mp3 或 .wma 格式），或使用文本转语音的方式创建自定义问候语。</span><span class="sxs-lookup"><span data-stu-id="f307d-261">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="f307d-262">**无问候语**当用户拨入自动助理电话号码时, 将不会播放任何问候语。</span><span class="sxs-lookup"><span data-stu-id="f307d-262">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="f307d-263">**上载音频文件**如果您选择此项, 请录制假日问候语, 然后上传音频文件 (采用 .wav、mp3 或 .wma 格式)</span><span class="sxs-lookup"><span data-stu-id="f307d-263">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="f307d-264">**键入问候消息**如果选择此选项, 请输入希望系统读取的文本 (最多为1000个字符)。</span><span class="sxs-lookup"><span data-stu-id="f307d-264">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="f307d-265">例如，可以输入"新年快乐！</span><span class="sxs-lookup"><span data-stu-id="f307d-265">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="f307d-266">我们的办事处当前未营业。"</span><span class="sxs-lookup"><span data-stu-id="f307d-266">Our offices are currently closed."</span></span> <span data-ttu-id="f307d-267">在 "**键入问候消息**" 框中。</span><span class="sxs-lookup"><span data-stu-id="f307d-267">in the **Type a greeting message** box.</span></span>

![数字4的图标, 引用上一个屏幕截图中的标注](media/sfbcallout4.png)

<span data-ttu-id="f307d-269">**操作**你可以选择在此节假日期间收到的通话所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="f307d-269">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="f307d-270">可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="f307d-270">You can chose from the following options:</span></span>

- <span data-ttu-id="f307d-271">**断开连接** 呼叫者听到假日问候语以后被断开连接。</span><span class="sxs-lookup"><span data-stu-id="f307d-271">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="f307d-272">**重定向呼叫** 这可用来将呼叫自动发送至：</span><span class="sxs-lookup"><span data-stu-id="f307d-272">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="f307d-273">拥有 **电话系统** 许可证，启用了企业语音或在 Office 365 中分配了呼叫计划的 \*\*公司人员 \*\*。</span><span class="sxs-lookup"><span data-stu-id="f307d-273">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="f307d-274">你可以通过此设置将呼叫者直接转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-274">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="f307d-275">若要执行此操作, 请选择**公司中的人员**, 并将其设置为将呼叫直接转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f307d-275">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="f307d-276">**公司人员** 可以是联机用户或者是使用 Skype for Business Server 2015 或者 Lync Server 2013 的本地托管用户。</span><span class="sxs-lookup"><span data-stu-id="f307d-276">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="f307d-277">**语音应用程序**选择与已创建的呼叫队列或自动助理相关联的资源帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="f307d-277">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="f307d-278">默认方式，将假日期间到达的所有呼叫设置为听到问候语（如果有）后断开连接，所以如果希望有不同的反应，则必须指定重定向。</span><span class="sxs-lookup"><span data-stu-id="f307d-278">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="f307d-279">"选择拨叫范围"页面</span><span class="sxs-lookup"><span data-stu-id="f307d-279">Select dial scope page</span></span>

<span data-ttu-id="f307d-280">在此页面上, 你可以设置你的组织中的哪些用户将在你的目录中列出, 并且当呼叫加入你的组织的人员可以使用名称进行拨号。</span><span class="sxs-lookup"><span data-stu-id="f307d-280">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![显示 "拨号作用域" 页面的屏幕截图](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="f307d-282">![数字1的图标, 在上一个屏幕截图](media/sfbcallout1.png)中使用 "**包括**" 选项引用标注, 你有两个选项:</span><span class="sxs-lookup"><span data-stu-id="f307d-282">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="f307d-283">**所有在线用户** 使用此选项可以将组织中的所有人包含在目录搜索中。</span><span class="sxs-lookup"><span data-stu-id="f307d-283">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="f307d-284">所有具有**电话系统**许可证的联机用户, 以及使用 Office 365 中具有呼叫计划的 Skype For business 服务器或 Lync server 2013 的用户托管的用户。</span><span class="sxs-lookup"><span data-stu-id="f307d-284">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="f307d-285">**自定义用户组**如果使用此选项, 则可以搜索在你的组织中创建的 Office 365 组、通讯组列表或安全组, 以及添加到此 Office 365 组、通讯组列表或安全组的人员, 这些**用户是使用电话系统许可证**或使用 Skype For Business server 2015 或 Lync Server 2013 内部托管。</span><span class="sxs-lookup"><span data-stu-id="f307d-285">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="f307d-286">你可以添加多个 Office 365 组、通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="f307d-286">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![数字2的图标, 引用上一个屏幕截图中的标注](media/sfbcallout2.png)

<span data-ttu-id="f307d-288">使用 "**排除**" 选项, 您有两个选项:</span><span class="sxs-lookup"><span data-stu-id="f307d-288">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="f307d-289">**无** 使用此选项表示不会将任何在线用户从目录搜索中排除。</span><span class="sxs-lookup"><span data-stu-id="f307d-289">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="f307d-290">**自定义用户组**如果使用此选项, 则可以搜索在你的组织中创建的 Office 365 组、通讯组列表或安全组, 并且添加到此 Office 365 组、通讯组列表或安全组的所有人员都将从目录搜索中排除。</span><span class="sxs-lookup"><span data-stu-id="f307d-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="f307d-291">你可以添加多个 Office 365 组、通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="f307d-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="f307d-292">当有人通过语音识别按名称使用 "拨号" 时, 最多可能需要36小时才能让新用户在目录中列出其名称。</span><span class="sxs-lookup"><span data-stu-id="f307d-292">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="f307d-293">输入所有必填字段并设置呼叫处理菜单和选项后, 单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-293">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="f307d-294">编辑和测试自动助理</span><span class="sxs-lookup"><span data-stu-id="f307d-294">Editing and testing auto attendants</span></span>

<span data-ttu-id="f307d-295">保存自动助理后，自动助理将在" **自动助理**"页面列出。</span><span class="sxs-lookup"><span data-stu-id="f307d-295">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="f307d-296">这将允许你快速查看已设置的一些选项, 包括姓名、电话号码、语言和状态。</span><span class="sxs-lookup"><span data-stu-id="f307d-296">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="f307d-297">如果要更改自动助理, 请选择 "自动助理", 然后在 "操作" 窗格中单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f307d-297">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="f307d-298">您还可以使用 "操作" 窗格中的 "**测试**" 按钮, 快速将测试呼叫置于自动助理。</span><span class="sxs-lookup"><span data-stu-id="f307d-298">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="f307d-299">自动助理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="f307d-299">Auto attendant cmdlets</span></span>

<span data-ttu-id="f307d-300">还可以使用 Windows PowerShell 来创建和设置自动助理。</span><span class="sxs-lookup"><span data-stu-id="f307d-300">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="f307d-301">下面是管理自动助理所需的 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f307d-301">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="f307d-302">新-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="f307d-302">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="f307d-303">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="f307d-303">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="f307d-304">CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="f307d-304">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="f307d-305">CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="f307d-305">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="f307d-306">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="f307d-306">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="f307d-307">新-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="f307d-307">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="f307d-308">新-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="f307d-308">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="f307d-309">新-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="f307d-309">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="f307d-310">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="f307d-310">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="f307d-311">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="f307d-311">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="f307d-312">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="f307d-312">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="f307d-313">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="f307d-313">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="f307d-314">CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="f307d-314">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="f307d-315">新-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="f307d-315">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="f307d-316">CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="f307d-316">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="f307d-317">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="f307d-317">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="f307d-318">新-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="f307d-318">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="f307d-319">有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="f307d-319">More about Windows PowerShell</span></span>

- <span data-ttu-id="f307d-320">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="f307d-320">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f307d-321">使用 Windows PowerShell, 你可以使用单一的管理点管理 Office 365 和 Microsoft 团队, 这样你有多个任务需要执行这些任务即可。</span><span class="sxs-lookup"><span data-stu-id="f307d-321">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f307d-322">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f307d-322">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="f307d-323">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="f307d-323">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="f307d-324">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f307d-324">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="f307d-325">Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 365 管理中心, 例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="f307d-325">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f307d-326">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="f307d-326">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="f307d-327">通过 Office 365 PowerShell 管理 Office 365</span><span class="sxs-lookup"><span data-stu-id="f307d-327">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="f307d-328">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f307d-328">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="f307d-329">相关主题</span><span class="sxs-lookup"><span data-stu-id="f307d-329">Related topics</span></span>

[<span data-ttu-id="f307d-330">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="f307d-330">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="f307d-331">获取服务电话号码</span><span class="sxs-lookup"><span data-stu-id="f307d-331">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="f307d-332">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="f307d-332">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="f307d-333">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="f307d-333">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="f307d-334">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="f307d-334">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="f307d-335">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="f307d-335">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
