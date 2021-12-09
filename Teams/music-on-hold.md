---
title: 音乐保持状态
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: 了解如何在 音乐 电话系统 中管理"保留"电话系统。
ms.openlocfilehash: 7a7a79bb2d96bcd43e12b27424630acd7a0c90eb
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355731"
---
# <a name="music-on-hold"></a>音乐保持状态

当Microsoft Teams呼叫者从公共电话交换网 (PSTN) 呼叫时，PSTN 呼叫者可以收听所选音乐。

播放的音乐是 Microsoft 提供的默认音乐，或者是上传和配置的自定义音乐。 作为租户管理员，通过创建 音乐 Teams 调用策略并将策略分配给用户来音乐保留Teams可用。

PSTN 呼叫Microsoft Teams中提供的默认音乐不收取组织支付的任何版权费。

请注意，PSTN 呼叫者音乐其他情况下侦听保持状态;例如，当呼叫进入云呼叫队列时，或者当呼叫被用户Microsoft Teams时。 本文中提到的功能未涵盖或控制这些方案。

## <a name="configure-music-on-hold"></a>配置音乐保留状态

若要配置音乐保留：：

1.  在管理中心左侧导航Teams，转到 **"语音>呼叫策略"。**

2.  在" **管理策略"** 选项卡上，选择一个现有策略或创建新策略。

3.  在 **"音乐 PSTN 呼叫者** 保留"字段中，选择下拉菜单中的"已启用"。

也可使用 powerShell 音乐配置保留Teams保留。 在 TeamsCallingPolicy 中，将 MusicOnHoldEnabledType 参数更改为 Enabled，然后将该策略实例授予一个或多个用户。

如果Teams具有 Teams 保留设置为"禁用"的 音乐 呼叫策略，则当 Teams 用户将呼叫设置为保持时，不会播放任何音乐。

## <a name="configure-custom-music"></a>配置自定义音乐

除了向 PSTN 呼叫者播放默认音乐外，您还可以上传包含音乐或其他音频内容的自定义音频文件，并配置要播放给 PSTN 呼叫者的音频文件。
例如，当外部 PSTN 呼叫者被置于保留状态时，部门或组织可能希望播放自定义公告或自定义音乐。  

> [!NOTE]
> 你负责独立清除和保护使用任何音乐或音频文件的一切必要权限和权限，Microsoft Teams服务。 这可能包括来自所有相关权限持有者的音频文件中任何音乐、音效、音频、品牌、名称和其他内容的知识产权和其他权利。 持有者可能包括艺术家、执行者、表演者、艺术家、歌曲作者、作曲者、录制标签、音乐发布者、联盟、协会、权利代理人、集体管理组织，以及拥有、控制或许可音乐版权、声音效果、音频和其他知识产权的其他任何方。

若要配置自定义 音乐 保留，请使用 Teams PowerShell 模块 2.5.0 或更高版本中的 PowerShell cmdlet New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy 和 Import/Get/Remove-CsOnlineAudioFile。


1. 确保呼叫Teams PSTN 呼叫音乐策略中设置为"已启用"的用户Teams保留。 

2. Upload自定义音频文件。

3. 创建Teams自定义音频文件的呼叫保留策略，并将其分配给Teams用户。

### <a name="upload-the-custom-audio-file"></a>Upload自定义音频文件

自定义保留音乐从上传音频文件开始。 为此，请使用 PowerShell cmdlet Import-CsOnlineAudioFile。 下面显示了使用 PowerShell 接口上传 MP3 音频文件的示例：

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>在呼叫保留策略中Teams音频文件

上传音频文件后，需要在创建或设置 Teams 呼叫保留策略时，使用文件的 ID 在 Teams 呼叫保留策略中引用该文件。 例如：

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

在创建了新的呼叫Teams策略后，可以使用以下方法Grant-CsTeamsCallHoldPolicy它：

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

若要获取有关已上传音频文件的信息，请使用 Get-CsOnlineAudioFile cmdlet。

若要删除上传的音频文件，请使用 Remove-CsOnlineAudioFile cmdlet。 删除音频文件之前，请检查是否未在 TeamsCallHoldPolicy 中使用该音频文件。

## <a name="feature-availability"></a>功能可用性

下表指示哪些客户端和设备支持哪些功能音乐保留和自定义音乐保留。 Microsoft 将继续添加功能支持，因此请经常回来查看是否有其他可用性。


| 功能 | 桌面 <br> Windows/Mac OS | 浏览器 | 移动 <br> iOS | 移动 <br> Android | Teams 电话 |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 保持 1：1 PSTN 呼叫 | -音乐保留<br>-自定义音乐保留 | -音乐保留<br>-自定义音乐保留 | -音乐保留<br>-自定义音乐保留 | 音乐保持状态 | 音乐保持状态 |
| 在 1：1 PSTN 呼叫上保留咨询转移 |-音乐保留<br>-自定义音乐保留 | | | | |

## <a name="restrictions"></a>限制

- 音乐保留仅在商业云中可用。

- 音乐保持仅在用户进入 TeamsOnly 模式时可用。

- 如果调用Teams用户启用了Location-Based路由，音乐无法向调用方播放保留状态。

- 上载音频文件后无法导出;只能将其删除。

- 对于音乐"共享线路外观"和"委派"配置的用户 (保留) 以及何时使用呼叫保留。 将音乐保留标准游戏。

- 在某些情况下，直接路由媒体旁路呼叫将转换为非媒体旁路，以播放 音乐 on Hold，呼叫将保持为非媒体旁路，直到呼叫终止。

## <a name="related-topics"></a>相关主题

- [向用户分配策略](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)
