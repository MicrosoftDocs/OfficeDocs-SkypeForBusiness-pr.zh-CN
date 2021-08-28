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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: 了解如何管理组织中Teams实时事件的设置。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8eccc6e885cef67d4f6240483d3995df88d7cfc
ms.sourcegitcommit: 25fd720c008dcf1573344e50d736131a20c3ac7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2021
ms.locfileid: "58683303"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>在 Microsoft Teams 中配置实时事件设置

使用Teams事件设置来配置组织中举行实时事件的设置。 可以设置支持 URL 并配置第三方视频分发提供商。 这些设置适用于在组织中创建的所有实时事件。

可以在管理中心内轻松Microsoft Teams这些设置。 在左侧导航栏中，转到"**会议**  >  **实时事件设置"。**

![实时事件Teams屏幕截图](../media/teams-live-events-settings.png "屏幕截图Teams管理中心中配置的直播事件Microsoft Teams设置")

## <a name="set-up-event-support-url"></a>设置事件支持 URL

此 URL 显示给实时事件与会者。 为组织添加支持 URL，为与会者提供一种在实时活动期间联系支持人员的方法。

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到"**会议**  >  **实时事件设置&quot;。**
2. 在 **&quot;支持 URL&quot;** 下，输入组织的支持 URL。

    ![管理中心内实时事件的支持 URL 设置](../media/teams-live-events-settings-supporturl.png &quot;实时事件的支持 URL Teams屏幕截图")

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

请运行以下命令：

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
有关详细信息，请参阅[Set-CsTeamsMeetingBroadcastConfiguration。](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>配置第三方视频分发提供商 

如果通过 Microsoft 视频交付合作伙伴购买并设置软件定义的网络 (SDN) 解决方案或企业内容交付网络 (eCDN) 解决方案，请为 Teams 中的实时事件配置提供商。 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，转到"**会议**  >  **实时事件设置&quot;。**
2. 在 **&quot;第三方视频分发提供商&quot;下**，完成以下操作： 

    ![管理中心中的第三方视频分发提供商设置](../media/teams-live-events-settings-distribution-provider.png &quot;实时事件的第三方视频分发提供商设置的屏幕截图")

    - **使用第三方分发提供商** 启用此选项以启用第三方视频分发提供商。
    - **SDN 提供程序名称** 选择你使用的提供商。
    - **提供程序许可证密钥** 输入从提供商联系人获取的许可证 ID。
    - **SDN API 模板 URL** 输入从提供商联系人获取的 API 模板 URL。

### <a name="using-windows-powershell"></a>使用 Windows PowerShell
从提供程序联系人获取许可证 ID 或 API 令牌和 API 模板，然后根据使用的提供程序运行下列操作之一：

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```
**Peer5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

有关详细信息，请参阅[Set-CsTeamsMeetingBroadcastConfiguration。](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> 如果计划使用外部应用或设备创建实时事件，则还需要使用 Microsoft Stream 配置 [eCDN 提供程序](/stream/network-caching)。 

>[!Note]
> 从使用 Microsoft Stream 到[使用 OneDrive for Business 和 SharePoint for meeting 进行会议录制](../tmr-meeting-recording-change.md)的改变将是分阶段进行的。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。

>[!Note]
> 所选的 eCDN 解决方案受所选第三方提供商的服务条款和隐私策略的约束，将控制 eCDN 提供商解决方案的使用。 使用 eCDN 提供商的解决方案不受 Microsoft 批量许可条款或在线服务条款限制。 如果您不同意第三方提供商的条款，请不要在 Microsoft Teams 中启用 eCDN 解决方案。

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [规划 Teams 实时事件](plan-for-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
