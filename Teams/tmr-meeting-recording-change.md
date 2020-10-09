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
ms.openlocfilehash: 7a42c46cf9592c64676d153e1885357a4ee8ec7b
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389930"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="3a3da-103">使用 OneDrive for Business 和 SharePoint 或流进行会议录制</span><span class="sxs-lookup"><span data-stu-id="3a3da-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="3a3da-104">将会议录制从 Microsoft Stream 改为 OneDrive for Business 和 SharePoint 将是一种分阶段的方法。</span><span class="sxs-lookup"><span data-stu-id="3a3da-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="3a3da-105">在启动时，租户管理员可以立即选择此新工作流选项，并开始在10月2020中查看录制自动上载到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="3a3da-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="3a3da-106">11月，您必须选择退出如果您希望继续使用流，并且在2021的早期，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="3a3da-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="3a3da-107">Microsoft 团队具有保存会议录制的新方法。</span><span class="sxs-lookup"><span data-stu-id="3a3da-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="3a3da-108">作为从经典 Microsoft Stream 过渡到 [新流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 microsoft 365 中的 microsoft OneDrive 和 SharePoint 上并提供许多好处。</span><span class="sxs-lookup"><span data-stu-id="3a3da-108">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="3a3da-109">使用 OneDrive for Business 和 SharePoint 存储录制的好处包括：</span><span class="sxs-lookup"><span data-stu-id="3a3da-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="3a3da-110">团队会议录制的保留策略 (TMR)  (S + C E5 autoretention 标签) </span><span class="sxs-lookup"><span data-stu-id="3a3da-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="3a3da-111">从 OneDrive for business 和 SharePoint 信息管理中获益</span><span class="sxs-lookup"><span data-stu-id="3a3da-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="3a3da-112">轻松设置权限和共享</span><span class="sxs-lookup"><span data-stu-id="3a3da-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="3a3da-113">仅具有明确共享的 (外部用户) 与来宾共享录制</span><span class="sxs-lookup"><span data-stu-id="3a3da-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="3a3da-114">请求访问流</span><span class="sxs-lookup"><span data-stu-id="3a3da-114">Request access flow</span></span>
- <span data-ttu-id="3a3da-115">提供 OneDrive for business 和 SharePoint 共享链接</span><span class="sxs-lookup"><span data-stu-id="3a3da-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="3a3da-116">增加了配额</span><span class="sxs-lookup"><span data-stu-id="3a3da-116">Increased quota</span></span>
- <span data-ttu-id="3a3da-117">会议录制更快地可用</span><span class="sxs-lookup"><span data-stu-id="3a3da-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="3a3da-118">**转到本地** 租户支持</span><span class="sxs-lookup"><span data-stu-id="3a3da-118">**Go local** tenant support</span></span>
- <span data-ttu-id="3a3da-119">多地区支持-录制存储在特定于该用户的区域中</span><span class="sxs-lookup"><span data-stu-id="3a3da-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="3a3da-120">将您自己的密钥 (BYOK) 支持</span><span class="sxs-lookup"><span data-stu-id="3a3da-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="3a3da-121">改进的记录质量和演讲者特性</span><span class="sxs-lookup"><span data-stu-id="3a3da-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="3a3da-122">需要考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="3a3da-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="3a3da-123">将有英语的隐藏式字幕和脚本。</span><span class="sxs-lookup"><span data-stu-id="3a3da-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="3a3da-124">您将不能搜索脚本或其内容。</span><span class="sxs-lookup"><span data-stu-id="3a3da-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="3a3da-125">你将无法编辑这些脚本，但你可以将标题切换为 "开/关"。</span><span class="sxs-lookup"><span data-stu-id="3a3da-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="3a3da-126">你可以控制你共享录制的人员，但不能阻止具有共享访问权限的用户下载录制。</span><span class="sxs-lookup"><span data-stu-id="3a3da-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="3a3da-127">录制完成后，你将不会收到电子邮件，但录制将在会议聊天完成后显示在会议聊天中。</span><span class="sxs-lookup"><span data-stu-id="3a3da-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="3a3da-128">这将比以前在流中更快的速度</span><span class="sxs-lookup"><span data-stu-id="3a3da-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="3a3da-129">有关详细信息，请观看 "会议录制"。</span><span class="sxs-lookup"><span data-stu-id="3a3da-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="3a3da-130">为 OneDrive for business 和 SharePoint 设置会议录制选项</span><span class="sxs-lookup"><span data-stu-id="3a3da-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="3a3da-131">安装 Skype For Business Online PowerShell 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3a3da-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="3a3da-132">a.</span><span class="sxs-lookup"><span data-stu-id="3a3da-132">a.</span></span> <span data-ttu-id="3a3da-133">下载 [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="3a3da-133">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="3a3da-134">b.</span><span class="sxs-lookup"><span data-stu-id="3a3da-134">b.</span></span> <span data-ttu-id="3a3da-135">按照提示进行安装。</span><span class="sxs-lookup"><span data-stu-id="3a3da-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="3a3da-136">c.</span><span class="sxs-lookup"><span data-stu-id="3a3da-136">c.</span></span> <span data-ttu-id="3a3da-137">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="3a3da-137">Restart your machine.</span></span>

2. <span data-ttu-id="3a3da-138">以管理员身份启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a3da-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="3a3da-139">导入 SkypeOnline 连接器并作为团队管理员登录。</span><span class="sxs-lookup"><span data-stu-id="3a3da-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="3a3da-140">使用 [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 设置团队会议策略以从流存储切换到 ODSP。</span><span class="sxs-lookup"><span data-stu-id="3a3da-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="3a3da-141">选择退出 OneDrive for Business 和 SharePoint 以继续使用流</span><span class="sxs-lookup"><span data-stu-id="3a3da-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="3a3da-142">即使策略指示它已设置为 **流**，它也可能不会设置。</span><span class="sxs-lookup"><span data-stu-id="3a3da-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="3a3da-143">通常情况下，如果未设置策略，则默认设置为 " **流**"。</span><span class="sxs-lookup"><span data-stu-id="3a3da-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="3a3da-144">但是，如果你想要取消使用 SharePoint 或 OneDrive，请使用此新更改，然后必须将策略重置为 **流** ，以确保它是默认设置。</span><span class="sxs-lookup"><span data-stu-id="3a3da-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="3a3da-145">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="3a3da-145">Frequently asked questions</span></span>

<span data-ttu-id="3a3da-146">**会议录制将存储在何处？**</span><span class="sxs-lookup"><span data-stu-id="3a3da-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="3a3da-147">对于非频道会议，录制将存储在属于已启动会议录制 **的人员** 的 OneDrive 的最高级别的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3a3da-147">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="3a3da-148">上例</span><span class="sxs-lookup"><span data-stu-id="3a3da-148">Example:</span></span>

  <span data-ttu-id="3a3da-149"><i>录像机的 OneDrive For business</i> /**录制**</span><span class="sxs-lookup"><span data-stu-id="3a3da-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="3a3da-150">对于频道会议，录制内容存储在名为 " **录制**" 的文件夹中的 "团队网站" 文档库中。</span><span class="sxs-lookup"><span data-stu-id="3a3da-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="3a3da-151">上例</span><span class="sxs-lookup"><span data-stu-id="3a3da-151">Example:</span></span>

  <span data-ttu-id="3a3da-152"><i>团队名称-频道名称</i> /**文档** /**录制**</span><span class="sxs-lookup"><span data-stu-id="3a3da-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="3a3da-153">**如何处理以前员工的录制？**</span><span class="sxs-lookup"><span data-stu-id="3a3da-153">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="3a3da-154">由于视频与 OneDrive 和 SharePoint 中的任何其他文件一样，在员工离职后处理所有权和保留将遵循正常的 [OneDrive 和 sharepoint 进程]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。</span><span class="sxs-lookup"><span data-stu-id="3a3da-154">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="3a3da-155">**哪些人具有查看会议录制的权限？**</span><span class="sxs-lookup"><span data-stu-id="3a3da-155">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="3a3da-156">对于非频道会议，除外部用户之外的所有会议被邀请者都将自动获取个人共享链接。</span><span class="sxs-lookup"><span data-stu-id="3a3da-156">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="3a3da-157">外部用户需要通过会议组织者或启动会议录制的人员显式添加到共享列表。</span><span class="sxs-lookup"><span data-stu-id="3a3da-157">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="3a3da-158">对于频道会议，权限继承自频道中的 "所有者" 和 "成员列表" 列表。</span><span class="sxs-lookup"><span data-stu-id="3a3da-158">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="3a3da-159">**如何管理脚本？**</span><span class="sxs-lookup"><span data-stu-id="3a3da-159">**How can I manage transcripts?**</span></span>

<span data-ttu-id="3a3da-160">选择加入此预览的客户将不会在其团队会议录制中提供已迁移到 OneDrive 和 SharePoint 的隐藏字幕。</span><span class="sxs-lookup"><span data-stu-id="3a3da-160">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="3a3da-161">我们正在努力在2020年10月向会议录制添加字幕，以英文隐藏的字幕开始。</span><span class="sxs-lookup"><span data-stu-id="3a3da-161">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="3a3da-162">对于已选择加入以允许在[团队云录制](cloud-recording.md)中介绍的内容的客户，将在团队会议录制中提供隐藏式字幕</span><span class="sxs-lookup"><span data-stu-id="3a3da-162">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="3a3da-163">字幕有助于为所有功能的查看者创建包含内容。</span><span class="sxs-lookup"><span data-stu-id="3a3da-163">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="3a3da-164">作为所有者，你可以隐藏字幕，但除非你删除团队中的标题，否则仍可在团队中使用记录。</span><span class="sxs-lookup"><span data-stu-id="3a3da-164">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="3a3da-165">了解 [如何打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="3a3da-165">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="3a3da-166">录制会议时，从录制会议的60天起，团队会议录制支持隐藏式字幕。</span><span class="sxs-lookup"><span data-stu-id="3a3da-166">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="3a3da-167">**我的存储配额将受到怎样的影响**</span><span class="sxs-lookup"><span data-stu-id="3a3da-167">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="3a3da-168">工作组会议录制文件实时在 OneDrive for business 和 SharePoint 中，并包含在这些服务的配额中。</span><span class="sxs-lookup"><span data-stu-id="3a3da-168">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="3a3da-169">请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for business 配额] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="3a3da-169">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="3a3da-170">**如何播放团队会议录制？**</span><span class="sxs-lookup"><span data-stu-id="3a3da-170">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="3a3da-171">你的视频将在 OneDrive for business 或 SharePoint 的视频播放器上播放，具体取决于你访问该文件的位置。</span><span class="sxs-lookup"><span data-stu-id="3a3da-171">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="3a3da-172">**如果你计划将会弃用添加到 Stream，现有视频是否保持原样和持续多长时间？**</span><span class="sxs-lookup"><span data-stu-id="3a3da-172">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="3a3da-173">作为平台的流在不久的将来不会被弃用。</span><span class="sxs-lookup"><span data-stu-id="3a3da-173">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="3a3da-174">在开始迁移之前，当前实时流中的视频将一直保留。</span><span class="sxs-lookup"><span data-stu-id="3a3da-174">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="3a3da-175">迁移后，这些视频也将迁移到 ODSP。</span><span class="sxs-lookup"><span data-stu-id="3a3da-175">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="3a3da-176">有关详细信息，请查看 [此处](https://docs.microsoft.com/stream/streamnew/classic-migration) 。</span><span class="sxs-lookup"><span data-stu-id="3a3da-176">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
