---
title: 将 OneDrive 和 SharePoint 用于会议录制
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
ms.openlocfilehash: 624dcb4f99bc8ae2b83a1b8f62917ac0a5701888
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486767"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="7608c-103">使用 OneDrive for Business 和 SharePoint 或流进行会议录制</span><span class="sxs-lookup"><span data-stu-id="7608c-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="7608c-104">使用 Microsoft Stream to OneDrive for Business 和 Microsoft SharePoint for 会议录制的更改将是一种分阶段方法。</span><span class="sxs-lookup"><span data-stu-id="7608c-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>


|<span data-ttu-id="7608c-105">日期</span><span class="sxs-lookup"><span data-stu-id="7608c-105">Date</span></span>|<span data-ttu-id="7608c-106">活动</span><span class="sxs-lookup"><span data-stu-id="7608c-106">Event</span></span>|
|---|-----------------|
|<span data-ttu-id="7608c-107">第4季度早些 CY20</span><span class="sxs-lookup"><span data-stu-id="7608c-107">Early Q4 CY20</span></span>|<span data-ttu-id="7608c-108">**OneDrive for business 和 SharePoint 上的团队会议录制可供选择加入或选择退出。**</span><span class="sxs-lookup"><span data-stu-id="7608c-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="7608c-109">租户管理员可以选择加入或退出 OneDrive for Business 和 SharePoint 设置 PowerShell 中的团队策略</span><span class="sxs-lookup"><span data-stu-id="7608c-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="7608c-110">第4季度中旬 CY20</span><span class="sxs-lookup"><span data-stu-id="7608c-110">Mid Q4 CY20</span></span>|<span data-ttu-id="7608c-111">**OneDrive for business 和 SharePoint 上的团队会议录制设置为未选择的租户的默认设置**</span><span class="sxs-lookup"><span data-stu-id="7608c-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="7608c-112">这是适用于大多数客户的推荐途径</span><span class="sxs-lookup"><span data-stu-id="7608c-112">This is the  recommended path for most customers</span></span>|
|<span data-ttu-id="7608c-113">第1季度 CY21</span><span class="sxs-lookup"><span data-stu-id="7608c-113">Q1 CY21</span></span>|<span data-ttu-id="7608c-114">**不再允许将团队会议录制保存到经典流**</span><span class="sxs-lookup"><span data-stu-id="7608c-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="7608c-115">所有租户均可将团队会议录制内容保存到 OneDrive for business 和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="7608c-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|


<span data-ttu-id="7608c-116">Microsoft 团队具有保存会议录制的新方法。</span><span class="sxs-lookup"><span data-stu-id="7608c-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="7608c-117">作为从经典 Microsoft Stream 过渡到 [新流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 microsoft 365 中的 microsoft OneDrive 和 SharePoint 上并提供许多好处。</span><span class="sxs-lookup"><span data-stu-id="7608c-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="7608c-118">使用 OneDrive for Business 和 SharePoint 存储录制的好处包括：</span><span class="sxs-lookup"><span data-stu-id="7608c-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="7608c-119">团队会议录制的保留策略 (TMR)  (S + C E5 autoretention 标签) </span><span class="sxs-lookup"><span data-stu-id="7608c-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="7608c-120">从 OneDrive for business 和 SharePoint 信息管理中获益</span><span class="sxs-lookup"><span data-stu-id="7608c-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="7608c-121">轻松设置权限和共享</span><span class="sxs-lookup"><span data-stu-id="7608c-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="7608c-122">仅具有明确共享的 (外部用户) 与来宾共享录制</span><span class="sxs-lookup"><span data-stu-id="7608c-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="7608c-123">请求访问流</span><span class="sxs-lookup"><span data-stu-id="7608c-123">Request access flow</span></span>
- <span data-ttu-id="7608c-124">提供 OneDrive for business 和 SharePoint 共享链接</span><span class="sxs-lookup"><span data-stu-id="7608c-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="7608c-125">增加了配额</span><span class="sxs-lookup"><span data-stu-id="7608c-125">Increased quota</span></span>
- <span data-ttu-id="7608c-126">会议录制更快地可用</span><span class="sxs-lookup"><span data-stu-id="7608c-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="7608c-127">**转到本地** 租户支持</span><span class="sxs-lookup"><span data-stu-id="7608c-127">**Go local** tenant support</span></span>
- <span data-ttu-id="7608c-128">多地区支持-录制存储在特定于该用户的区域中</span><span class="sxs-lookup"><span data-stu-id="7608c-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="7608c-129">将您自己的密钥 (BYOK) 支持</span><span class="sxs-lookup"><span data-stu-id="7608c-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="7608c-130">改进的记录质量和演讲者特性</span><span class="sxs-lookup"><span data-stu-id="7608c-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="7608c-131">需要考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="7608c-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="7608c-132">将有英语的隐藏式字幕和脚本。</span><span class="sxs-lookup"><span data-stu-id="7608c-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="7608c-133">您将不能搜索脚本或其内容。</span><span class="sxs-lookup"><span data-stu-id="7608c-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="7608c-134">你将无法编辑这些脚本，但你可以将标题切换为 "开/关"。</span><span class="sxs-lookup"><span data-stu-id="7608c-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="7608c-135">你可以控制你共享录制的人员，但不能阻止具有共享访问权限的用户下载录制。</span><span class="sxs-lookup"><span data-stu-id="7608c-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="7608c-136">录制完成后，你将不会收到电子邮件，但录制将在会议聊天完成后显示在会议聊天中。</span><span class="sxs-lookup"><span data-stu-id="7608c-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="7608c-137">这将比以前在流中更快的速度</span><span class="sxs-lookup"><span data-stu-id="7608c-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="7608c-138">有关详细信息，请观看 "会议录制"。</span><span class="sxs-lookup"><span data-stu-id="7608c-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="7608c-139">为 OneDrive for business 和 SharePoint 设置会议录制选项</span><span class="sxs-lookup"><span data-stu-id="7608c-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="7608c-140">安装 Skype For Business Online PowerShell 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7608c-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="7608c-141">a.</span><span class="sxs-lookup"><span data-stu-id="7608c-141">a.</span></span> <span data-ttu-id="7608c-142">下载 [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="7608c-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="7608c-143">b.</span><span class="sxs-lookup"><span data-stu-id="7608c-143">b.</span></span> <span data-ttu-id="7608c-144">按照提示进行安装。</span><span class="sxs-lookup"><span data-stu-id="7608c-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="7608c-145">c.</span><span class="sxs-lookup"><span data-stu-id="7608c-145">c.</span></span> <span data-ttu-id="7608c-146">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="7608c-146">Restart your machine.</span></span>

2. <span data-ttu-id="7608c-147">以管理员身份启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7608c-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="7608c-148">导入 SkypeOnline 连接器并作为团队管理员登录。</span><span class="sxs-lookup"><span data-stu-id="7608c-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="7608c-149">使用 [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 设置团队会议策略以从流存储切换到 ODSP。</span><span class="sxs-lookup"><span data-stu-id="7608c-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="7608c-150">选择退出 OneDrive for Business 和 SharePoint 以继续使用流</span><span class="sxs-lookup"><span data-stu-id="7608c-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="7608c-151">即使策略指示它已设置为 **流**，它也可能不会设置。</span><span class="sxs-lookup"><span data-stu-id="7608c-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="7608c-152">通常情况下，如果未设置策略，则默认设置为 " **流**"。</span><span class="sxs-lookup"><span data-stu-id="7608c-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="7608c-153">但是，如果你想要取消使用 SharePoint 或 OneDrive，请使用此新更改，然后必须将策略重置为 **流** ，以确保它是默认设置。</span><span class="sxs-lookup"><span data-stu-id="7608c-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a><span data-ttu-id="7608c-154">权限或基于角色的访问</span><span class="sxs-lookup"><span data-stu-id="7608c-154">Permissions or role-based access</span></span>


|<span data-ttu-id="7608c-155">会议类型</span><span class="sxs-lookup"><span data-stu-id="7608c-155">Meeting type</span></span>                               | <span data-ttu-id="7608c-156">单击 "记录"</span><span class="sxs-lookup"><span data-stu-id="7608c-156">Who clicked on Record?</span></span>| <span data-ttu-id="7608c-157">录制的土地在哪里？</span><span class="sxs-lookup"><span data-stu-id="7608c-157">Where does the recording land?</span></span>                               |<span data-ttu-id="7608c-158">谁有权访问？</span><span class="sxs-lookup"><span data-stu-id="7608c-158">Who has access?</span></span> <span data-ttu-id="7608c-159">R/W、R 或共享</span><span class="sxs-lookup"><span data-stu-id="7608c-159">R/W, R or sharing</span></span>                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="7608c-160">与内部团体的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="7608c-160">1:1 call with internal parties</span></span>             |<span data-ttu-id="7608c-161">呼叫者</span><span class="sxs-lookup"><span data-stu-id="7608c-161">Caller</span></span>                 |<span data-ttu-id="7608c-162">呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="7608c-162">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="7608c-163">-呼叫方是所有者、具有被调用方的完全权限 (如果在同一租户) 中具有只读访问权限，则在不同租户) 没有访问权限的情况下，不 (共享访问被调用方。</span><span class="sxs-lookup"><span data-stu-id="7608c-163">- Caller is owner, has full rights  - Callee (if in the same tenant) has read only access, no sharing access -  Callee (if in different tenant) has no access.</span></span> <span data-ttu-id="7608c-164">调用方必须将其共享给被呼叫方</span><span class="sxs-lookup"><span data-stu-id="7608c-164">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="7608c-165">与内部团体的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="7608c-165">1:1 call with internal parties</span></span>             |<span data-ttu-id="7608c-166">被叫方</span><span class="sxs-lookup"><span data-stu-id="7608c-166">Callee</span></span>                 |<span data-ttu-id="7608c-167">被呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="7608c-167">Callee’s OneDrive for Business account</span></span>                        |<span data-ttu-id="7608c-168">-被调用方是所有者、具有完全权限-调用方 (如果在同一租户中具有只读访问权限，则没有共享访问权限，调用方 (如果在不同租户) 没有访问权限。</span><span class="sxs-lookup"><span data-stu-id="7608c-168">- Callee is owner, has full rights - Caller (if in the same tenant has read only access, no sharing access - Caller (if in different tenant) has no access.</span></span> <span data-ttu-id="7608c-169">被呼叫方必须将其共享给被呼叫方</span><span class="sxs-lookup"><span data-stu-id="7608c-169">Callee must share it to the Callee</span></span>|
|<span data-ttu-id="7608c-170">使用外部通话的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="7608c-170">1:1 call with an external call</span></span>             |<span data-ttu-id="7608c-171">呼叫者</span><span class="sxs-lookup"><span data-stu-id="7608c-171">Caller</span></span>                 |<span data-ttu-id="7608c-172">呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="7608c-172">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="7608c-173">-呼叫方为所有者，具有完全权限的被调用方没有访问权限。</span><span class="sxs-lookup"><span data-stu-id="7608c-173">- Caller is owner, has full rights - Callee has no access.</span></span> <span data-ttu-id="7608c-174">调用方必须将其共享给被呼叫方</span><span class="sxs-lookup"><span data-stu-id="7608c-174">Caller must share it to the Callee</span></span>|
|<span data-ttu-id="7608c-175">使用外部通话的1:1 通话</span><span class="sxs-lookup"><span data-stu-id="7608c-175">1:1 call with an external call</span></span>             |<span data-ttu-id="7608c-176">被叫方</span><span class="sxs-lookup"><span data-stu-id="7608c-176">Callee</span></span>                 |<span data-ttu-id="7608c-177">呼叫者的 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="7608c-177">Caller’s OneDrive for Business account</span></span>                        |<span data-ttu-id="7608c-178">-被调用方是所有者，具有完全权限-呼叫方没有访问权限。</span><span class="sxs-lookup"><span data-stu-id="7608c-178">- Callee is owner, has full rights - Caller has no access.</span></span> <span data-ttu-id="7608c-179">被呼叫方必须将其共享给呼叫方</span><span class="sxs-lookup"><span data-stu-id="7608c-179">Callee must share it to the Caller</span></span>|
|<span data-ttu-id="7608c-180">群组通话</span><span class="sxs-lookup"><span data-stu-id="7608c-180">Group call</span></span>                                 |<span data-ttu-id="7608c-181">任何呼叫成员</span><span class="sxs-lookup"><span data-stu-id="7608c-181">Any member of the call</span></span> |<span data-ttu-id="7608c-182">单击记录的 OneDrive for Business 帐户的成员</span><span class="sxs-lookup"><span data-stu-id="7608c-182">Member who clicked on Record’s OneDrive for Business account</span></span>  |<span data-ttu-id="7608c-183">-单击 "记录" 的成员具有完全权限-来自同一租户的其他成员具有 "读取" 权限，其他成员对于其他成员没有权限。</span><span class="sxs-lookup"><span data-stu-id="7608c-183">- Member who clicked on Record has full rights - Other members from the same tenant have Read rights - Other members for different have no rights to it.</span></span>|
|<span data-ttu-id="7608c-184">即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="7608c-184">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="7608c-185">组织者</span><span class="sxs-lookup"><span data-stu-id="7608c-185">Organizer</span></span>              |<span data-ttu-id="7608c-186">组织者的 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="7608c-186">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="7608c-187">-组织者对录制具有完全权限-会议的所有其他成员都具有 "读取" 访问权限</span><span class="sxs-lookup"><span data-stu-id="7608c-187">- Organizer has full rights to the recording - All other members of the meeting have read access</span></span>|
|<span data-ttu-id="7608c-188">即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="7608c-188">Adhoc/Scheduled meeting</span></span>                    |<span data-ttu-id="7608c-189">其他会议成员</span><span class="sxs-lookup"><span data-stu-id="7608c-189">Other meeting member</span></span>   |<span data-ttu-id="7608c-190">单击记录的成员</span><span class="sxs-lookup"><span data-stu-id="7608c-190">Member who clicked on Record</span></span>                                  |<span data-ttu-id="7608c-191">-单击记录的成员对录制具有完全权限-组织者具有编辑权限，并且可以共享-所有其他成员都具有读取访问权限</span><span class="sxs-lookup"><span data-stu-id="7608c-191">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members have read access</span></span>|
|<span data-ttu-id="7608c-192">与外部用户进行即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="7608c-192">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="7608c-193">组织者</span><span class="sxs-lookup"><span data-stu-id="7608c-193">Organizer</span></span>              |<span data-ttu-id="7608c-194">组织者的 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="7608c-194">Organizer’s OneDrive for Business account</span></span>                     |<span data-ttu-id="7608c-195">-组织者对录制具有完全权限，与组织者相同的租户的所有其他成员都具有 "读取" 权限-所有其他外部成员都不具有访问权限，并且组织者必须将其共享</span><span class="sxs-lookup"><span data-stu-id="7608c-195">- Organizer has full rights to the recording - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="7608c-196">与外部用户进行即席/计划会议</span><span class="sxs-lookup"><span data-stu-id="7608c-196">Adhoc/Scheduled meeting with external users</span></span>|<span data-ttu-id="7608c-197">其他会议成员</span><span class="sxs-lookup"><span data-stu-id="7608c-197">Other meeting member</span></span>   |<span data-ttu-id="7608c-198">单击记录的成员</span><span class="sxs-lookup"><span data-stu-id="7608c-198">Member who clicked on Record</span></span>                                  |<span data-ttu-id="7608c-199">-单击记录的成员对录制具有完全权限-组织者具有编辑权限，并且可以从与组织者相同的租户中共享会议的所有其他成员，并且所有其他外部成员都不具有访问权限，并且组织者必须将其共享</span><span class="sxs-lookup"><span data-stu-id="7608c-199">- Member who clicked on Record has full rights to the recording - Organizer has edit rights and can share - All other members of the meeting from the same tenant as the organizer have read access - All other external members have no access and the Organizer must share it to them</span></span>|
|<span data-ttu-id="7608c-200">频道会议</span><span class="sxs-lookup"><span data-stu-id="7608c-200">Channel meeting</span></span>                            |<span data-ttu-id="7608c-201">频道成员</span><span class="sxs-lookup"><span data-stu-id="7608c-201">Channel Member</span></span>         |<span data-ttu-id="7608c-202">该频道的团队 SharePoint 位置</span><span class="sxs-lookup"><span data-stu-id="7608c-202">Teams' SharePoint location for that channel</span></span>                   |<span data-ttu-id="7608c-203">-单击记录的成员对录制具有编辑权限-其他成员的每个权限都基于通道 SharePoint 权限</span><span class="sxs-lookup"><span data-stu-id="7608c-203">- Member who clicked on Record has edit rights to the recording  - Every other member’s permissions are based off of the Channel SharePoint permissions</span></span>|


## <a name="frequently-asked-questions"></a><span data-ttu-id="7608c-204">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="7608c-204">Frequently asked questions</span></span>

<span data-ttu-id="7608c-205">**会议录制将存储在何处？**</span><span class="sxs-lookup"><span data-stu-id="7608c-205">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="7608c-206">对于非频道会议，录制将存储在属于已启动会议录制 **的人员** 的 OneDrive 的最高级别的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7608c-206">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="7608c-207">上例</span><span class="sxs-lookup"><span data-stu-id="7608c-207">Example:</span></span>

  <span data-ttu-id="7608c-208"><i>录像机的 OneDrive For business</i> /**录制**</span><span class="sxs-lookup"><span data-stu-id="7608c-208"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="7608c-209">对于频道会议，录制内容存储在名为 " **录制**" 的文件夹中的 "团队网站" 文档库中。</span><span class="sxs-lookup"><span data-stu-id="7608c-209">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="7608c-210">上例</span><span class="sxs-lookup"><span data-stu-id="7608c-210">Example:</span></span>

  <span data-ttu-id="7608c-211"><i>团队名称-频道名称</i> /**文档** /**录制**</span><span class="sxs-lookup"><span data-stu-id="7608c-211"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="7608c-212">**如何处理以前员工的录制？**</span><span class="sxs-lookup"><span data-stu-id="7608c-212">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="7608c-213">由于视频与 OneDrive 和 SharePoint 中的任何其他文件一样，在员工离职后处理所有权和保留将遵循正常的 [OneDrive 和 sharepoint 进程]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。</span><span class="sxs-lookup"><span data-stu-id="7608c-213">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="7608c-214">**哪些人具有查看会议录制的权限？**</span><span class="sxs-lookup"><span data-stu-id="7608c-214">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="7608c-215">对于非频道会议，除外部用户之外的所有会议被邀请者都将自动获取个人共享链接。</span><span class="sxs-lookup"><span data-stu-id="7608c-215">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="7608c-216">外部用户需要通过会议组织者或启动会议录制的人员显式添加到共享列表。</span><span class="sxs-lookup"><span data-stu-id="7608c-216">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="7608c-217">对于频道会议，权限继承自频道中的 "所有者" 和 "成员列表" 列表。</span><span class="sxs-lookup"><span data-stu-id="7608c-217">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="7608c-218">**如何管理脚本？**</span><span class="sxs-lookup"><span data-stu-id="7608c-218">**How can I manage transcripts?**</span></span>

<span data-ttu-id="7608c-219">选择加入此预览的客户将不会在其团队会议录制中提供已迁移到 OneDrive 和 SharePoint 的隐藏字幕。</span><span class="sxs-lookup"><span data-stu-id="7608c-219">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="7608c-220">我们正在努力在2020年10月向会议录制添加字幕，以英文隐藏的字幕开始。</span><span class="sxs-lookup"><span data-stu-id="7608c-220">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="7608c-221">对于已选择加入以允许在[团队云录制](cloud-recording.md)中介绍的内容的客户，将在团队会议录制中提供隐藏式字幕</span><span class="sxs-lookup"><span data-stu-id="7608c-221">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="7608c-222">字幕有助于为所有功能的查看者创建包含内容。</span><span class="sxs-lookup"><span data-stu-id="7608c-222">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="7608c-223">作为所有者，你可以隐藏字幕，但除非你删除团队中的标题，否则仍可在团队中使用记录。</span><span class="sxs-lookup"><span data-stu-id="7608c-223">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="7608c-224">了解 [如何打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="7608c-224">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="7608c-225">录制会议时，从录制会议的60天起，团队会议录制支持隐藏式字幕。</span><span class="sxs-lookup"><span data-stu-id="7608c-225">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="7608c-226">**我的存储配额将受到怎样的影响**</span><span class="sxs-lookup"><span data-stu-id="7608c-226">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="7608c-227">工作组会议录制文件实时在 OneDrive for business 和 SharePoint 中，并包含在这些服务的配额中。</span><span class="sxs-lookup"><span data-stu-id="7608c-227">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="7608c-228">请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for business 配额] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="7608c-228">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="7608c-229">**如何播放团队会议录制？**</span><span class="sxs-lookup"><span data-stu-id="7608c-229">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="7608c-230">你的视频将在 OneDrive for business 或 SharePoint 的视频播放器上播放，具体取决于你访问该文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7608c-230">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="7608c-231">**如果你计划将会弃用添加到 Stream，现有视频是否保持原样和持续多长时间？**</span><span class="sxs-lookup"><span data-stu-id="7608c-231">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="7608c-232">作为平台的流在不久的将来不会被弃用。</span><span class="sxs-lookup"><span data-stu-id="7608c-232">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="7608c-233">在开始迁移之前，当前实时流中的视频将一直保留。</span><span class="sxs-lookup"><span data-stu-id="7608c-233">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="7608c-234">迁移后，这些视频也将迁移到 ODSP。</span><span class="sxs-lookup"><span data-stu-id="7608c-234">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="7608c-235">有关详细信息，请查看 [此处](https://docs.microsoft.com/stream/streamnew/classic-migration) 。</span><span class="sxs-lookup"><span data-stu-id="7608c-235">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
