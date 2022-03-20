---
title: 网络漫游策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 了解如何管理 Teams 网络漫游策略的设置。
ms.openlocfilehash: 684bb9f30abb6a474582d83614d0e259ed44b21a
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660718"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>使用网络漫游策略管理视频和媒体设置

除了使用会议策略管理视频和媒体设置之外，你现在还可以通过使用 TeamsNetworkRoamingPolicy 动态控制 Microsoft Teams 客户端使用的以下属性的使用： 

- IP 视频
- 媒体比特率

此策略支持你将设置分配给网络站点。 Teams 客户端将根据连接到的网络站点动态选取设置。 当 Teams 客户端从分配了漫游策略的网络站点登录时，将使用该策略。 如果未分配策略，则将使用会议策略中设置的值。 有关会议策略音频和视频设置的详细信息，请参阅 [音频和视频的会议策略设置](meeting-policies-audio-and-video.md)。

## <a name="configure-the-teamsnetworkroamingpolicy"></a>配置 TeamsNetworkRoamingPolicy

要配置 TeamsNetworkRoamingPolicy，请使用以下 PowerShell cmdlet：

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy 包含以下参数：

- AllowIPVideo - 此设置控制是否可以在用户主持的会议和用户启动的 1:1 和群组通话中启用视频。

- MediaBitRateKb - 此设置确定用户在通话和会议中的音频、视频和基于视频的应用共享传输的总平均媒体比特率。

配置策略后，通过使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet 将其分配给一个或多个网络站点，如下所示：

```PowerShell
 Set-CsTenantNetworkSite -NetworkRoamingPolicy
 ``` 
 
 要从网络站点中删除策略，请使用以下 cmdlet：
 
 ```PowerShell
 Set-CsTenantNetworkSite -NetworkRoamingPolicy $null
 ```

要为未启用企业语音的用户启用网络漫游策略，还必须在 TeamsMeetingPolicy 中启用 AllowNetworkConfigurationSettingsLookup 设置。 默认情况下，此设置处于关闭状态。

有关创建网络站点的详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。 

## <a name="examples"></a>示例

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>支持的客户端

- Windows 
- MacOS 桌面

## <a name="known-issues"></a>已知问题

在 Teams Online PowerShell v 2.0.0 中指定 New- 和 Get-CsTeamsNetworkRoamingPolicy 时，你将看到显示额外的数据。


## <a name="related-topics"></a>相关主题

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
