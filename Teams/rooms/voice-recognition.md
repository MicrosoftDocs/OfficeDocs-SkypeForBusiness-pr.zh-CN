---
title: 租户管理控制，用于 (语音配置文件) 语音Teams 会议室
author: cichur
ms.author: v-cichur
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解租户管理对会议室中语音 (语音配置文件) Teams控制。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b4a8a5d0b866a3eb278ffdba575966f97c549d6
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997742"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a><span data-ttu-id="f4ef5-103">管理智能扬声器的语音识别技术控制</span><span class="sxs-lookup"><span data-stu-id="f4ef5-103">Manage voice recognition technology controls for an Intelligent Speaker</span></span>

<span data-ttu-id="f4ef5-104">智能说话人使用语音配置文件信息来识别谁在实时听录中说哪些内容。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-104">An Intelligent Speaker uses voice profile information to recognize who said what in live transcription.</span></span> <span data-ttu-id="f4ef5-105">当Microsoft Teams 会议室会议Windows配备智能扬声器时，可以在会议期间使用实时听录。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-105">When a Microsoft Teams Rooms for Windows meeting room is equipped with an Intelligent Speaker, live transcription can be used during the meeting.</span></span> <span data-ttu-id="f4ef5-106">本文介绍租户管理员如何控制用于语音识别的语音分析，以生成实时听录。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-106">This article explains how you, a tenant admin, control the voice profiling that's used for voice recognition to generate live transcription.</span></span> <span data-ttu-id="f4ef5-107">你可以控制组织使用语音识别的程度以及以下功能：</span><span class="sxs-lookup"><span data-stu-id="f4ef5-107">You can control to what degree the organization is using voice recognition and the following features:</span></span>

- <span data-ttu-id="f4ef5-108">在脚本中编辑发言人的姓名。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-108">Edit the speaker's name in transcripts.</span></span>
- <span data-ttu-id="f4ef5-109">更改脚本中单个话语的说话人或更改脚本中所有话语中的 (而不是在将来的脚本) 。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-109">Change the speaker of a single utterance in the transcript or change the speaker in all the utterances in the transcript (but not on future transcripts).</span></span>
- <span data-ttu-id="f4ef5-110">更改会议中列出的人的说话人标识。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-110">Change the speaker identification for the people who are listed in the meeting.</span></span>
- <span data-ttu-id="f4ef5-111">删除每个脚本上标识为该发言人的一个或多个陈述的标识。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-111">Remove the identification of one or more utterances identified as that speaker, on every transcript.</span></span>

## <a name="review-intelligent-speaker-requirements"></a><span data-ttu-id="f4ef5-112">查看智能说话人要求</span><span class="sxs-lookup"><span data-stu-id="f4ef5-112">Review Intelligent Speaker requirements</span></span>

<span data-ttu-id="f4ef5-113">智能扬声器包括特殊的七麦克风阵列。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-113">An Intelligent Speaker includes a special seven-microphone array.</span></span> <span data-ttu-id="f4ef5-114">系统使用语音配置文件信息来识别会议室中最多 10 个人的声音。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-114">The system uses voice profile information to identify voices of up to 10 people in meeting rooms.</span></span>

<span data-ttu-id="f4ef5-115">以下各项是智能说话人要求：</span><span class="sxs-lookup"><span data-stu-id="f4ef5-115">The following items are Intelligent Speaker requirements:</span></span>

- <span data-ttu-id="f4ef5-116">客户租户必须位于北美 (美国) 。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f4ef5-116">The customer tenant must be located in the U.S. (North America).<sup>1</sup></span></span>
- <span data-ttu-id="f4ef5-117">会议室应最多有 10 人当场。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-117">The meeting room should have a maximum of 10 people present in person.</span></span>
- <span data-ttu-id="f4ef5-118">会议室具有至少 7 Mbps 的上载链接。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-118">The meeting room has an upload link of minimum 7 Mbps.</span></span>

 <span data-ttu-id="f4ef5-119"><sup>1</sup> 智能扬声器和关联的语音配置文件和用法将仅以 EN-US 语言提供，对于美国、 (美国区域) 租户。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-119"><sup>1</sup> An Intelligent Speaker and associated voice profile and usage will only be available in EN-US language and for US (NA-US region) tenants.</span></span> <span data-ttu-id="f4ef5-120">租户用户注册并使用智能扬声器进行属性化听录时，这两个条件都必须成立。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-120">Both conditions must be true for a tenant user to enroll and use an Intelligent Speaker for attributed transcription.</span></span>

## <a name="set-up-an-intelligent-speaker"></a><span data-ttu-id="f4ef5-121">设置智能扬声器</span><span class="sxs-lookup"><span data-stu-id="f4ef5-121">Set up an Intelligent Speaker</span></span>

<span data-ttu-id="f4ef5-122">智能扬声器使用 USB 直接连接到Teams 会议室主机。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-122">An Intelligent Speaker connects directly using USB to the Teams Rooms console.</span></span> <span data-ttu-id="f4ef5-123">为获得最佳结果，应在 Yealink 品牌主机上使用 Yealink 品牌智能扬声器。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-123">For best results, a Yealink brand Intelligent Speaker should be used with a Yealink brand console.</span></span>

> [!NOTE]
> <span data-ttu-id="f4ef5-124">Yealink 智能 **扬声器必须与** Yealink 主机一同使用。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-124">A Yealink Intelligent Speaker **must** be used with a Yealink console.</span></span>

> [!NOTE]
> <span data-ttu-id="f4ef5-125">我们不支持连接到 Logitech Surface Pro Microsoft Teams 会议室 的智能Surface Pro Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-125">We don't support an Intelligent Speaker connected to Logitech Surface Pro Microsoft Teams Rooms.</span></span> <span data-ttu-id="f4ef5-126">有一个已知Teams 会议室无法通过扩展坞识别智能扬声器。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-126">There is a known issue that Teams Rooms can't recognize the Intelligent Speaker through the dock.</span></span>

<span data-ttu-id="f4ef5-127">智能扬声器应放置在至少 8 英寸 (20 厘米) 远离墙壁和大对象（如笔记本电脑）。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-127">An Intelligent Speaker should be placed at least 8 inches (20 cm) away from walls and large objects, such as laptops.</span></span> <span data-ttu-id="f4ef5-128">如果智能扬声器 USB 电缆对于设置来说不够长，请使用电缆扩展器。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-128">If the Intelligent Speaker USB cable isn't long enough for your setup, use cable extenders.</span></span>

1. <span data-ttu-id="f4ef5-129">以管理员角色登录到主机。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-129">Sign in to the console as administrator.</span></span>
2. <span data-ttu-id="f4ef5-130">设置Teams设置以匹配智能扬声器麦克风和扬声器。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-130">Set the Teams device settings to match the Intelligent Speaker microphone and speaker.</span></span>
   <span data-ttu-id="f4ef5-131">也可通过 TAC 门户（而不是会议室控制台）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-131">You can also do this through the TAC portal instead of at the room console.</span></span>

   <span data-ttu-id="f4ef5-132">该图显示了智能扬声器如何连接到设备（如果设备包含数据框）。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-132">The diagram shows how the Intelligent Speaker is connected to the device if the device includes a data box.</span></span>

   ![<span data-ttu-id="f4ef5-133">"智能扬声器"设置，包含扬声器、电源和 Data Box。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-133">The Intelligent Speaker setup with the speaker, the power and data box.</span></span> <span data-ttu-id="f4ef5-134">一条线转到主机的 USB 端口，另一条线转到电源。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-134">One line goes to the USB port of the console, and the other line goes to power.</span></span> ](../media/intelligent-speakers1.png)

   <span data-ttu-id="f4ef5-135">该图显示了如果设备不包含数据框，智能扬声器如何连接到设备。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-135">The diagram shows how the Intelligent Speaker is connected to the device if the device doesn't include a data box.</span></span>

   ![<span data-ttu-id="f4ef5-136">智能扬声器设置，扬声器直接连接到主机。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-136">The Intelligent Speaker setup with the speaker connecting directly to the console.</span></span> ](../media/intelligent-speakers2.png)

> [!Note]
> <span data-ttu-id="f4ef5-137">EPOS 和 Yealink 设备应具有"EPOS"或"Yealink"前缀，在扬声器名称中包含"UAC2_RENDER"，麦克风名称中包含"UAC2_TEAMS"。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-137">EPOS and Yealink devices should have "EPOS" or "Yealink" prefix and contain "UAC2_RENDER" in the speaker name and "UAC2_TEAMS" in the microphone name.</span></span> <span data-ttu-id="f4ef5-138">如果在下拉菜单中找不到这些麦克风和扬声器名称，请重新启动智能扬声器设备。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-138">If you don't find these microphone and speaker names in the dropdown menu, restart the Intelligent Speaker device.</span></span>

## <a name="enable-an-intelligent-speaker-user-recognition"></a><span data-ttu-id="f4ef5-139">启用智能说话人用户识别</span><span class="sxs-lookup"><span data-stu-id="f4ef5-139">Enable an Intelligent Speaker user recognition</span></span>

<span data-ttu-id="f4ef5-140">语音配置文件数据可用于具有智能扬声器的任何会议。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-140">Voice profile data can be used in any meeting with an Intelligent Speaker.</span></span> <span data-ttu-id="f4ef5-141">有关[Teams设置](../meeting-policies-in-teams.md#allow-transcription)的信息，请参阅会议策略和 PowerShell 会议[cmdlet。](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f4ef5-141">See [Teams meetings policies](../meeting-policies-in-teams.md#allow-transcription) and the [PowerShell meeting cmdlets](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) for information on the meeting settings.</span></span>

<span data-ttu-id="f4ef5-142">当策略设置为区分时，或者非会议被邀请者在会议期间加入时，将创建用户的语音配置文件数据。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-142">The voice profile data of the user is created when the policy is set to distinguish or a non-meeting invitee walks in during the meeting.</span></span> <span data-ttu-id="f4ef5-143">语音配置文件数据在会议结束时关闭。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-143">The voice profile data is dismissed at the end of the meeting.</span></span>

<span data-ttu-id="f4ef5-144">以下是设置智能说话人与用户识别所需的策略。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-144">The following are the required policies to set an Intelligent Speaker and user recognition.</span></span>

|<span data-ttu-id="f4ef5-145">策略</span><span class="sxs-lookup"><span data-stu-id="f4ef5-145">Policy</span></span>|<span data-ttu-id="f4ef5-146">说明</span><span class="sxs-lookup"><span data-stu-id="f4ef5-146">Description</span></span>|<span data-ttu-id="f4ef5-147">值和行为</span><span class="sxs-lookup"><span data-stu-id="f4ef5-147">Values and Behavior</span></span>|
|-|-|-|
|<span data-ttu-id="f4ef5-148">enrollUserOverride</span><span class="sxs-lookup"><span data-stu-id="f4ef5-148">enrollUserOverride</span></span>|<span data-ttu-id="f4ef5-149">用于设置租户的语音配置文件捕获Teams注册。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-149">Use to set voice profile capture, or enrollment, in Teams settings for a tenant.</span></span> |<span data-ttu-id="f4ef5-150">**禁用**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-150">**Disabled**</span></span><br><ul><li> <span data-ttu-id="f4ef5-151">从未注册的用户无法查看、注册或重新注册。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-151">Users who have never enrolled can't view, enroll, or re-enroll.</span></span><li><span data-ttu-id="f4ef5-152">注册流的入口点将隐藏。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-152">The entry point to the enrollment flow will be hidden.</span></span><li><span data-ttu-id="f4ef5-153">如果用户选择注册页面的链接，他们将看到一条消息，指出未为组织启用此功能。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-153">If users select a link to the enrollment page, they'll see a message that states this feature isn't enabled for their organization.</span></span>  <li><span data-ttu-id="f4ef5-154">已注册的用户可以在语音设置中查看和删除其Teams配置文件。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-154">Users who have enrolled can view and remove their voice profile in the Teams settings.</span></span> <span data-ttu-id="f4ef5-155">删除其语音配置文件后，他们将无法查看、访问或完成注册流。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-155">Once they remove their voice profile, they won't be able to view, access, or complete the enrollment flow.</span></span></li></ul><br><span data-ttu-id="f4ef5-156">**已启用**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-156">**Enabled**</span></span><br><ul><li> <span data-ttu-id="f4ef5-157">用户可以查看、访问和完成注册流。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-157">Users can view, access, and complete the enrollment flow.</span></span><li><span data-ttu-id="f4ef5-158">入口点会显示在"Teams"选项卡下的"设置 **"页面上**。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-158">The entry point will show on Teams settings page under the **Recognition** tab.</span></span></li></ul>|
|<span data-ttu-id="f4ef5-159">roomAttributeUserOverride</span><span class="sxs-lookup"><span data-stu-id="f4ef5-159">roomAttributeUserOverride</span></span>|<span data-ttu-id="f4ef5-160">在会议室中控制基于语音的用户标识。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-160">Control the voice-based user identification in meeting rooms.</span></span> <span data-ttu-id="f4ef5-161">此设置是帐户Teams 会议室必需的。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-161">This setting is required for Teams Rooms accounts.</span></span>| <span data-ttu-id="f4ef5-162">**禁用**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-162">**Off**</span></span><br><ul><li><span data-ttu-id="f4ef5-163">Teams 会议室设备不会从会议室发送节省音频流的带宽。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-163">The Teams Rooms device won't send audio stream-saving bandwidth from the room.</span></span> <li><span data-ttu-id="f4ef5-164">不会对会议室用户进行属性或区分，也不会检索或使用其语音签名。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-164">Meeting room users won't be attributed or distinguished, and their voice signatures won't be retrieved or used at all.</span></span><li><span data-ttu-id="f4ef5-165">会议室用户未知。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-165">Meeting room users are unknown.</span></span></li></ul> <br><span data-ttu-id="f4ef5-166">**属性**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-166">**Attribute**</span></span><br><ul><li><span data-ttu-id="f4ef5-167">聊天室用户将基于其注册状态进行属性管理。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-167">Rooms users will be attributed based on their enrollment status.</span></span><li><span data-ttu-id="f4ef5-168">注册的用户在听录中显示其姓名。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-168">Users who are enrolled are shown with their name in the transcription.</span></span>  <li><span data-ttu-id="f4ef5-169">未注册的用户将显示为"发言人 n"。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-169">Users who aren't enrolled show as Speaker n.</span></span><li><span data-ttu-id="f4ef5-170">设备Teams 会议室从会议室发送 7 个音频流。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-170">The Teams Rooms device will send seven audio streams from the room.</span></span></ul> <br><span data-ttu-id="f4ef5-171">**区分**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-171">**Distinguish**</span></span><br> <span data-ttu-id="f4ef5-172">*此设置将在以后可用。*</span><span class="sxs-lookup"><span data-stu-id="f4ef5-172">*This setting will be available at a later date.*</span></span>|
|<span data-ttu-id="f4ef5-173">enabletranscription</span><span class="sxs-lookup"><span data-stu-id="f4ef5-173">enabletranscription</span></span>|<span data-ttu-id="f4ef5-174">用户和聊天室Teams必需。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-174">Required for user and Teams rooms accounts.</span></span>|<span data-ttu-id="f4ef5-175">**True** 和 **False**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-175">**True** and **False**</span></span>|
||||

<span data-ttu-id="f4ef5-176">在Teams管理中心中，设置"**允许听录"** 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-176">In the Teams admin center, set the **Allow transcription** policy.</span></span> <span data-ttu-id="f4ef5-177">设置默认 **为"关闭**"。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-177">Settings are **Off** by default.</span></span>

![突出显示会议策略并选中"允许听录"的管理中心](../media/allow-transcription1.png)

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="f4ef5-179">常见问题 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="f4ef5-179">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="f4ef5-180">**语音配置文件数据存储在何处？**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-180">**Where is the voice profile data stored?**</span></span>

<span data-ttu-id="f4ef5-181">语音配置文件数据存储在包含用户Office 365云中。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-181">Voice profile data is stored in Office 365 cloud with user content.</span></span>

<span data-ttu-id="f4ef5-182">**什么是保留时间线和策略？**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-182">**What is the retention timeline and policy?**</span></span>

<span data-ttu-id="f4ef5-183">数据保留概述 中介绍了常规 [保留策略](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-183">General retention policy is stated in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span> <span data-ttu-id="f4ef5-184">此外，如果用户未在 3 年内受邀参加智能扬声器的任何会议，则用户的语音配置文件数据将在 3 年后删除。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-184">In addition, a user's voice profile data will be deleted after 3 years  if the user isn't invited to any meetings with an Intelligent Speaker within that 3-year period.</span></span> <span data-ttu-id="f4ef5-185">数据不会用于现有员工的任何会议。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-185">Data isn't used in any meetings for existing employees.</span></span> <span data-ttu-id="f4ef5-186">如果某个员工离开了公司，则语音配置文件数据被视为用户内容，并按数据保留Office 365中所述的数据保留[策略处理](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-186">If an employee has left the company, voice profile data is considered user content and is treated as such per Office 365 data retention policy described in the [Data retention overview](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="f4ef5-187">**语音配置文件数据是否用于Microsoft 服务？**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-187">**Is voice profile data used across Microsoft services?**</span></span>

<span data-ttu-id="f4ef5-188">否，语音配置文件数据仅用于用户已同意的目的。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-188">No, voice profile data is only used for the purpose for which the user has provided consent.</span></span> <span data-ttu-id="f4ef5-189">Microsoft 不会使用语音配置文件数据，除非在Teams方案中。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-189">Microsoft will not use the voice profile data except within Teams voice recognition scenarios.</span></span>

<span data-ttu-id="f4ef5-190">例如，Microsoft 不会在下列情况下使用数据：</span><span class="sxs-lookup"><span data-stu-id="f4ef5-190">For example, Microsoft won't use the data in the following situations:</span></span>

<span data-ttu-id="f4ef5-191">**我加入另一组织的会议时是否使用了我的语音配置文件数据？**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-191">**Is my voice profile data used when I join a meeting in another organization?**</span></span>

<span data-ttu-id="f4ef5-192">仅在由组织中用户组织的会议中为否。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-192">No only in meetings organized by a user in your organization.</span></span>

<span data-ttu-id="f4ef5-193">**如何导出我的语音配置文件？**</span><span class="sxs-lookup"><span data-stu-id="f4ef5-193">**How can I export my voice profile?**</span></span>

<span data-ttu-id="f4ef5-194">IT 管理员可以随时导出音频数据。</span><span class="sxs-lookup"><span data-stu-id="f4ef5-194">Your IT admin can export your audio data at any time.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f4ef5-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="f4ef5-195">Related topics</span></span>

[<span data-ttu-id="f4ef5-196">支持文章：使用智能说话人识别聊天室内参与者 </span><span class="sxs-lookup"><span data-stu-id="f4ef5-196">Support article: Use Intelligent Speakers to Identify in-room participants </span></span>](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
