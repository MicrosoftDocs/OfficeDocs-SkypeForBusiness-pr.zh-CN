---
title: 使用 OneDrive for Business 和 SharePoint 进行会议录制
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何从 Microsoft 团队中的 OneDrive for Business 和 SharePoint 会议录制存储切换到 OneDrive for Business 和 SharePoint 会议录制。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce6c5cc546c3c2e8b8369247de38e0f734b9b467
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739220"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="0df0b-103">使用 OneDrive for Business 和 SharePoint 或流进行会议录制</span><span class="sxs-lookup"><span data-stu-id="0df0b-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="0df0b-104">使用 Microsoft Stream to OneDrive for Business 和 Microsoft SharePoint for 会议录制的更改将是一种分阶段方法。</span><span class="sxs-lookup"><span data-stu-id="0df0b-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>


|<span data-ttu-id="0df0b-105">日期</span><span class="sxs-lookup"><span data-stu-id="0df0b-105">Date</span></span>|<span data-ttu-id="0df0b-106">活动</span><span class="sxs-lookup"><span data-stu-id="0df0b-106">Event</span></span>|
|---|-----------------|
|<span data-ttu-id="0df0b-107">第4季度早些 CY20</span><span class="sxs-lookup"><span data-stu-id="0df0b-107">Early Q4 CY20</span></span>|<span data-ttu-id="0df0b-108">**OneDrive for business 和 SharePoint 上的团队会议录制可供选择加入或选择退出。**</span><span class="sxs-lookup"><span data-stu-id="0df0b-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="0df0b-109">租户管理员可以选择加入或退出 OneDrive for Business 和 SharePoint 设置 PowerShell 中的团队策略</span><span class="sxs-lookup"><span data-stu-id="0df0b-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="0df0b-110">第4季度中旬 CY20</span><span class="sxs-lookup"><span data-stu-id="0df0b-110">Mid Q4 CY20</span></span>|<span data-ttu-id="0df0b-111">**OneDrive for business 和 SharePoint 上的团队会议录制设置为未选择的租户的默认设置**</span><span class="sxs-lookup"><span data-stu-id="0df0b-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="0df0b-112">这是适用于大多数客户的推荐途径</span><span class="sxs-lookup"><span data-stu-id="0df0b-112">This is the  recommended path for most customers</span></span>|
|<span data-ttu-id="0df0b-113">第1季度 CY21</span><span class="sxs-lookup"><span data-stu-id="0df0b-113">Q1 CY21</span></span>|<span data-ttu-id="0df0b-114">**不再允许将团队会议录制保存到经典流**</span><span class="sxs-lookup"><span data-stu-id="0df0b-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="0df0b-115">所有租户均可将团队会议录制内容保存到 OneDrive for business 和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="0df0b-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|


<span data-ttu-id="0df0b-116">Microsoft 团队具有保存会议录制的新方法。</span><span class="sxs-lookup"><span data-stu-id="0df0b-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="0df0b-117">作为从经典 Microsoft Stream 过渡到 [新流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 microsoft 365 中的 microsoft OneDrive for Business 和 SharePoint 中，并提供许多好处。</span><span class="sxs-lookup"><span data-stu-id="0df0b-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive for Business and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="0df0b-118">使用 OneDrive for Business 和 SharePoint 存储录制的好处包括：</span><span class="sxs-lookup"><span data-stu-id="0df0b-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="0df0b-119">团队会议录制的保留策略 (TMR)  (S + C E5 autoretention 标签) </span><span class="sxs-lookup"><span data-stu-id="0df0b-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="0df0b-120">从 OneDrive for business 和 SharePoint 信息管理中获益</span><span class="sxs-lookup"><span data-stu-id="0df0b-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="0df0b-121">轻松设置权限和共享</span><span class="sxs-lookup"><span data-stu-id="0df0b-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="0df0b-122">仅具有明确共享的 (外部用户) 与来宾共享录制</span><span class="sxs-lookup"><span data-stu-id="0df0b-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="0df0b-123">请求访问流</span><span class="sxs-lookup"><span data-stu-id="0df0b-123">Request access flow</span></span>
- <span data-ttu-id="0df0b-124">提供 OneDrive for business 和 SharePoint 共享链接</span><span class="sxs-lookup"><span data-stu-id="0df0b-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="0df0b-125">增加了配额</span><span class="sxs-lookup"><span data-stu-id="0df0b-125">Increased quota</span></span>
- <span data-ttu-id="0df0b-126">会议录制更快地可用</span><span class="sxs-lookup"><span data-stu-id="0df0b-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="0df0b-127">**转到本地** 租户支持</span><span class="sxs-lookup"><span data-stu-id="0df0b-127">**Go local** tenant support</span></span>
- <span data-ttu-id="0df0b-128">多地区支持-录制存储在特定于该用户的区域中</span><span class="sxs-lookup"><span data-stu-id="0df0b-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="0df0b-129">将您自己的密钥 (BYOK) 支持</span><span class="sxs-lookup"><span data-stu-id="0df0b-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="0df0b-130">改进的记录质量和演讲者特性</span><span class="sxs-lookup"><span data-stu-id="0df0b-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="0df0b-131">需要考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="0df0b-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="0df0b-132">将有英语的隐藏式字幕和脚本。</span><span class="sxs-lookup"><span data-stu-id="0df0b-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="0df0b-133">您将不能搜索脚本或其内容。</span><span class="sxs-lookup"><span data-stu-id="0df0b-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="0df0b-134">你将无法编辑这些脚本，但你可以将标题切换为 "开/关"。</span><span class="sxs-lookup"><span data-stu-id="0df0b-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="0df0b-135">你可以控制你共享录制的人员，但不能阻止具有共享访问权限的用户下载录制。</span><span class="sxs-lookup"><span data-stu-id="0df0b-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="0df0b-136">录制完成后，你将不会收到电子邮件，但录制将在会议聊天完成后显示在会议聊天中。</span><span class="sxs-lookup"><span data-stu-id="0df0b-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="0df0b-137">这将比以前在流中更快的速度</span><span class="sxs-lookup"><span data-stu-id="0df0b-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="0df0b-138">有关详细信息，请观看 "会议录制"。</span><span class="sxs-lookup"><span data-stu-id="0df0b-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="0df0b-139">为 OneDrive for business 和 SharePoint 设置会议录制选项</span><span class="sxs-lookup"><span data-stu-id="0df0b-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

> [!Note]
> <span data-ttu-id="0df0b-140">"会议录制" 选项是 "团队" 策略级别的一个设置。</span><span class="sxs-lookup"><span data-stu-id="0df0b-140">The meeting recording option is a setting at the Teams policy level.</span></span> <span data-ttu-id="0df0b-141">以下示例显示了如何设置全局策略。</span><span class="sxs-lookup"><span data-stu-id="0df0b-141">The following example shows how to set the Global policy.</span></span> <span data-ttu-id="0df0b-142">请确保为你分配给用户的策略设置了 "会议录制" 选项。</span><span class="sxs-lookup"><span data-stu-id="0df0b-142">Make sure that you set the meeting recording option for the policy or policies that you've assigned to your users.</span></span> <span data-ttu-id="0df0b-143">团队会议策略更改需要一段时间才能传播。</span><span class="sxs-lookup"><span data-stu-id="0df0b-143">Teams meeting policy changes take awhile to propagate.</span></span> <span data-ttu-id="0df0b-144">在设置后的几个小时后再次查看，然后注销并再次登录。</span><span class="sxs-lookup"><span data-stu-id="0df0b-144">Check back after a few hours of setting it, then sign out and sign in again.</span></span>

1. <span data-ttu-id="0df0b-145">安装 Skype For Business Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0df0b-145">Install Skype For Business Online PowerShell.</span></span> 
<span data-ttu-id="0df0b-146">**注意**： Skype For Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="0df0b-146">**Note**: Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="0df0b-147">如果您使用的是最新的团队 PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="0df0b-147">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span> <span data-ttu-id="0df0b-148">请参阅 [管理与 PowerShell 的 Skype for Business Online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="0df0b-148">See [Manage Skype for Business Online with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).</span></span>

    <span data-ttu-id="0df0b-149">a.</span><span class="sxs-lookup"><span data-stu-id="0df0b-149">a.</span></span> <span data-ttu-id="0df0b-150">下载 [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="0df0b-150">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).</span></span> 

    <span data-ttu-id="0df0b-151">b.</span><span class="sxs-lookup"><span data-stu-id="0df0b-151">b.</span></span> <span data-ttu-id="0df0b-152">按照提示进行安装。</span><span class="sxs-lookup"><span data-stu-id="0df0b-152">Follow the prompts to install it.</span></span>

    <span data-ttu-id="0df0b-153">c.</span><span class="sxs-lookup"><span data-stu-id="0df0b-153">c.</span></span> <span data-ttu-id="0df0b-154">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="0df0b-154">Restart your machine.</span></span>

2. <span data-ttu-id="0df0b-155">以管理员身份启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0df0b-155">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="0df0b-156">导入 SkypeOnline 连接器并作为团队管理员登录。</span><span class="sxs-lookup"><span data-stu-id="0df0b-156">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. <span data-ttu-id="0df0b-157">使用 [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) 将团队会议策略设置为从流存储过渡到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df0b-157">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) to set a Teams Meeting Policy to transition from the Stream storage to OneDrive for Business and SharePoint.</span></span>

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="0df0b-158">选择退出 OneDrive for Business 和 SharePoint 以继续使用流</span><span class="sxs-lookup"><span data-stu-id="0df0b-158">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="0df0b-159">即使策略指示它已设置为 **流**，它也可能不会设置。</span><span class="sxs-lookup"><span data-stu-id="0df0b-159">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="0df0b-160">通常情况下，如果未设置策略，则默认设置为 " **流**"。</span><span class="sxs-lookup"><span data-stu-id="0df0b-160">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="0df0b-161">但是，如果你想要取消使用 SharePoint 或 OneDrive，请使用此新更改，然后必须将策略重置为 **流** ，以确保它是默认设置。</span><span class="sxs-lookup"><span data-stu-id="0df0b-161">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a><span data-ttu-id="0df0b-162">权限或基于角色的访问</span><span class="sxs-lookup"><span data-stu-id="0df0b-162">Permissions or role-based access</span></span>


|<span data-ttu-id="0df0b-163">会议类型</span><span class="sxs-lookup"><span data-stu-id="0df0b-163">Meeting type</span></span>                               | <span data-ttu-id="0df0b-164">单击 "记录"</span><span class="sxs-lookup"><span data-stu-id="0df0b-164">Who clicked on Record?</span></span>| <span data-ttu-id="0df0b-165">录制的土地在哪里？</span><span class="sxs-lookup"><span data-stu-id="0df0b-165">Where does the recording land?</span></span>                               |<span data-ttu-id="0df0b-166">谁有权访问？</span><span class="sxs-lookup"><span data-stu-id="0df0b-166">Who has access?</span></span> <span data-ttu-id="0df0b-167">R/W、R 或共享</span><span class="sxs-lookup"><span data-stu-id="0df0b-167">R/W, R or sharing</span></span>                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="0df0b-168">与内部团体的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="0df0b-168">1:1 call with internal parties</span></span>             |<span data-ttu-id="0df0b-169">呼叫者</span><span class="sxs-lookup"><span data-stu-id="0df0b-169">Caller</span></span>                 |<span data-ttu-id="0df0b-170">呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="0df0b-170">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="0df0b-171">-呼叫方是所有者、具有被调用方的完全权限 (如果在同一租户) 中具有只读访问权限，则在不同租户) 没有访问权限的情况下，不 (共享访问被调用方。</span><span class="sxs-lookup"><span data-stu-id="0df0b-171">- Caller is owner, has full rights  - Callee (if in the same tenant) has read only access, no sharing access -  Callee (if in different tenant) has no access.</span></span> <span data-ttu-id="0df0b-172">调用方必须将其共享给被呼叫方</span><span class="sxs-lookup"><span data-stu-id="0df0b-172">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="0df0b-173">与内部团体的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="0df0b-173">1:1 call with internal parties</span></span>             |<span data-ttu-id="0df0b-174">被叫方</span><span class="sxs-lookup"><span data-stu-id="0df0b-174">Callee</span></span>                 |<span data-ttu-id="0df0b-175">被呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="0df0b-175">Callee’s OneDrive for Business account</span></span>                        |<span data-ttu-id="0df0b-176">-被调用方是所有者、具有完全权限-调用方 (如果在同一租户中具有只读访问权限，则没有共享访问权限，调用方 (如果在不同租户) 没有访问权限。</span><span class="sxs-lookup"><span data-stu-id="0df0b-176">- Callee is owner, has full rights - Caller (if in the same tenant has read only access, no sharing access - Caller (if in different tenant) has no access.</span></span> <span data-ttu-id="0df0b-177">被呼叫方必须将其共享给被呼叫方</span><span class="sxs-lookup"><span data-stu-id="0df0b-177">Callee must share it to the Callee</span></span>|
|<span data-ttu-id="0df0b-178">使用外部通话的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="0df0b-178">1:1 call with an external call</span></span>             |<span data-ttu-id="0df0b-179">呼叫者</span><span class="sxs-lookup"><span data-stu-id="0df0b-179">Caller</span></span>                 |<span data-ttu-id="0df0b-180">呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="0df0b-180">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="0df0b-181">-呼叫方为所有者，具有完全权限的被调用方没有访问权限。</span><span class="sxs-lookup"><span data-stu-id="0df0b-181">- Caller is owner, has full rights - Callee has no access.</span></span> <span data-ttu-id="0df0b-182">调用方必须将其共享给被呼叫方</span><span class="sxs-lookup"><span data-stu-id="0df0b-182">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="0df0b-183">使用外部通话的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="0df0b-183">1:1 call with an external call</span></span>             |<span data-ttu-id="0df0b-184">被叫方</span><span class="sxs-lookup"><span data-stu-id="0df0b-184">Callee</span></span>                 |<span data-ttu-id="0df0b-185">呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="0df0b-185">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="0df0b-186">-被调用方是所有者，具有完全权限-呼叫方没有访问权限。</span><span class="sxs-lookup"><span data-stu-id="0df0b-186">- Callee is owner, has full rights - Caller has no access.</span></span> <span data-ttu-id="0df0b-187">被呼叫方必须将其共享给呼叫方</span><span class="sxs-lookup"><span data-stu-id="0df0b-187">Callee must share it to the Caller</span></span>|
|<span data-ttu-id="0df0b-188">群组通话</span><span class="sxs-lookup"><span data-stu-id="0df0b-188">Group call</span></span>                                 |<span data-ttu-id="0df0b-189">任何呼叫成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-189">Any member of the call</span></span> |<span data-ttu-id="0df0b-190">单击记录的 OneDrive for Business 帐户的成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-190">Member who clicked on Record’s OneDrive for Business account</span></span>  |<span data-ttu-id="0df0b-191">-单击记录的成员具有完全权限-来自同一租户的其他成员具有读取权限-来自不同租户的其他成员没有权限。</span><span class="sxs-lookup"><span data-stu-id="0df0b-191">- Member who clicked on Record has full rights - Other members from the same tenant have Read rights - Other members from different tenant have no rights to it.</span></span>|
|<span data-ttu-id="0df0b-192">即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="0df0b-192">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="0df0b-193">组织者</span><span class="sxs-lookup"><span data-stu-id="0df0b-193">Organizer</span></span>              |<span data-ttu-id="0df0b-194">组织者的 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="0df0b-194">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="0df0b-195">-组织者对录制具有完全权限-会议的所有其他成员都具有 "读取" 访问权限</span><span class="sxs-lookup"><span data-stu-id="0df0b-195">- Organizer has full rights to the recording - All other members of the meeting have read access</span></span>|
|<span data-ttu-id="0df0b-196">即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="0df0b-196">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="0df0b-197">其他会议成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-197">Other meeting member</span></span>   |<span data-ttu-id="0df0b-198">单击记录的成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-198">Member who clicked on Record</span></span>                                  |<span data-ttu-id="0df0b-199">-单击记录的成员对录制具有完全权限-组织者具有编辑权限，并且可以共享-所有其他成员都具有读取访问权限</span><span class="sxs-lookup"><span data-stu-id="0df0b-199">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members have read access</span></span>|
|<span data-ttu-id="0df0b-200">与外部用户进行即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="0df0b-200">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="0df0b-201">组织者</span><span class="sxs-lookup"><span data-stu-id="0df0b-201">Organizer</span></span>              |<span data-ttu-id="0df0b-202">组织者的 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="0df0b-202">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="0df0b-203">-组织者对录制具有完全权限，与组织者相同的租户的所有其他成员都具有 "读取" 权限-所有其他外部成员都不具有访问权限，并且组织者必须将其共享</span><span class="sxs-lookup"><span data-stu-id="0df0b-203">- Organizer has full rights to the recording - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="0df0b-204">与外部用户进行即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="0df0b-204">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="0df0b-205">其他会议成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-205">Other meeting member</span></span>   |<span data-ttu-id="0df0b-206">单击记录的成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-206">Member who clicked on Record</span></span>                                  |<span data-ttu-id="0df0b-207">-单击记录的成员对录制具有完全权限-组织者具有编辑权限，并且可以从与组织者相同的租户中共享会议的所有其他成员，并且所有其他外部成员都不具有访问权限，并且组织者必须将其共享</span><span class="sxs-lookup"><span data-stu-id="0df0b-207">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="0df0b-208">频道会议</span><span class="sxs-lookup"><span data-stu-id="0df0b-208">Channel meeting</span></span>                            |<span data-ttu-id="0df0b-209">频道成员</span><span class="sxs-lookup"><span data-stu-id="0df0b-209">Channel Member</span></span>         |<span data-ttu-id="0df0b-210">该频道的团队 SharePoint 位置</span><span class="sxs-lookup"><span data-stu-id="0df0b-210">Teams' SharePoint location for that channel</span></span>                   |<span data-ttu-id="0df0b-211">-单击记录的成员对录制具有编辑权限-其他成员的每个权限都基于通道 SharePoint 权限</span><span class="sxs-lookup"><span data-stu-id="0df0b-211">- Member who clicked on Record has edit rights to the recording  - Every other member’s permissions are based off of the Channel SharePoint permissions</span></span>|


## <a name="frequently-asked-questions"></a><span data-ttu-id="0df0b-212">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0df0b-212">Frequently asked questions</span></span>

<span data-ttu-id="0df0b-213">**会议录制将存储在何处？**</span><span class="sxs-lookup"><span data-stu-id="0df0b-213">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="0df0b-214">对于非频道会议，录制内容存储在属于开始会议录制人员**Recordings**的 OneDrive for business 的最高级别的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0df0b-214">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive for Business that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="0df0b-215">上例</span><span class="sxs-lookup"><span data-stu-id="0df0b-215">Example:</span></span>

  <span data-ttu-id="0df0b-216"><i>录像机的 OneDrive For business</i> /**录制**</span><span class="sxs-lookup"><span data-stu-id="0df0b-216"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="0df0b-217">对于频道会议，录制内容存储在名为 " **录制**" 的文件夹中的 "团队网站" 文档库中。</span><span class="sxs-lookup"><span data-stu-id="0df0b-217">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="0df0b-218">上例</span><span class="sxs-lookup"><span data-stu-id="0df0b-218">Example:</span></span>

  <span data-ttu-id="0df0b-219"><i>团队名称-频道名称</i> /**文档** /**录制**</span><span class="sxs-lookup"><span data-stu-id="0df0b-219"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="0df0b-220">**如何处理以前员工的录制？**</span><span class="sxs-lookup"><span data-stu-id="0df0b-220">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="0df0b-221">由于视频与 OneDrive for Business 和 SharePoint 中的任何其他文件一样，在员工离职后处理所有权和保留将遵循正常的 [OneDrive for business 和 sharepoint 进程]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。</span><span class="sxs-lookup"><span data-stu-id="0df0b-221">Since videos are just like any other file in OneDrive for Business and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive for Business and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="0df0b-222">**哪些人具有查看会议录制的权限？**</span><span class="sxs-lookup"><span data-stu-id="0df0b-222">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="0df0b-223">对于非频道会议，除外部用户之外的所有会议被邀请者都将自动获取个人共享链接。</span><span class="sxs-lookup"><span data-stu-id="0df0b-223">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="0df0b-224">外部用户需要通过会议组织者或启动会议录制的人员显式添加到共享列表。</span><span class="sxs-lookup"><span data-stu-id="0df0b-224">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="0df0b-225">对于频道会议，权限继承自频道中的 "所有者" 和 "成员列表" 列表。</span><span class="sxs-lookup"><span data-stu-id="0df0b-225">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="0df0b-226">**如何管理脚本？**</span><span class="sxs-lookup"><span data-stu-id="0df0b-226">**How can I manage transcripts?**</span></span>

<span data-ttu-id="0df0b-227">选择加入此预览的客户将不会在其团队会议录制中提供隐藏字幕，这些标题将迁移到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0df0b-227">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive for Business and SharePoint.</span></span><span data-ttu-id="0df0b-228">我们正在努力在2020年10月向会议录制添加字幕，以英文隐藏的字幕开始。</span><span class="sxs-lookup"><span data-stu-id="0df0b-228">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="0df0b-229">对于已选择加入以允许在[团队云录制](cloud-recording.md)中介绍的内容的客户，将在团队会议录制中提供隐藏式字幕</span><span class="sxs-lookup"><span data-stu-id="0df0b-229">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="0df0b-230">字幕有助于为所有功能的查看者创建包含内容。</span><span class="sxs-lookup"><span data-stu-id="0df0b-230">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="0df0b-231">作为所有者，你可以隐藏字幕，但除非你删除团队中的标题，否则仍可在团队中使用记录。</span><span class="sxs-lookup"><span data-stu-id="0df0b-231">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="0df0b-232">了解 [如何打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="0df0b-232">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="0df0b-233">录制会议时，从录制会议的60天起，团队会议录制支持隐藏式字幕。</span><span class="sxs-lookup"><span data-stu-id="0df0b-233">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="0df0b-234">如果团队会议录制从其原始位置移动或复制到 OneDrive 或 SharePoint 上的原始位置，则不会完全支持隐藏式字幕。</span><span class="sxs-lookup"><span data-stu-id="0df0b-234">Closed captions are not fully supported if the Teams Meeting Recording is moved or copied from its original location on OneDrive or SharePoint.</span></span>

<span data-ttu-id="0df0b-235">**我的存储配额将受到怎样的影响**</span><span class="sxs-lookup"><span data-stu-id="0df0b-235">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="0df0b-236">工作组会议录制文件实时在 OneDrive for business 和 SharePoint 中，并包含在这些服务的配额中。</span><span class="sxs-lookup"><span data-stu-id="0df0b-236">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="0df0b-237">请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for business 配额] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="0df0b-237">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="0df0b-238">**如何播放团队会议录制？**</span><span class="sxs-lookup"><span data-stu-id="0df0b-238">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="0df0b-239">你的视频将在 OneDrive for business 或 SharePoint 的视频播放器上播放，具体取决于你访问该文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0df0b-239">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="0df0b-240">**如果你计划将会弃用添加到 Stream，现有视频是否保持原样和持续多长时间？**</span><span class="sxs-lookup"><span data-stu-id="0df0b-240">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="0df0b-241">作为平台的流在不久的将来不会被弃用。</span><span class="sxs-lookup"><span data-stu-id="0df0b-241">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="0df0b-242">在开始迁移之前，当前实时流中的视频将一直保留。</span><span class="sxs-lookup"><span data-stu-id="0df0b-242">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="0df0b-243">迁移后，这些视频也将迁移到 ODSP。</span><span class="sxs-lookup"><span data-stu-id="0df0b-243">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="0df0b-244">有关详细信息，请查看 [此处](https://docs.microsoft.com/stream/streamnew/classic-migration) 。</span><span class="sxs-lookup"><span data-stu-id="0df0b-244">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
