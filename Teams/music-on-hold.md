---
title: 保留音乐
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
description: 了解如何在电话系统中管理音乐保留功能。
ms.openlocfilehash: 9e2a2aa352a1fd65955b35d4175b831653c694cb
ms.sourcegitcommit: 52450514880fe72af0d0b2fab1419eadfc3a583f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2022
ms.locfileid: "68499446"
---
# <a name="music-on-hold"></a>保留音乐

当 Microsoft Teams 用户暂停传入呼叫时，调用方可以收听所选音乐。

播放的音乐是 Microsoft 提供的默认音乐，或者是上传和配置的自定义音乐。 作为租户管理员，通过创建 Teams 调用策略并将策略分配给 Teams 用户来配置“保留音乐”是否可用。

Microsoft Teams 呼叫方案中提供的默认音乐不含组织支付的任何版税。

请注意，调用方也可以在其他情况下收听“暂停音乐”;例如，当他们调用到云呼叫队列或其呼叫由 Microsoft Teams 用户寄存时。 本文中提到的功能不涵盖或控制这些方案。

## <a name="configure-music-on-hold"></a>在保留时配置音乐

若要配置“按住音乐”：

1. 在 Teams 管理中心的左侧导航中，转到 **语音>呼叫策略**。

2. 在“ **管理策略** ”选项卡上，选择现有策略之一或创建一个新策略。

3. 在 **PSTN 调用方的“音乐保留** ”字段中，在下拉菜单中选择 **“启用** ”。

还可以使用 Teams PowerShell 模块配置“保持音乐”。 在 TeamsCallingPolicy 中，将 MusicOnHoldEnabledType 参数更改为“已启用”，然后将该策略实例授予一个或多个用户。

如果 Teams 用户具有 Teams 呼叫策略，而“保留音乐”设置为“已禁用”，则当 Teams 用户暂停呼叫时，将不会播放任何音乐。

## <a name="configure-custom-music"></a>配置自定义音乐

除了向调用方播放默认音乐外，还可以上传包含音乐或其他音频内容的自定义音频文件，并将该音频文件配置为播放给调用方。
例如，当外部 PSTN 调用方处于保留状态时，部门或组织可能想要播放自定义公告或自定义音乐。

配置是使用调用保留策略完成的。

> [!NOTE]
> 你负责独立清除和保护所有必要的权限和权限，以便将任何音乐或音频文件与 Microsoft Teams 服务配合使用。 这可能包括所有相关权利人对音频文件中任何音乐、声音效果、音频、品牌、名称和其他内容的知识产权和其他权利。 持有者可以包括艺术家、演员、表演者、音乐家、词曲作者、作曲家、唱片公司、音乐出版商、工会、公会、权利协会、集体管理组织以及拥有、控制或许可音乐版权、音效、音频和其他知识产权的任何其他各方。

### <a name="use-the-teams-admin-center"></a>使用 Teams 管理中心
可以通过创建或编辑呼叫保留策略，使用 Teams 管理中心为用户配置保留的自定义音乐。

若要配置新的调用保留策略，

1. 在 Teams 管理中心，转到 **语音** > **呼叫保留策略**。

2. 选择 **“添加** ”选项卡。

3. 为策略提供名称和说明。

4. 选择 **“上传”文件** 以上传自定义音乐音频文件。

5. 选择“**应用**”。

### <a name="assign-a-custom-call-hold-policy-to-users"></a>为用户分配自定义呼叫保留策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>使用 PowerShell
若要在保留时配置自定义音乐，请在 Teams PowerShell 模块 3.0.0 或更高版本中使用 PowerShell cmdlet New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy 和 Import/Get/Remove/Export-CsOnlineAudioFile。

有关支持的音频格式和最大文件大小，请参阅 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. 确保 Teams 用户在 Teams 调用策略中为已设置为“已启用”的 PSTN 调用方保留音乐。 

2. 上传自定义音频文件。

3. 创建引用自定义音频文件的 Teams 呼叫保留策略，并将其分配给 Teams 用户。

### <a name="upload-the-custom-audio-file"></a>上传自定义音频文件

保留时自定义音乐的配置从上传音频文件开始。 为此，请使用 PowerShell cmdlet [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) 。

下面显示了使用 Windows PowerShell 5.1 上传 MP3 音频文件的示例。 有关其他示例，请参阅 [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)。

```PowerShell
C:\> $content = [System.IO.File]::ReadAllBytes('C:\tmp\customMoH1.mp3')
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>在 Teams 呼叫保留策略中引用音频文件

上传音频文件后，在创建或设置 Teams 呼叫保留策略时，需要使用该文件的 ID 引用 Teams 呼叫保留策略中的文件。 例如：

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

创建新的 Teams 呼叫保留策略后，可以使用Grant-CsTeamsCallHoldPolicy将其授予用户，如下所示：

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

若要获取有关上传音频文件的信息，请使用Get-CsOnlineAudioFile cmdlet。

若要删除上传的音频文件，请使用Remove-CsOnlineAudioFile cmdlet。 在删除音频文件之前，请检查你是否未在 TeamsCallHoldPolicy 中使用该音频文件。

若要导出上传的音频文件，请使用Export-CsOnlineAudioFile cmdlet。

## <a name="feature-availability"></a>功能可用性

下表指示客户端和设备支持“保留音乐”和“保留自定义音乐”的功能。 Microsoft 将继续添加功能支持，因此请经常返回以获取额外的可用性。

| 功能 | 桌面 <br> Windows/Mac OS | 浏览器 | 移动 <br> iOS | 移动 <br> Android | Teams 电话 |
| :------------| :------- | :------- | :------- | :------- | :------- |
| 按住 1：1 PSTN 呼叫 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 |
| 按住 1：1 Teams 呼叫 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 |
| 在 1：1 PSTN 呼叫时保留传输 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | | |
| 在 1：1 Teams 呼叫时保留传输 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐| | | |
| 在 1：1 PSTN 呼叫时保留协商传输 |-音乐保持<br>-保留自定义音乐 || -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 |
| 在 1：1 Teams 呼叫时保留协商转移 |-音乐保持<br>-保留自定义音乐 || -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 | -音乐保持<br>-保留自定义音乐 |

## <a name="restrictions"></a>限制

- 保留音乐仅在商业和 GCC 云实例中可用。

- 仅当用户处于 TeamsOnly 模式时，保留音乐才可用。

- 如果为调用的 Teams 用户启用了Location-Based路由，则只会向调用方播放标准的 Hold 音乐。

- 对于为共享行外观 (委派) 和使用呼叫寄存的用户配置的“保留时自定义音乐”不可用。 将播放标准的保留音乐。

- 在某些情况下，直接路由媒体旁路呼叫将转换为非媒体旁路播放音乐保留，呼叫将保持为非媒体旁路，直到呼叫终止。

## <a name="related-topics"></a>相关主题

- [向用户分配策略](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
