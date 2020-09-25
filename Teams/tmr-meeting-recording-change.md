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
ms.openlocfilehash: d1072f86d019415dbc97d0507ff9d76b2cbdc6e6
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269636"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="ecbe3-103">使用 OneDrive for Business 和 SharePoint 或流进行会议录制</span><span class="sxs-lookup"><span data-stu-id="ecbe3-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="ecbe3-104">将会议录制从 Microsoft Stream 改为 OneDrive for Business 和 SharePoint 将是一种分阶段的方法。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="ecbe3-105">在启动时，租户管理员可以立即选择此新工作流选项，并开始在10月2020中查看录制自动上载到 OneDrive for Business 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="ecbe3-106">11月，您必须选择退出如果您希望继续使用流，并且在2021的早期，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="ecbe3-107">Microsoft 团队具有保存会议录制的新方法。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="ecbe3-108">从流出发，此方法在 Microsoft 365 中使用 Microsoft OneDrive 和 SharePoint，并提供许多好处。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="ecbe3-109">使用 OneDrive for Business 和 SharePoint 存储录制的好处包括：</span><span class="sxs-lookup"><span data-stu-id="ecbe3-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="ecbe3-110">团队会议录制的保留策略 (TMR)  (S + C E5 autoretention 标签) </span><span class="sxs-lookup"><span data-stu-id="ecbe3-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="ecbe3-111">从 OneDrive for business 和 SharePoint 信息管理中获益</span><span class="sxs-lookup"><span data-stu-id="ecbe3-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="ecbe3-112">轻松设置权限和共享</span><span class="sxs-lookup"><span data-stu-id="ecbe3-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="ecbe3-113">仅具有明确共享的 (外部用户) 与来宾共享录制</span><span class="sxs-lookup"><span data-stu-id="ecbe3-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="ecbe3-114">请求访问流</span><span class="sxs-lookup"><span data-stu-id="ecbe3-114">Request access flow</span></span>
- <span data-ttu-id="ecbe3-115">提供 OneDrive for business 和 SharePoint 共享链接</span><span class="sxs-lookup"><span data-stu-id="ecbe3-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="ecbe3-116">增加了配额</span><span class="sxs-lookup"><span data-stu-id="ecbe3-116">Increased quota</span></span>
- <span data-ttu-id="ecbe3-117">会议录制更快地可用</span><span class="sxs-lookup"><span data-stu-id="ecbe3-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="ecbe3-118">**转到本地** 租户支持</span><span class="sxs-lookup"><span data-stu-id="ecbe3-118">**Go local** tenant support</span></span>
- <span data-ttu-id="ecbe3-119">多地区支持-录制存储在特定于该用户的区域中</span><span class="sxs-lookup"><span data-stu-id="ecbe3-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="ecbe3-120">将您自己的密钥 (BYOK) 支持</span><span class="sxs-lookup"><span data-stu-id="ecbe3-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="ecbe3-121">改进的记录质量和演讲者特性</span><span class="sxs-lookup"><span data-stu-id="ecbe3-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="ecbe3-122">需要考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="ecbe3-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="ecbe3-123">将有英语的隐藏式字幕和脚本。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="ecbe3-124">您将不能搜索脚本或其内容。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="ecbe3-125">你将无法编辑这些脚本，但你可以将标题切换为 "开/关"。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="ecbe3-126">你可以控制你共享录制的人员，但不能阻止具有共享访问权限的用户下载录制。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="ecbe3-127">录制完成后，你将不会收到电子邮件，但录制将在会议聊天完成后显示在会议聊天中。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="ecbe3-128">这将比以前在流中更快的速度</span><span class="sxs-lookup"><span data-stu-id="ecbe3-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="ecbe3-129">有关详细信息，请观看 "会议录制"。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="ecbe3-130">为 OneDrive for business 和 SharePoint 设置会议录制选项</span><span class="sxs-lookup"><span data-stu-id="ecbe3-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="ecbe3-131">安装 Skype For Business Online PowerShell 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="ecbe3-132">a.</span><span class="sxs-lookup"><span data-stu-id="ecbe3-132">a.</span></span> <span data-ttu-id="ecbe3-133">下载 [Skype For Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="ecbe3-134">b.</span><span class="sxs-lookup"><span data-stu-id="ecbe3-134">b.</span></span> <span data-ttu-id="ecbe3-135">按照提示进行安装。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="ecbe3-136">c.</span><span class="sxs-lookup"><span data-stu-id="ecbe3-136">c.</span></span> <span data-ttu-id="ecbe3-137">重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-137">Restart your machine.</span></span>

2. <span data-ttu-id="ecbe3-138">以管理员身份启动 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecbe3-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="ecbe3-139">导入 SkypeOnline 连接器并作为团队管理员登录。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="ecbe3-140">使用 [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 设置团队会议策略以从流存储切换到 ODSP。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="ecbe3-141">选择退出 OneDrive for Business 和 SharePoint 以继续使用流</span><span class="sxs-lookup"><span data-stu-id="ecbe3-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="ecbe3-142">即使策略指示它已设置为 **流**，它也可能不会设置。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-142">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="ecbe3-143">如果它设置为 nothing，则默认为流。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-143">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="ecbe3-144">如果要选择退出，则 **必须** 将策略重置为 " **流** "，以确保流是默认的。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-144">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="ecbe3-145">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="ecbe3-145">Frequently asked questions</span></span>

<span data-ttu-id="ecbe3-146">**会议录制将存储在何处？**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="ecbe3-147">对于非频道会议，录制将存储在名为的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-147">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="ecbe3-148">录制 \* \*，属于 OneDrive 的最高级别，属于启动会议录制的人员。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-148">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="ecbe3-149">上例</span><span class="sxs-lookup"><span data-stu-id="ecbe3-149">Example:</span></span>

  <span data-ttu-id="ecbe3-150"><i>录像机的 OneDrive For business</i> /**录制**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-150"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="ecbe3-151">对于频道会议，录制内容存储在名为 " **录制**" 的文件夹中的 "团队网站" 文档库中。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-151">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="ecbe3-152">上例</span><span class="sxs-lookup"><span data-stu-id="ecbe3-152">Example:</span></span>

  <span data-ttu-id="ecbe3-153"><i>团队名称-频道名称</i> /**文档** /**录制**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-153"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="ecbe3-154">**哪些人具有查看会议录制的权限？**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-154">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="ecbe3-155">对于非频道会议，除外部用户之外的所有会议被邀请者都将自动获取个人共享链接。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-155">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="ecbe3-156">外部用户需要通过会议组织者或启动会议录制的人员显式添加到共享列表。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-156">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="ecbe3-157">对于频道会议，权限继承自频道中的 "所有者" 和 "成员列表" 列表。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-157">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="ecbe3-158">**如何管理脚本？**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-158">**How can I manage transcripts?**</span></span>

<span data-ttu-id="ecbe3-159">选择加入此预览的客户将不会在其团队会议录制中提供已迁移到 OneDrive 和 SharePoint 的隐藏字幕。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-159">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="ecbe3-160">我们正在努力在2020年10月向会议录制添加字幕，以英文隐藏的字幕开始。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-160">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="ecbe3-161">对于已选择加入以允许在[团队云录制](cloud-recording.md)中介绍的内容的客户，将在团队会议录制中提供隐藏式字幕</span><span class="sxs-lookup"><span data-stu-id="ecbe3-161">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="ecbe3-162">字幕有助于为所有功能的查看者创建包含内容。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-162">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="ecbe3-163">作为所有者，你可以隐藏字幕，但除非你删除团队中的标题，否则仍可在团队中使用记录。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-163">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="ecbe3-164">了解 [如何打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="ecbe3-164">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="ecbe3-165">录制会议时，从录制会议的60天起，团队会议录制支持隐藏式字幕。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-165">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="ecbe3-166">**我的存储配额将受到怎样的影响**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-166">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="ecbe3-167">工作组会议录制文件实时在 OneDrive for business 和 SharePoint 中，并包含在这些服务的配额中。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-167">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="ecbe3-168">请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for business 配额] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-168">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="ecbe3-169">**如何播放团队会议录制？**</span><span class="sxs-lookup"><span data-stu-id="ecbe3-169">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="ecbe3-170">你的视频将在 OneDrive for business 或 SharePoint 的视频播放器上播放，具体取决于你访问该文件的位置。</span><span class="sxs-lookup"><span data-stu-id="ecbe3-170">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>
