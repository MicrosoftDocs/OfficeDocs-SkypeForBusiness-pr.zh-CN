---
title: 路由对未分配号码的调用
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解如何将呼叫路由到组织中的未分配号码。
ms.openlocfilehash: 3f3d0b9e6962cce7abdb91efa8539dd559c38956
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272297"
---
# <a name="routing-calls-to-unassigned-numbers"></a>路由对未分配号码的调用

作为管理员，可以将呼叫路由到组织中未分配的号码。 例如，你可能希望将调用路由到未分配号码，如下所示： 

- 将给定未分配号码的所有调用路由到自定义公告。

- 将给定未分配号码的所有调用路由到主交换板。

可以将未分配号码的呼叫路由到用户、与自动助理或呼叫队列关联的资源帐户，或者路由到将自定义音频文件播放给调用方的公告服务。

## <a name="configuration"></a>配置

若要将调用路由到未分配的号码，请使用 Teams PowerShell 模块 2.5.1 或更高版本中提供的 New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment cmdlet。

需要指定调用这些数字或号码范围以及调用这些号码的关联路由。 例如，以下命令指定对数字 +1 的所有调用 (555) 222-3333 将路由到资源帐户 aa@contoso.com：

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

下一个示例指定，对号码范围 +1 (555) 333-0000 到 +1 (555) 333-9999 的所有调用都将路由到公告服务，该服务会将音频文件 MainAnnouncement.wav 播放到调用方。

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>注释

- 如果路由到公告，音频文件将播放一次给调用方。

- 若要将呼叫路由到未分配的 Microsoft 呼叫计划订阅者号码，租户需要具有可用 [的通信额度](what-are-communications-credits.md)。

- 若要将呼叫路由到未分配的 Microsoft 呼叫计划服务号码，租户需要至少拥有一个 **Microsoft Teams 电话资源帐户** 许可证。

- 支持的自定义音频文件格式为 WAV (未压缩的线性 PCM，采用单声道或立体声) 的 8/16/32 位深度，WMA (单声道仅) 和 MP3。 音频文件内容不能超过 5 MB。

- 对 Microsoft Teams 的入站呼叫和来自 Microsoft Teams 的出站调用都将根据未分配的号码范围检查调用号码。

- 如果指定的模式/范围包含分配给租户中的用户或资源帐户的电话号码，则对这些电话号码的呼叫将路由到相应的目标，而不会路由到指定的未分配号码处理。 没有对范围内的数字进行其他检查。 如果该范围包含有效的外部电话号码，则将根据处理方式路由从 Microsoft Teams 到该电话号码的出站呼叫。

## <a name="related-topics"></a>相关主题

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
