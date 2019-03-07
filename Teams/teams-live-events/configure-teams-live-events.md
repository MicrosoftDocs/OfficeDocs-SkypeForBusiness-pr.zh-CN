---
title: 在 Microsoft Teams 中配置实时事件设置
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何管理保留在您的组织中的团队 live 事件的设置。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94a167e8a929f2011ccaa773cd04d4e0ca6a2a0e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463665"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="0c077-103">在 Microsoft Teams 中配置实时事件设置</span><span class="sxs-lookup"><span data-stu-id="0c077-103">Configure live event settings in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="0c077-104">使用团队 live 事件设置您的组织中配置的实时事件的保留设置。</span><span class="sxs-lookup"><span data-stu-id="0c077-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="0c077-105">您可以设置的支持 URL 和配置第三方视频分布提供程序。</span><span class="sxs-lookup"><span data-stu-id="0c077-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="0c077-106">这些设置适用于您的组织中创建的所有 live 事件。</span><span class="sxs-lookup"><span data-stu-id="0c077-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="0c077-107">您可以方便地管理 Microsoft 团队管理中心中的这些设置。</span><span class="sxs-lookup"><span data-stu-id="0c077-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0c077-108">在左侧导航窗格中，转到**会议** > **Live 事件设置**。</span><span class="sxs-lookup"><span data-stu-id="0c077-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="0c077-109">![live 事件 settings.png](../media/teams-live-events-settings.png "团队的屏幕截图 live 事件设置可以配置在管理中心中的 Microsoft 团队")</span><span class="sxs-lookup"><span data-stu-id="0c077-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="0c077-110">设置事件支持 URL</span><span class="sxs-lookup"><span data-stu-id="0c077-110">Set up event support URL</span></span>

<span data-ttu-id="0c077-111">显示此 URL live 事件与会者。</span><span class="sxs-lookup"><span data-stu-id="0c077-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="0c077-112">添加您的组织的支持 URL，使与会者可以与支持部门联系 live 事件期间方式。</span><span class="sxs-lookup"><span data-stu-id="0c077-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![团队-徽标-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="0c077-114">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="0c077-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0c077-115">在左侧导航窗格中，转到**会议** > **Live 事件设置**。</span><span class="sxs-lookup"><span data-stu-id="0c077-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="0c077-116">在**支持的 URL**，输入您的组织的支持 URL。</span><span class="sxs-lookup"><span data-stu-id="0c077-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="0c077-117">![支持 URL 设置 live 的 Microsoft 团队管理中心中的事件](../media/teams-live-events-settings-supporturl.png "屏幕截图支持 URL 设置团队 live 事件")</span><span class="sxs-lookup"><span data-stu-id="0c077-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="0c077-118">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c077-118">Using Windows PowerShell</span></span>
<span data-ttu-id="0c077-119">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c077-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="0c077-120">有关详细信息，请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0c077-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="0c077-121">配置第三方视频分布提供程序</span><span class="sxs-lookup"><span data-stu-id="0c077-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="0c077-122">如果您购买并设置软件定义网络 (SDN) 解决方案或通过 Microsoft 视频传递合作伙伴的企业内容交付网络 (eCDN) 解决方案，团队中配置实时事件提供的程序。</span><span class="sxs-lookup"><span data-stu-id="0c077-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![团队-徽标-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="0c077-124">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="0c077-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0c077-125">在左侧导航窗格中，转到**会议** > **Live 事件设置**。</span><span class="sxs-lookup"><span data-stu-id="0c077-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="0c077-126">在**第三方视频分布提供**，完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="0c077-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="0c077-127">![Microsoft 团队管理中心中的第三方视频分布提供程序设置](../media/teams-live-events-settings-distribution-provider.png "屏幕截图的第三方视频分布提供程序设置的实时事件")</span><span class="sxs-lookup"><span data-stu-id="0c077-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="0c077-128">**使用第三方分发提供程序**关闭此到启用的第三方视频分布提供程序。</span><span class="sxs-lookup"><span data-stu-id="0c077-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="0c077-129">**SDN 提供程序名称**选择您使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="0c077-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="0c077-130">**提供程序许可证密钥**输入你从提供程序联系人的许可证 ID。</span><span class="sxs-lookup"><span data-stu-id="0c077-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="0c077-131">**SDN API 模板 URL**输入你从提供程序联系人的 API 模板 URL。</span><span class="sxs-lookup"><span data-stu-id="0c077-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="0c077-132">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c077-132">Using Windows PowerShell</span></span>
<span data-ttu-id="0c077-133">从提供程序联系人，获得许可证 ID 或 API 令牌和 API 模板，然后运行以下内容，具体取决于您使用的提供程序之一：</span><span class="sxs-lookup"><span data-stu-id="0c077-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="0c077-134">**配置单元**</span><span class="sxs-lookup"><span data-stu-id="0c077-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="0c077-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="0c077-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="0c077-136">有关详细信息，请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0c077-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="0c077-137">如果您计划来创建使用外部编码器的实时事件，您还需要配置[与 Microsoft 流您 eCDN 提供程序](https://docs.microsoft.com/stream/network-caching)。</span><span class="sxs-lookup"><span data-stu-id="0c077-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="0c077-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c077-138">Related topics</span></span>
- [<span data-ttu-id="0c077-139">什么是团队 live 事件？</span><span class="sxs-lookup"><span data-stu-id="0c077-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="0c077-140">规划团队 live 事件</span><span class="sxs-lookup"><span data-stu-id="0c077-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="0c077-141">设置团队的实时事件</span><span class="sxs-lookup"><span data-stu-id="0c077-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)