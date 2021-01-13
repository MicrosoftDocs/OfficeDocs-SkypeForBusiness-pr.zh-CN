---
title: 在 Microsoft Teams 中配置实时事件设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
- enabler-strategic
description: 了解如何管理组织中组织的 Teams 实时事件设置。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831192"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="c007b-103">在 Microsoft Teams 中配置实时事件设置</span><span class="sxs-lookup"><span data-stu-id="c007b-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="c007b-104">使用 Teams 实时事件设置为组织中举行实时事件配置设置。</span><span class="sxs-lookup"><span data-stu-id="c007b-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="c007b-105">可以设置支持 URL 并配置第三方视频分发提供商。</span><span class="sxs-lookup"><span data-stu-id="c007b-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="c007b-106">这些设置适用于在组织中创建的所有实时事件。</span><span class="sxs-lookup"><span data-stu-id="c007b-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="c007b-107">可以在 Microsoft Teams 管理中心轻松管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="c007b-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c007b-108">在左侧导航栏中，转到 **"会议**  >  **实时事件"设置**。</span><span class="sxs-lookup"><span data-stu-id="c007b-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="c007b-109">![Teams 实时事件设置的屏幕截图](../media/teams-live-events-settings.png "可在 Microsoft Teams 管理中心配置的 Teams 实时事件设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c007b-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="c007b-110">设置事件支持 URL</span><span class="sxs-lookup"><span data-stu-id="c007b-110">Set up event support URL</span></span>

<span data-ttu-id="c007b-111">此 URL 向现场活动与会者显示。</span><span class="sxs-lookup"><span data-stu-id="c007b-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="c007b-112">为组织添加支持 URL，为与会者提供在直播活动期间联系支持人员的方法。</span><span class="sxs-lookup"><span data-stu-id="c007b-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) <span data-ttu-id="c007b-114">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c007b-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c007b-115">在左侧导航栏中，转到 **"会议**  >  **实时事件设置"。**</span><span class="sxs-lookup"><span data-stu-id="c007b-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="c007b-116">在 **"支持 URL"** 下，输入组织的支持 URL。</span><span class="sxs-lookup"><span data-stu-id="c007b-116">Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id="c007b-117">![管理中心内实时事件的支持 URL 设置](../media/teams-live-events-settings-supporturl.png "Teams 实时事件的支持 URL 设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c007b-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="c007b-118">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c007b-118">Using Windows PowerShell</span></span>

<span data-ttu-id="c007b-119">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c007b-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="c007b-120">有关详细信息，请参阅[Set-CsTeamsMeetingBroadcastConfiguration。](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c007b-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="c007b-121">配置第三方视频分发提供商</span><span class="sxs-lookup"><span data-stu-id="c007b-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="c007b-122">如果通过 Microsoft 视频交付合作伙伴购买并设置软件定义的网络 (SDN) 解决方案或企业内容交付网络 (eCDN) 解决方案，请为 Teams 中的实时事件配置提供商。</span><span class="sxs-lookup"><span data-stu-id="c007b-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) <span data-ttu-id="c007b-124">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c007b-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c007b-125">在左侧导航栏中，转到 **"会议**  >  **实时事件设置"。**</span><span class="sxs-lookup"><span data-stu-id="c007b-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="c007b-126">在 **"第三方视频分发提供商"** 下，完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="c007b-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="c007b-127">![管理中心内的第三方视频分发提供商设置](../media/teams-live-events-settings-distribution-provider.png "实时事件的第三方视频分发提供商设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c007b-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="c007b-128">**使用第三方分发提供商** 启用此选项以启用第三方视频分发提供商。</span><span class="sxs-lookup"><span data-stu-id="c007b-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="c007b-129">**SDN 提供程序名称** 选择你使用的提供商。</span><span class="sxs-lookup"><span data-stu-id="c007b-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="c007b-130">**提供程序许可证密钥** 输入从提供商联系人获取的许可证 ID。</span><span class="sxs-lookup"><span data-stu-id="c007b-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="c007b-131">**SDN API 模板 URL** 输入从提供商联系人获取的 API 模板 URL。</span><span class="sxs-lookup"><span data-stu-id="c007b-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="c007b-132">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c007b-132">Using Windows PowerShell</span></span>
<span data-ttu-id="c007b-133">从提供程序联系人获取许可证 ID 或 API 令牌和 API 模板，然后根据使用的提供程序运行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="c007b-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="c007b-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="c007b-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="c007b-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="c007b-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="c007b-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="c007b-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="c007b-137">有关详细信息，请参阅[Set-CsTeamsMeetingBroadcastConfiguration。](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c007b-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="c007b-138">如果计划使用外部应用或设备创建实时事件，则还需要使用 Microsoft Stream 配置 [eCDN 提供程序](https://docs.microsoft.com/stream/network-caching)。</span><span class="sxs-lookup"><span data-stu-id="c007b-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="c007b-p104">从使用 Microsoft Stream 到[使用 OneDrive for Business 和 SharePoint for meeting 进行会议录制](../tmr-meeting-recording-change.md)的改变将是分阶段进行的。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="c007b-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="related-topics"></a><span data-ttu-id="c007b-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="c007b-141">Related topics</span></span>
- [<span data-ttu-id="c007b-142">什么是 Teams 实时事件？</span><span class="sxs-lookup"><span data-stu-id="c007b-142">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="c007b-143">规划 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="c007b-143">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="c007b-144">设置 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="c007b-144">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
