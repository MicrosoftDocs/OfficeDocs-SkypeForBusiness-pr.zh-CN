---
title: 配置 live 事件中的 Microsoft 团队
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: 了解如何在 Microsoft 团队中，包括设置与会者可见性和录制选项配置 live 事件设置。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354353"
---
# <a name="configure-live-events-in-microsoft-teams"></a><span data-ttu-id="f72e9-103">配置 live 事件中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f72e9-103">Configure live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a><span data-ttu-id="f72e9-104">设置事件支持链接</span><span class="sxs-lookup"><span data-stu-id="f72e9-104">Set up event support link</span></span>
<span data-ttu-id="f72e9-105">这是将向 live 事件与会者显示的链接。</span><span class="sxs-lookup"><span data-stu-id="f72e9-105">This is the link that will be shown to the live event attendees.</span></span> 

<span data-ttu-id="f72e9-106">在 Windows PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f72e9-106">In Windows PowerShell, run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a><span data-ttu-id="f72e9-107">配置 attendee 可见性选项</span><span class="sxs-lookup"><span data-stu-id="f72e9-107">Configure attendee visibility options</span></span>
<span data-ttu-id="f72e9-108">这将允许 live 事件组织者具有适当的与会者可见性创建事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-108">This allows live event organizers to create events with appropriate attendee visibility.</span></span>

|<span data-ttu-id="f72e9-109">**值**</span><span class="sxs-lookup"><span data-stu-id="f72e9-109">**Values**</span></span>  |<span data-ttu-id="f72e9-110">**行为**</span><span class="sxs-lookup"><span data-stu-id="f72e9-110">**Behavior**</span></span>  |
|---------|---------|
|<span data-ttu-id="f72e9-111">所有人</span><span class="sxs-lookup"><span data-stu-id="f72e9-111">Everyone</span></span>     |<span data-ttu-id="f72e9-112">用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公共，公司和特定人员中的每个人。</span><span class="sxs-lookup"><span data-stu-id="f72e9-112">The user has an option to create live events with the following attendee visibility: Public, Everyone in company, and Specific people.</span></span> |
|<span data-ttu-id="f72e9-113">EveryoneInCompany</span><span class="sxs-lookup"><span data-stu-id="f72e9-113">EveryoneInCompany</span></span>     |<span data-ttu-id="f72e9-114">用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公司和特定人员中的每个人。</span><span class="sxs-lookup"><span data-stu-id="f72e9-114">The user has an option to create live events with the following attendee visibility: Everyone in company and Specific people.</span></span> <span data-ttu-id="f72e9-115">用户无法创建可由匿名用户参加的实时事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-115">The user cannot create live events that can be attended by anonymous users.</span></span>|
|<span data-ttu-id="f72e9-116">InvitedUsers</span><span class="sxs-lookup"><span data-stu-id="f72e9-116">InvitedUsers</span></span> |<span data-ttu-id="f72e9-117">用户只能创建 live 被限制为特定的某个人，如输入的事件管理器的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-117">The user can only create live events that are limited to specific people as entered by the event organizer.</span></span> <span data-ttu-id="f72e9-118">用户不能与公共和公司身份验证中的每个人创建 live 事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-118">The user cannot create live events with Public and Everyone in company authentication.</span></span> |

<span data-ttu-id="f72e9-119">使用 BroadcastAttendeeVisibility TeamsMeetingBroadcastPolicy 在 PowerShell 中设置来控制是否用户可以安排可以监视通过匿名与会者的广播的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-119">Use the setting BroadcastAttendeeVisibility in TeamsMeetingBroadcastPolicy in PowerShell to control whether the users can schedule broadcast events that can be watched by anonymous attendees.</span></span> 

<span data-ttu-id="f72e9-120">除非您的自定义策略分配给用户，用户将获得全局策略，具有默认设置为 EveryoneInCompany。</span><span class="sxs-lookup"><span data-stu-id="f72e9-120">Unless you have assigned a custom policy to the users, the users get Global policy, which has default set to EveryoneInCompany.</span></span> 
 
<span data-ttu-id="f72e9-121">在 Windows PowerShell 中，运行以下内容以允许用户在全局策略中创建匿名事件：</span><span class="sxs-lookup"><span data-stu-id="f72e9-121">In Windows PowerShell, run the following to allow users to create anonymous events in the global policy:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a><span data-ttu-id="f72e9-122">配置录制选项</span><span class="sxs-lookup"><span data-stu-id="f72e9-122">Configure recording options</span></span>
> [!NOTE]
> <span data-ttu-id="f72e9-123">此选项才适用于使用快速入门生产方法的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-123">This option is applicable to events that use the Quick start production method only.</span></span>

<span data-ttu-id="f72e9-124">始终记录的实时事件，从不记录，还是事件组织者可以决定记录事件，这样，管理员控制。</span><span class="sxs-lookup"><span data-stu-id="f72e9-124">This allows admins to control whether the live events are always recorded, never recorded, or whether the event organizer can decide to record the event or not.</span></span>  

|<span data-ttu-id="f72e9-125">**值**</span><span class="sxs-lookup"><span data-stu-id="f72e9-125">**Values**</span></span>  |<span data-ttu-id="f72e9-126">**行为**</span><span class="sxs-lookup"><span data-stu-id="f72e9-126">**Behavior**</span></span>  |
|---------|---------|
|<span data-ttu-id="f72e9-127">始终启用</span><span class="sxs-lookup"><span data-stu-id="f72e9-127">Always enabled</span></span> |<span data-ttu-id="f72e9-128">始终记录此用户组织的 live 事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-128">The live events organized by this user are always recorded.</span></span> <span data-ttu-id="f72e9-129">用户不具有用于重写的选项。</span><span class="sxs-lookup"><span data-stu-id="f72e9-129">The user doesn’t have an option to override.</span></span> <span data-ttu-id="f72e9-130">如果记录的实时事件，事件团队成员能够下载录制后事件，并且与会者可以观看后的事件是通过的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-130">If the live event is recorded, the event team members are able to download the recording after the event, and the attendees can watch the event after the event is over.</span></span> |
|<span data-ttu-id="f72e9-131">AlwaysDisabled</span><span class="sxs-lookup"><span data-stu-id="f72e9-131">AlwaysDisabled</span></span> |<span data-ttu-id="f72e9-132">永远不会记录此用户组织的 live 事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-132">The live events organized by this user are never recorded.</span></span> <span data-ttu-id="f72e9-133">用户不具有用于重写的选项。</span><span class="sxs-lookup"><span data-stu-id="f72e9-133">The user doesn’t have an option to override.</span></span> <span data-ttu-id="f72e9-134">如果记录的实时事件，为事件团队成员，创建不录制并与会者无法观看结束后的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-134">If the live event is recorded, no recording is created for the event team members, and the attendees cannot watch the event after it is over.</span></span> |
|<span data-ttu-id="f72e9-135">UserOverride</span><span class="sxs-lookup"><span data-stu-id="f72e9-135">UserOverride</span></span> |<span data-ttu-id="f72e9-136">用户可以决定 live 事件记录，以便在录制文件可以创建为事件工作组成员，并且与会者可以观看后的事件是通过的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-136">User can decide whether the live event is recorded so that a recording file can be created for the event team members, and attendees can watch the event after the event is over.</span></span> |

<span data-ttu-id="f72e9-137">使用录制选项创建的实时事件管理器的实时事件的控件设置*BroadcastRecordingMode* **TeamsMeetingBroadcastPolicy**在 PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="f72e9-137">Use the setting *BroadcastRecordingMode* in **TeamsMeetingBroadcastPolicy** in PowerShell to control recording options of the live events created by the live event organizer.</span></span>

<span data-ttu-id="f72e9-138">在 Windows PowerShell 中，运行以下 cmdlet 以更新全局策略中的记录模式：</span><span class="sxs-lookup"><span data-stu-id="f72e9-138">In Windows PowerShell, run the following cmdlet to update recording mode in the global policy:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a><span data-ttu-id="f72e9-139">配置实时转录和转换团队 live 事件 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="f72e9-139">Configure real-time transcription and translation in Teams live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="f72e9-140">此选项才适用于使用快速入门生产方法的事件。</span><span class="sxs-lookup"><span data-stu-id="f72e9-140">This option is applicable to events that use the Quick start production method only.</span></span>

<span data-ttu-id="f72e9-141">这将允许 live 事件组织者，以启用实时标题和转换为 live 事件与会者。</span><span class="sxs-lookup"><span data-stu-id="f72e9-141">This allows live event organizers to turn on real-time captions and translation for the live event attendees.</span></span> 

<span data-ttu-id="f72e9-142">使用中的设置*AllowBroadcastTranscription* **TeamsMeetingBroadcastPolicy**在 PowerShell 中控制是否 live 事件与会者都将能够看到转录和转换。</span><span class="sxs-lookup"><span data-stu-id="f72e9-142">Use the setting *AllowBroadcastTranscription* in **TeamsMeetingBroadcastPolicy** in PowerShell to control whether the live event attendees will be able to see transcription and translation.</span></span> <span data-ttu-id="f72e9-143">您可以了解有关在此处管理**TeamsMeetingBroadcastPolicy**与 Office 365 PowerShell 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f72e9-143">You can learn more about managing **TeamsMeetingBroadcastPolicy** with Office 365 PowerShell here.</span></span>  

<span data-ttu-id="f72e9-144">除非您的自定义策略分配给用户，用户将获得全局策略，具有转录和默认情况下禁用的转换。</span><span class="sxs-lookup"><span data-stu-id="f72e9-144">Unless you have assigned a custom policy to the users, the users get Global policy, which has transcription and translation disabled by default.</span></span>

<span data-ttu-id="f72e9-145">在 Windows PowerShell 中，运行以下 cmdlet，以在全局策略中打开转录和上的事件与会者的转换：</span><span class="sxs-lookup"><span data-stu-id="f72e9-145">In Windows PowerShell, run the following cmdlet to turn transcription and translation on for event attendees in the global policy:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a><span data-ttu-id="f72e9-146">管理工具</span><span class="sxs-lookup"><span data-stu-id="f72e9-146">Administrative tools</span></span> 
<span data-ttu-id="f72e9-147">虽然 Microsoft 直接控制所有 Office 365 Online 数据中心，并负责整体系统性能，但它可以控制仅结合为 Office 365 用户提供的总体体验的元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="f72e9-147">Although Microsoft directly controls all Office 365 Online data centers and is responsible for overall system performance, it can control only a portion of the elements that combine to provide the total experience for Office 365 users.</span></span> <span data-ttu-id="f72e9-148">组织自己负责网络连接到数据中心，客户的广域网 (WAN) 和客户的局域网 (Lan)。</span><span class="sxs-lookup"><span data-stu-id="f72e9-148">Organizations themselves are responsible for the network connections to the data centers, the customer’s wide area network (WAN), and the customer's local area networks (LANs).</span></span> <span data-ttu-id="f72e9-149">此外，它们是负责用户设备和其配置。</span><span class="sxs-lookup"><span data-stu-id="f72e9-149">Additionally, they are in charge of user devices and their configuration.</span></span><span data-ttu-id="f72e9-150">边缘服务器还负责维护所需的授权每个用户的任何所需的功能，包括，但不是限于到，只要用户需要访问功能的管理这些功能的功能。</span><span class="sxs-lookup"><span data-stu-id="f72e9-150"> They are also responsible for maintaining the required licensing per user for any desired feature, including, but not limited to, the ability to manage these features, for as long as the user needs access to the feature.</span></span>

<span data-ttu-id="f72e9-151">客户可以使用以下工具来管理的各种工作组 live 事件相关的任务。</span><span class="sxs-lookup"><span data-stu-id="f72e9-151">Customers can use the following tools to manage a variety of Teams live events related tasks.</span></span>
- [<span data-ttu-id="f72e9-152">Microsoft Office 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="f72e9-152">Microsoft Office 365 admin center</span></span>](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [<span data-ttu-id="f72e9-153">Microsoft 团队和 Skype 的业务 Online 管理中心</span><span class="sxs-lookup"><span data-stu-id="f72e9-153">Microsoft Teams and Skype for Business Online admin center</span></span>](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [<span data-ttu-id="f72e9-154">Microsoft 流管理中心</span><span class="sxs-lookup"><span data-stu-id="f72e9-154">Microsoft Stream admin center</span></span>](https://stream.microsoft.com)
- [<span data-ttu-id="f72e9-155">远程 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f72e9-155">Remote Windows PowerShell</span></span>](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f72e9-156">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="f72e9-156">Want to know more about Windows PowerShell?</span></span>
<span data-ttu-id="f72e9-157">当谈到 Windows PowerShell，它的所有有关管理用户和用户允许或不允许执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f72e9-157">When it comes to Windows PowerShell, it's all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f72e9-158">使用 Windows PowerShell，您可以管理 Office 365 和 Skype 业务 online 使用单点具有多个要执行的任务时，可以简化您的日常工作的管理。</span><span class="sxs-lookup"><span data-stu-id="f72e9-158">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f72e9-159">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f72e9-159">To get started with Windows PowerShell, see these topics:</span></span>
 - [<span data-ttu-id="f72e9-160">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="f72e9-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [<span data-ttu-id="f72e9-161">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f72e9-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="f72e9-p108">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="f72e9-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
 - [<span data-ttu-id="f72e9-164">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f72e9-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [<span data-ttu-id="f72e9-165">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f72e9-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [<span data-ttu-id="f72e9-166">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="f72e9-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
