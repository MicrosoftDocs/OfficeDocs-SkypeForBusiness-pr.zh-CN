---
title: '将 Skype for Business 与第三方音频会议提供商集成的生命周期结束 '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: 2021年7月31日, 生命期结束计划将结束与第三方音频会议提供商 (第三方 ACP) 的 Skype for Business 的集成。
ms.openlocfilehash: f5d821b1dbb71fb2b1371230a6d7575d6fb70fe8
ms.sourcegitcommit: c6ecea3205d509609a655db2348c04f655319df8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2019
ms.locfileid: "36170990"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a><span data-ttu-id="8ed2a-103">将 Skype for Business 与第三方音频会议提供商集成的生命周期结束</span><span class="sxs-lookup"><span data-stu-id="8ed2a-103">End of life program for the integration of Skype for Business with third-party audio conferencing providers</span></span> 

<span data-ttu-id="8ed2a-104">Microsoft 已宣布开始使用第三方音频会议提供商 (ACPs) 与 Skype for Business 集成的生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-104">Microsoft has announced the start of the end of life program for the integration of Skype for Business with third-party audio conferencing providers (ACPs).</span></span> 

<span data-ttu-id="8ed2a-105">生命周期结束计划将于2021年7月31日结束。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-105">The end of life program will conclude on July 31, 2021.</span></span> <span data-ttu-id="8ed2a-106">当程序结束时, 与第三方音频会议提供商的 Skype for Business 集成将停止工作, 并且将在该日期 (2021 年7月31日) 看到以下更改:</span><span class="sxs-lookup"><span data-stu-id="8ed2a-106">When the program concludes, the integration of Skype for Business with third-party audio conferencing providers will stop working and the following changes will be observed on that date (July 31, 2021):</span></span>

- <span data-ttu-id="8ed2a-107">尝试通过第三方 ACP 服务提供的拨入号码加入任何 Skype for Business 会议的参与者将不再连接到 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-107">Participants who attempt to join any Skype for Business meeting via dial-in numbers provided by a third-party ACP service will no longer be connected to the Skype for Business meeting.</span></span>
 
- <span data-ttu-id="8ed2a-108">为第三方 ACP 服务启用的用户将不再自动包含任何新的 Skype for business 会议邀请中的电话拨入信息。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-108">Users enabled for a third-party ACP service will no longer have their dial-in information automatically included in any new Skype for Business meeting invites.</span></span>

<span data-ttu-id="8ed2a-109">作为开始使用计划结束的一部分, 以下更改已生效, 并且将在生命周期结束之前继续保持不动的状态:</span><span class="sxs-lookup"><span data-stu-id="8ed2a-109">As part of the announcement of the start of the end of life program, the following change have taken effect and will continue to be in place until the conclusion of the end of life program:</span></span> 

- <span data-ttu-id="8ed2a-110">没有配置为使用第三方 ACP 服务的 Skype for business 用户的客户将无法将任何用户配置为使用第三方 ACP 服务。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-110">Customers with no Skype for Business users configured to use a third-party ACP service will not be able to configure any users to use a third-party ACP service.</span></span>

- <span data-ttu-id="8ed2a-111">已配置为使用第三方 ACP 服务的 Skype for business 用户的现有客户将继续能够在生命周期结束期间添加新用户。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-111">Existing customers with Skype for Business users configured to use a third-party ACP service will continue to be able to add new users for the duration of the end of life period.</span></span> <span data-ttu-id="8ed2a-112">请注意, 我们不建议将其他 Skype for Business 用户设置为使用第三方 ACP 服务, 因为将在2021年7月31日生效的更改也将应用于这些更改。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-112">Please note that we do not recommend setting up additional Skype for Business users to use a third-party ACP service, as the changes that will come into effect on July 31, 2021 will also apply to them.</span></span>

## <a name="preparing-for-this-change"></a><span data-ttu-id="8ed2a-113">准备进行此更改</span><span class="sxs-lookup"><span data-stu-id="8ed2a-113">Preparing for this change</span></span>

<span data-ttu-id="8ed2a-114">为准备此更改, 我们鼓励受影响的组织在2021年7月31日之前通知已启用的此计划更新用户。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-114">To prepare for this change, we encourage affected organizations to notify their enabled users of this planned update prior to July 31, 2021.</span></span> 

<span data-ttu-id="8ed2a-115">2021年7月31日之后, 用户可以继续使用 Skype for Business, 而不中断其在线会议;但是, 如果组织需要电话拨入音频会议和 Skype for business 或 Microsoft 团队, 则组织需要为 Microsoft 提供的音频会议启用用户。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-115">After July 31, 2021, users can continue to use Skype for Business with no interruption to their online meetings; however, organizations will need to enable their users for Audio Conferencing provided by Microsoft if they require dial-in audio conferencing with Skype for Business or Microsoft Teams.</span></span> <span data-ttu-id="8ed2a-116">若要了解有关 Microsoft 音频会议的详细信息, 请参阅[音频会议](https://products.office.com/en-us/skype-for-business/audio-conferencing)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-116">To learn more about Microsoft Audio Conferencing, see [Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing).</span></span> 

<span data-ttu-id="8ed2a-117">根据所需的组织结束状态, 可以遵循以下三个路径:</span><span class="sxs-lookup"><span data-stu-id="8ed2a-117">Depending on the desired end state of an organization, there are three paths that can be followed:</span></span>

- <span data-ttu-id="8ed2a-118">迁移到 Microsoft 音频会议。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-118">Migrate to Microsoft Audio Conferencing.</span></span> 
- <span data-ttu-id="8ed2a-119">继续单独使用第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-119">Continue to separately use a third-party audio conferencing provider.</span></span> 
- <span data-ttu-id="8ed2a-120">完全停止使用电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-120">Stop using dial-in conferencing altogether.</span></span>

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a><span data-ttu-id="8ed2a-121">路径 #1: 迁移到 Microsoft 音频会议</span><span class="sxs-lookup"><span data-stu-id="8ed2a-121">Path #1: Migrate to Microsoft Audio Conferencing</span></span>   

<span data-ttu-id="8ed2a-122">如果组织决定迁移到 Microsoft 音频会议并在2021年7月31日之前完成迁移, 将不会在该日期期间或之后遇到任何服务影响。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-122">Organizations that decide to migrate to Microsoft Audio Conferencing and complete their migration prior to July 31, 2021, will not experience any service impact during or after that date.</span></span> <span data-ttu-id="8ed2a-123">迁移到 Microsoft 音频会议将对组织引入以下更改:</span><span class="sxs-lookup"><span data-stu-id="8ed2a-123">The migration to Microsoft Audio Conferencing will introduce the following changes to an organization:</span></span> 

- <span data-ttu-id="8ed2a-124">将向所有其他 Office 365 服务收取服务费用。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-124">The service will be billed with all other Office 365 services.</span></span> 

- <span data-ttu-id="8ed2a-125">如果购买了标准套餐, 则按每个用户的每月订阅费用包括收费电话拨入费。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-125">If the standard subscription is purchased, toll dial-in cost will be included in the per-user monthly subscription cost.</span></span> 

- <span data-ttu-id="8ed2a-126">将为每个组织及其用户提供一组新的拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-126">A new set of dial-in phone numbers will be provided to each organization and its users.</span></span> <span data-ttu-id="8ed2a-127">若要查看 Microsoft 音频会议服务的地理覆盖范围, 请参阅[音频会议和通话计划的国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-127">To see the geographical coverage of Microsoft Audio Conferencing service, see [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).</span></span>
 
- <span data-ttu-id="8ed2a-128">已由使用第三方 ACP 启用的用户安排的会议将自动重新安排为包括 Microsoft 音频会议拨入信息。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-128">Meetings that have already been scheduled by users enabled with a third-party ACP will be automatically rescheduled to include Microsoft Audio Conferencing dial-in information.</span></span>
 
- <span data-ttu-id="8ed2a-129">每个会议的会议 Id 都是动态的, 这意味着每个会议都将拥有自己的专用会议 ID。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-129">The conference IDs of each meeting will be dynamic, meaning that each meeting will have its own dedicated conference ID.</span></span> <span data-ttu-id="8ed2a-130">动态会议 Id 提供了更高的安全性和更好的后端到后会议体验。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-130">Dynamic conference IDs provide enhanced security and an improved experience for back-to-back meetings.</span></span>

- <span data-ttu-id="8ed2a-131">该服务的所有使用均受音频会议服务使用条款的制约。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-131">All usage of the service is subject to the Audio Conferencing services use terms.</span></span> 

<span data-ttu-id="8ed2a-132">迁移到 Microsoft 音频会议非常简单, 只需在为服务获取许可证后的几个步骤中完成迁移即可。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-132">Migrating to Microsoft Audio Conferencing is simple, and it can be done in just a couple of steps after acquiring the licenses for the service.</span></span> <span data-ttu-id="8ed2a-133">若要了解如何迁移到 Microsoft 音频会议, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="8ed2a-133">To learn about how to migrate to Microsoft Audio Conferencing, see:</span></span>

- [<span data-ttu-id="8ed2a-134">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="8ed2a-134">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
<span data-ttu-id="8ed2a-135">**摘要：**</span><span class="sxs-lookup"><span data-stu-id="8ed2a-135">**Summary:**</span></span>

- <span data-ttu-id="8ed2a-136">迁移到 Microsoft 音频会议并在2021年7月31日之前完成迁移的组织将不会在该日期期间或之后看到对其服务的任何影响。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-136">Organizations that migrate to Microsoft Audio Conferencing and complete their migration before July 31, 2021, won’t see any impact to their service during or after that date.</span></span>

- <span data-ttu-id="8ed2a-137">若要了解有关迁移到 Microsoft 音频会议的详细信息, 请参阅[在 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-137">To learn more about migrating to Microsoft Audio Conferencing, see [Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md).</span></span> 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="8ed2a-138">路径 #2: 继续单独使用第三方音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="8ed2a-138">Path #2: Continue to separately use a third-party audio conferencing provider</span></span>

<span data-ttu-id="8ed2a-139">如果组织决定继续使用2021年7月31日的第三方 ACP, 将会受到服务影响, 因为第三方 ACP 的拨入信息将不再能够用于加入 Skype for business 会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-139">Organizations that decide to continue using a third-party ACP on and after July 31, 2021, will experience service impact because the third-party ACP dial-in information will no longer be able to be used to join the audio portion of a Skype for Business meeting.</span></span> 

<span data-ttu-id="8ed2a-140">为了防止某些参与者通过 VoIP 和其他参与者通过 VoIP 和其他参与者加入 Skype for Business 会议中的音频碎片, 我们建议这些组织在其用户的会议中禁用 VoIP ACP。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-140">To prevent the fragmentation of audio in Skype for Business meetings by having some participants joining via VoIP and other via the third-party ACP, it’s recommended for these organizations to disable using VoIP on their users’ meetings.</span></span> <span data-ttu-id="8ed2a-141">这样, 所有参与者都需要使用第三方 ACP 和会议的所有其他工作负荷 (如聊天或屏幕共享) 通过 Skype for business 继续支持会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-141">This way, all participants will need to join the audio portion of a meeting using the third-party ACP and all other workloads of the meeting (such as chat or screen sharing) can continue to be supported over Skype for Business.</span></span> 

- <span data-ttu-id="8ed2a-142">若要从给定组织者的所有会议中禁用 VoIP, 请通过 CsConferencingPolicy cmdlet 将其会议策略的 AllowIPAudio 参数设置为 false。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-142">To disable VoIP from all meetings of a given organizer, set the AllowIPAudio parameter of his or her Conferencing Policy to false via the Set-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="8ed2a-143">有关详细信息, 请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-143">For additional information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
 
<span data-ttu-id="8ed2a-144">根据日程安排和2021年7月31日起, 第三方 ACP 的拨入信息将不再自动包含在 Skype for Business 会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-144">In terms of scheduling, and as of July 31, 2021, the dial-in information of a third-party ACP will no longer be automatically included in Skype for Business meeting invites.</span></span> <span data-ttu-id="8ed2a-145">如果用户希望继续将此信息包含在会议的一部分中, 用户将需要手动在其 Skype for Business 会议邀请上添加拨入信息。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-145">Users will need to manually add the dial-in information on their Skype for Business meeting invites if they wish to continue including this information as part of their meetings.</span></span> 

<span data-ttu-id="8ed2a-146">请注意, 在2021年7月31日, 将不会自动重新安排用户的现有会议以删除任何第三方 ACP 的拨入信息。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-146">Please note that on July 31, 2021, the existing meetings of users will not be automatically rescheduled to remove any third-party ACP dial-in information.</span></span> <span data-ttu-id="8ed2a-147">决定为用户的会议启用 VoIP 的组织应考虑禁用其用户的第三方 ACP 的集成, 并使用会议迁移服务重新安排其会议以删除第三方音频从现有会议中会议拨入信息, 并在已计划的会议上阻止音频碎片。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-147">Organizations that decide to keep VoIP enabled for the meetings of their users should consider disabling the integration of third-party ACP for their users and reschedule their meetings using the meeting migration service to remove the third-party audio conferencing dial-in information from their existing meetings and prevent the fragmentation of audio on already-scheduled meetings.</span></span> 

- <span data-ttu-id="8ed2a-148">若要禁用给定组织者的第三方音频会议的集成, 请使用 CsUserAcp cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-148">To disable the integration of third-party audio conferencing for a given organizer, use the Remove-CsUserAcp cmdlet.</span></span> <span data-ttu-id="8ed2a-149">有关其他信息, 请参阅[Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-149">For additional information, see [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps).</span></span> 

- <span data-ttu-id="8ed2a-150">若要在禁用与第三方音频会议提供商的集成后, 自动重新安排用户的会议, 请参阅 "如何为用户手动运行会议迁移？"</span><span class="sxs-lookup"><span data-stu-id="8ed2a-150">To automatically reschedule the meetings of users after disabling the integration with a third-party audio conferencing provider, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="8ed2a-151">在[设置会议迁移服务 (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-151">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span> 

<span data-ttu-id="8ed2a-152">**摘要：**</span><span class="sxs-lookup"><span data-stu-id="8ed2a-152">**Summary:**</span></span>

- <span data-ttu-id="8ed2a-153">决定继续使用2021的第三方 ACP 的组织将受到影响, 因为第三方 ACP 无法用于加入 Skype for Business 会议, 新会议不会包含第三方 ACP 的拨入信息。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-153">Organizations that decide to continue using a third-party ACP on and after July 31, 2021, will be affected because a third-party ACP won’t be able to be used to join a Skype for Business meeting and new meetings will not include third-party ACP dial-in information.</span></span> 

- <span data-ttu-id="8ed2a-154">建议在2021年7月31日之前对所有受影响用户的所有会议禁用 VoIP, 以防止音频在通过 VoIP 和第三方 ACP 加入的参与者之间分段。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-154">It’s recommended that VoIP is disabled for all meetings of all affected users before July 31, 2021, to prevent the audio from being fragmented across participants joining via VoIP and via a third-party ACP.</span></span> 

    - <span data-ttu-id="8ed2a-155">若要从给定组织者的所有会议中禁用 VoIP, 请通过 CsConferencingPolicy cmdlet 将用户的会议策略的 AllowIPAudio 参数设置为 false。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-155">To disable VoIP from all meetings of a given organizer, set the AllowIPAudio parameter of the user’s Conferencing Policy to false via the Set-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="8ed2a-156">有关详细信息, 请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-156">For additional information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
 
- <span data-ttu-id="8ed2a-157">如果组织没有为所有会议禁用 VoIP, 则建议禁用用户使用 Skype for Business Online 与第三方 ACP 集成, 并重新安排其会议以删除第三方 ACP 拨入信息, 以阻止音频碎片。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-157">If an organization doesn’t disable VoIP for all meetings, it’s recommended for users to be disabled from using the Skype for Business Online integration with a third-party ACP and reschedule their meetings to remove the third-party ACP dial-in information to prevent fragmentation of audio.</span></span>

    - <span data-ttu-id="8ed2a-158">若要禁用给定组织者的第三方音频会议的集成, 请使用[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-158">To disable the integration of third-party audio conferencing for a given organizer, use the [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) cmdlet.</span></span> 

    - <span data-ttu-id="8ed2a-159">若要自动重新安排会议, 请参阅 "如何为用户手动运行会议迁移？"</span><span class="sxs-lookup"><span data-stu-id="8ed2a-159">To automatically reschedule the meetings, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="8ed2a-160">在[设置会议迁移服务 (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-160">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span>

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a><span data-ttu-id="8ed2a-161">路径 #3: 完全停止使用拨入式会议</span><span class="sxs-lookup"><span data-stu-id="8ed2a-161">Path #3: Stop using dial-in conferencing altogether</span></span>

<span data-ttu-id="8ed2a-162">决定完全停止使用电话拨入式会议的组织 (不是由 Microsoft 和第三方 ACP 提供) 都可以完全依赖 VoIP 来支持 Skype for business 会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-162">Organizations that decide to stop using dial-in conferencing completely (neither provided by Microsoft nor by a third-party ACP) can fully rely on VoIP to support the audio portion of a Skype for Business meeting.</span></span> 

<span data-ttu-id="8ed2a-163">这些组织将需要禁用其用户使用第三方音频会议提供商, 并使用会议迁移服务自动重新安排其会议以删除其电话拨入式会议信息。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-163">These organizations would need to disable their users from using a third-party audio conferencing provider and have their meetings automatically rescheduled using the meeting migration service to remove their dial-in conferencing information.</span></span> 

- <span data-ttu-id="8ed2a-164">若要禁用给定组织者的第三方音频会议的集成, 请使用 CsUserAcp cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-164">To disable the integration of third-party audio conferencing for a given organizer, use the Remove-CsUserAcp cmdlet.</span></span> <span data-ttu-id="8ed2a-165">有关其他信息, 请参阅[Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-165">For additional information, see [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps).</span></span> 

- <span data-ttu-id="8ed2a-166">若要在禁用与第三方音频会议提供商的集成后, 自动重新安排用户的会议, 请参阅 "如何为用户手动运行会议迁移？"</span><span class="sxs-lookup"><span data-stu-id="8ed2a-166">To automatically reschedule the meetings of users after disabling the integration with a third-party audio conferencing provider, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="8ed2a-167">在[设置会议迁移服务 (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-167">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span> 

<span data-ttu-id="8ed2a-168">**摘要：**</span><span class="sxs-lookup"><span data-stu-id="8ed2a-168">**Summary:**</span></span> 

- <span data-ttu-id="8ed2a-169">决定在 2021 7 月31日之前停止使用音频会议的组织不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-169">Organizations that decide to stop using audio conferencing altogether before July 31, 2021, will not be impacted.</span></span>

- <span data-ttu-id="8ed2a-170">若要禁用给定组织者的第三方音频会议的集成, 请使用 CsUserAcp cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-170">To disable the integration of third-party audio conferencing for a given organizer, use the Remove-CsUserAcp cmdlet.</span></span> <span data-ttu-id="8ed2a-171">有关其他信息, 请参阅[Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-171">For additional information, see [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps).</span></span> 

- <span data-ttu-id="8ed2a-172">若要在禁用与第三方音频会议提供商的集成后自动重新安排用户的会议, 请参阅 "如何为用户手动运行会议迁移？"</span><span class="sxs-lookup"><span data-stu-id="8ed2a-172">To automatically reschedule the meetings of users after disabling integration with third-party audio conferencing providers, see “How do I run Meeting Migration manually for a user?”</span></span> <span data-ttu-id="8ed2a-173">在[设置会议迁移服务 (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。</span><span class="sxs-lookup"><span data-stu-id="8ed2a-173">in [Setting up the Meeting Migration Service (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).</span></span>
