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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解如何将呼叫路由到组织中的未分配号码。
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795514"
---
# <a name="routing-calls-to-unassigned-numbers"></a>将呼叫路由到未分配号码

管理员可以将呼叫路由到组织中的未分配号码。 例如，你可能希望将呼叫路由到未分配号码，如下所示： 

- 将对给定未分配号码的所有呼叫路由到自定义公告。

- 将对给定未分配号码的所有呼叫路由到主总机。

可以将呼叫路由到未分配号码的用户、与自动助理或呼叫队列关联的资源帐户，或者路由到将向呼叫方播放自定义音频文件的公告服务。

可以使用 Teams 管理中心或使用 PowerShell 配置未分配号码的路由。

## <a name="use-teams-admin-center"></a>使用 Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **电话号码**”。

2. 在“ **路由规则** ”选项卡上，单击“ **添加**”。

3. 为规则指定名称、说明并指定规则的计算顺序。

4. 确定要添加的规则类型。 可以选择预配置电话号码模式类型并完成模式和路由选项的规则。 还可以选择“高级设置”，在其中直接输入电话号码模式和路由选项的正则表达式。

5. 选择“**保存**”。

还可以直接为未分配的电话号码创建路由规则。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **电话号码**”。

2. 在“ **号码** ”选项卡上，选择未分配的电话号码，然后单击视图顶部的“ **路由** ”

4. 为规则指定名称、说明并指定规则的计算顺序。

4. 选择路由选项。

5. 选择“**保存**”。

可以使用“测试编号”功能测试路由规则。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **电话号码**”。

2. 在“ **路由规则** ”选项卡上，单击“ **测试编号**”。

3. 直接输入电话号码或单击“ **选择号码** ”，然后从下拉列表中选择一个未分配的电话号码。

4. 选择“ **测试**”。


## <a name="use-powershell"></a>使用 PowerShell

若要将呼叫路由到未分配号码，请使用 Teams PowerShell 模块 2.5.1 或更高版本中提供的 New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment cmdlet。

需要指定被调用号码或号码范围，以及对这些号码的调用关联的路由。 例如，以下命令指定对数字 +1 (555) 222-3333 的所有调用都将路由到资源帐户 aa@contoso.com：

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

下一个示例指定对号码范围 +1 (555) 333-0000 到 +1 (555) 333-9999 的所有呼叫都将路由到公告服务，该服务将向调用方播放音频文件 MainAnnouncement.wav。

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>注释

- 如果路由到通知，音频文件将播放给调用方一次。

- 若要将呼叫路由到未分配的 Microsoft 通话套餐订阅者号码，租户需要具有可用的 [通信额度](what-are-communications-credits.md)。

- 若要将呼叫路由到未分配的 Microsoft 通话套餐服务号码，租户需要至少有一 **个Microsoft Teams 电话资源帐户** 许可证。

- 自定义音频文件支持的格式为 WAV (未压缩的线性 PCM、单声道或立体声) 中深度为 8/16/32 位的线性 PCM、WMA (仅单声道) 和 MP3。 音频文件内容不能超过 5 MB。

> [!NOTE]
> 你负责独立清除和保护与 Microsoft Teams 服务一起使用任何音乐或音频文件的所有必要权限。 这可能包括所有相关权利持有人在音频文件中的任何音乐、音效、音频、品牌、名称和其他内容的知识产权和其他权利。 持有者可能包括艺术家、演员、表演者、音乐家、词曲作者、作曲家、唱片公司、音乐出版商、工会、公会、权利协会、集体管理组织以及拥有、控制或许可音乐版权、音效、音频和其他知识产权的任何其他方。

- 对 Microsoft Teams 的入站呼叫和来自 Microsoft Teams 的出站呼叫都将根据未分配号码范围检查呼叫号码。

- 如果指定的模式/范围包含分配给租户中用户或资源帐户的电话号码，则对这些电话号码的呼叫将路由到相应的目标，而不是路由到指定的未分配号码处理。 没有对范围中的数字进行其他检查。 如果范围包含有效的外部电话号码，则会根据处理方式路由从 Microsoft Teams 到该电话号码的出站呼叫。


## <a name="related-topics"></a>相关主题

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
