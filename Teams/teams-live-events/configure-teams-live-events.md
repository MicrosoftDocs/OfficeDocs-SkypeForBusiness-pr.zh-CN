---
title: 在 Microsoft Teams 中配置实时事件设置
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何管理组织中保留的团队实时事件的设置。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74eafcd6b16fe6d4c4b4f82c3b3472879ba506eb
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344175"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="4a7ed-103">在 Microsoft Teams 中配置实时事件设置</span><span class="sxs-lookup"><span data-stu-id="4a7ed-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="4a7ed-104">使用团队实时事件设置来配置你的组织中保留的实时事件的设置。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="4a7ed-105">您可以设置支持 URL 并配置第三方视频分发提供商。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="4a7ed-106">这些设置适用于在你的组织中创建的所有实时事件。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="4a7ed-107">你可以在 Microsoft 团队管理中心中轻松管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4a7ed-108">在左侧导航中, 转到 "**会议** > **实时事件" 设置**。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="4a7ed-109">![live-event-settings](../media/teams-live-events-settings.png "团队实时事件设置的屏幕截图, 可在 Microsoft 团队管理中心进行配置")</span><span class="sxs-lookup"><span data-stu-id="4a7ed-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="4a7ed-110">设置事件支持 URL</span><span class="sxs-lookup"><span data-stu-id="4a7ed-110">Set up event support URL</span></span>

<span data-ttu-id="4a7ed-111">此 URL 将显示给实时事件参与者。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="4a7ed-112">为你的组织添加支持 URL, 以便与会者在实时事件期间向其提供联系支持的方法。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft 团队徽标的图标](../media/teams-logo-30x30.png) <span data-ttu-id="4a7ed-114">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="4a7ed-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4a7ed-115">在左侧导航中, 转到 "**会议** > **实时事件设置**"。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="4a7ed-116">在 "**支持 url**" 下, 输入您的组织的支持 url。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="4a7ed-117">![Microsoft 团队管理中心中实时事件的支持 URL 设置](../media/teams-live-events-settings-supporturl.png "团队实时事件的支持 URL 设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="4a7ed-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="4a7ed-118">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a7ed-118">Using Windows PowerShell</span></span>
<span data-ttu-id="4a7ed-119">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4a7ed-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="4a7ed-120">有关详细信息, 请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="4a7ed-121">配置第三方视频分发提供商</span><span class="sxs-lookup"><span data-stu-id="4a7ed-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="4a7ed-122">如果你通过 Microsoft 视频传递合作伙伴购买和设置软件定义的网络 (SDN) 解决方案或企业内容交付网络 (eCDN) 解决方案, 请为团队中的实时事件配置提供程序。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft 团队徽标的图标](../media/teams-logo-30x30.png) <span data-ttu-id="4a7ed-124">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="4a7ed-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4a7ed-125">在左侧导航中, 转到 "**会议** > **实时事件设置**"。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="4a7ed-126">在**第三方视频分发提供商**下, 完成以下操作:</span><span class="sxs-lookup"><span data-stu-id="4a7ed-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="4a7ed-127">![Microsoft 团队管理中心中的第三方视频分发提供商设置](../media/teams-live-events-settings-distribution-provider.png "实时事件的第三方视频分发提供商设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="4a7ed-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="4a7ed-128">**使用第三方分发提供商**打开此项以启用第三方视频分发提供商。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="4a7ed-129">**SDN 提供程序名称**选择您正在使用的提供商。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="4a7ed-130">**提供商许可证密钥**输入您从提供商联系人处获得的许可证 ID。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="4a7ed-131">**SDN API 模板 URL**输入从提供商联系人处获取的 API 模板 URL。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="4a7ed-132">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a7ed-132">Using Windows PowerShell</span></span>
<span data-ttu-id="4a7ed-133">从你的提供商联系人获取许可证 ID 或 API 令牌和 API 模板, 然后根据你正在使用的提供程序, 运行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="4a7ed-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="4a7ed-134">**配置单元**</span><span class="sxs-lookup"><span data-stu-id="4a7ed-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="4a7ed-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="4a7ed-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="4a7ed-136">有关详细信息, 请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="4a7ed-137">如果你计划创建使用外部编码器的实时事件, 你还需要[使用 Microsoft Stream 配置 eCDN 提供程序](https://docs.microsoft.com/stream/network-caching)。</span><span class="sxs-lookup"><span data-stu-id="4a7ed-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="4a7ed-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a7ed-138">Related topics</span></span>
- [<span data-ttu-id="4a7ed-139">什么是 Teams 实时事件？</span><span class="sxs-lookup"><span data-stu-id="4a7ed-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="4a7ed-140">规划 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="4a7ed-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="4a7ed-141">设置 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="4a7ed-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)