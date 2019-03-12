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
description: 了解如何管理保留在您的组织中的团队 live 事件的设置。
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56a7834f1547c682c690f8c42082af0a314efec9
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542836"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>在 Microsoft Teams 中配置实时事件设置
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

使用团队 live 事件设置您的组织中配置的实时事件的保留设置。 您可以设置的支持 URL 和配置第三方视频分布提供程序。 这些设置适用于您的组织中创建的所有 live 事件。 

您可以方便地管理 Microsoft 团队管理中心中的这些设置。 在左侧导航窗格中，转到**会议** > **Live 事件设置**。 

![live 事件 settings.png](../media/teams-live-events-settings.png "团队的屏幕截图 live 事件设置可以配置在管理中心中的 Microsoft 团队") 

## <a name="set-up-event-support-url"></a>设置事件支持 URL

显示此 URL live 事件与会者。 添加您的组织的支持 URL，使与会者可以与支持部门联系 live 事件期间方式。

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![团队-徽标-30x30.png](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航窗格中，转到**会议** > **Live 事件设置**。
2. 在**支持的 URL**，输入您的组织的支持 URL。 

    ![支持 URL 设置 live 的 Microsoft 团队管理中心中的事件](../media/teams-live-events-settings-supporturl.png "屏幕截图支持 URL 设置团队 live 事件")

### <a name="using-windows-powershell"></a>使用 Windows PowerShell
请运行以下命令：
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
有关详细信息，请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。
## <a name="configure-a-third-party-video-distribution-provider"></a>配置第三方视频分布提供程序 

如果您购买并设置软件定义网络 (SDN) 解决方案或通过 Microsoft 视频传递合作伙伴的企业内容交付网络 (eCDN) 解决方案，团队中配置实时事件提供的程序。 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![团队-徽标-30x30.png](../media/teams-logo-30x30.png) 使用 Microsoft 团队管理中心

1. 在左侧导航窗格中，转到**会议** > **Live 事件设置**。
2. 在**第三方视频分布提供**，完成以下任务： 

    ![Microsoft 团队管理中心中的第三方视频分布提供程序设置](../media/teams-live-events-settings-distribution-provider.png "屏幕截图的第三方视频分布提供程序设置的实时事件")

    - **使用第三方分发提供程序**关闭此到启用的第三方视频分布提供程序。
    - **SDN 提供程序名称**选择您使用的提供程序。
    - **提供程序许可证密钥**输入你从提供程序联系人的许可证 ID。
    - **SDN API 模板 URL**输入你从提供程序联系人的 API 模板 URL。

### <a name="using-windows-powershell"></a>使用 Windows PowerShell
从提供程序联系人，获得许可证 ID 或 API 令牌和 API 模板，然后运行以下内容，具体取决于您使用的提供程序之一：

**配置单元** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
有关详细信息，请参阅[设置 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。

> [!NOTE]
> 如果您计划来创建使用外部编码器的实时事件，您还需要配置[与 Microsoft 流您 eCDN 提供程序](https://docs.microsoft.com/stream/network-caching)。 

### <a name="related-topics"></a>相关主题
- [什么是团队 live 事件？](what-are-teams-live-events.md)
- [规划团队 live 事件](plan-for-teams-live-events.md)
- [设置团队的实时事件](set-up-for-teams-live-events.md)