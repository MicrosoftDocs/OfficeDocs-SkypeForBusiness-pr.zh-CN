---
title: 将呼叫路由到未分配号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解如何将呼叫路由到组织中未分配号码。
ms.openlocfilehash: f53e83b3d4f26123feed70bdecad32cb45bc5588
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442790"
---
# <a name="routing-calls-to-unassigned-numbers"></a>将呼叫路由到未分配号码

作为管理员，可以将呼叫路由到组织中未分配号码。 例如，你可能希望将调用路由到未分配号码，如下所示： 

- 将所有调用路由到给定的未分配号码到自定义公告。

- 将所有调用路由到给定的未分配号码到主切换板。

可以将对未分配号码的呼叫路由到用户、与 自动助理 或呼叫队列关联的资源帐户，或者路由到将为呼叫者播放自定义音频文件的公告服务。

## <a name="configuration"></a>配置

若要将调用路由到未分配号码，请使用 Teams PowerShell 模块 2.5.1 或更高版本中提供的 New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment cmdlet。

需要指定被叫号码或号码范围，以及调用这些号码的关联路由。 例如，以下命令指定对号码 +1 (555) 222-3333 的所有调用都将路由到资源帐户 aa@contoso.com：

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

下一个示例指定对号码范围 +1 (555) 333-0000 到 +1 (555) 333-9999 的所有调用都将路由到公告服务，它将向调用方播放音频文件 MainAnnouncement.wav。

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>注释

- 如果路由到公告，音频文件将播放一次给调用方。

- 若要将呼叫路由到未分配的 Microsoft 呼叫计划订阅者号码，租户需要具有可用的 [通信积分](what-are-communications-credits.md)。

- 若要将调用路由到未分配的 Microsoft 呼叫计划服务号码，租户至少需要具有一电话系统 – 虚拟用户许可证。

- 支持自定义音频文件的格式是 WAV (未压缩的线性 PCM，单声道或立体声) 中深度为 8/16/32 位，WMA (单声道) 和 MP3。 音频文件内容不能超过 5 MB。

## <a name="related-topics"></a>相关主题

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
