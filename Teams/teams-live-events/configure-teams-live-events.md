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
# <a name="configure-live-event-settings-in-microsoft-teams"></a>在 Microsoft Teams 中配置实时事件设置

使用团队实时事件设置来配置你的组织中保留的实时事件的设置。 您可以设置支持 URL 并配置第三方视频分发提供商。 这些设置适用于在你的组织中创建的所有实时事件。 

你可以在 Microsoft 团队管理中心中轻松管理这些设置。 在左侧导航中, 转到 "**会议** > **实时事件" 设置**。 

![live-event-settings](../media/teams-live-events-settings.png "团队实时事件设置的屏幕截图, 可在 Microsoft 团队管理中心进行配置") 

## <a name="set-up-event-support-url"></a>设置事件支持 URL

此 URL 将显示给实时事件参与者。 为你的组织添加支持 URL, 以便与会者在实时事件期间向其提供联系支持的方法。

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft 团队徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航中, 转到 "**会议** > **实时事件设置**"。
2. 在 "**支持 url**" 下, 输入您的组织的支持 url。 

    ![Microsoft 团队管理中心中实时事件的支持 URL 设置](../media/teams-live-events-settings-supporturl.png "团队实时事件的支持 URL 设置的屏幕截图")

### <a name="using-windows-powershell"></a>使用 Windows PowerShell
请运行以下命令：
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
有关详细信息, 请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。
## <a name="configure-a-third-party-video-distribution-provider"></a>配置第三方视频分发提供商 

如果你通过 Microsoft 视频传递合作伙伴购买和设置软件定义的网络 (SDN) 解决方案或企业内容交付网络 (eCDN) 解决方案, 请为团队中的实时事件配置提供程序。 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft 团队徽标的图标](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航中, 转到 "**会议** > **实时事件设置**"。
2. 在**第三方视频分发提供商**下, 完成以下操作: 

    ![Microsoft 团队管理中心中的第三方视频分发提供商设置](../media/teams-live-events-settings-distribution-provider.png "实时事件的第三方视频分发提供商设置的屏幕截图")

    - **使用第三方分发提供商**打开此项以启用第三方视频分发提供商。
    - **SDN 提供程序名称**选择您正在使用的提供商。
    - **提供商许可证密钥**输入您从提供商联系人处获得的许可证 ID。
    - **SDN API 模板 URL**输入从提供商联系人处获取的 API 模板 URL。

### <a name="using-windows-powershell"></a>使用 Windows PowerShell
从你的提供商联系人获取许可证 ID 或 API 令牌和 API 模板, 然后根据你正在使用的提供程序, 运行下列操作之一:

**配置单元** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
有关详细信息, 请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。

> [!NOTE]
> 如果你计划创建使用外部编码器的实时事件, 你还需要[使用 Microsoft Stream 配置 eCDN 提供程序](https://docs.microsoft.com/stream/network-caching)。 

### <a name="related-topics"></a>相关主题
- [什么是 Teams 实时事件？](what-are-teams-live-events.md)
- [规划 Teams 实时事件](plan-for-teams-live-events.md)
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)