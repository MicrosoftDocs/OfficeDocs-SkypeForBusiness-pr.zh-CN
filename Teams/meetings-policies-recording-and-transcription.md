---
title: 管理用于录制和听录的会议策略
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 了解如何在 Teams 中管理用于录制和听录的会议策略设置。
ms.openlocfilehash: 57e90984cde312f1804d5d2144c82a4d252822b6
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466200"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>记录&听录的会议策略设置

本文介绍特定于 Teams 会议中录制和听录的会议策略设置。 可以在“**会议会议** > ”策略下的团队管理中心中找到这些设置。

## <a name="transcription"></a>转录

这是按组织者和按用户策略的组合。 此设置控制播放会议录制内容期间是否提供字幕和转录功能。 启动录制的人员需要打开此设置，才能使用这些功能进行录制。

启用此设置将创建与会议记录一起存储的脚本，它在会议录制内容中启用“**搜索**”、“**CC**”和“**脚本**”。

录制会议的听录目前仅支持在 Teams 会议中将其语言设置为或说英语的用户。

## <a name="cloud-recording"></a>云录制

此设置是每个组织者和每个用户策略的组合，并控制是否可以记录会议。 如果为参与者启用了策略设置，并且他们是来自同一组织的经过身份验证的用户，则会议组织者或其他会议参与者可以启动录制。

组织之外的人员，如联合和匿名用户，无法启动录制。 来宾无法开始或停止录制。

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

查看以下示例。

| 用户                 | 会议策略         | 允许云录制 |
|----------------------|------------------------|-----------------------|
| Daniela              | 全局                 | 关闭                   |
| Amanda               | Location1MeetingPolicy | 开                    |
| John (外部)  | 不适用         | 不适用        |

- 达妮拉组织的会议无法录制。
- 阿曼达无法录制丹妮拉组织的会议。
- 可以录制阿曼达组织的会议。
- 丹妮拉无法录制阿曼达组织的会议。
- 约翰无法录制阿曼达组织的会议。

若要了解有关云会议记录的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="meetings-automatically-expire"></a>会议自动过期

此设置控制会议录制是否自动过期。 打开此设置后，你将获得设置默认过期时间（以天为单位）的选项。

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="来自 Teams 管理中心自动会议过期设置的屏幕截图。":::

此设置提供了一个简单的工具，可减少旧录制使用的存储量。 OneDrive 和 SharePoint 系统将监视所有会议录制的过期设置，并在记录到期日期自动将录制内容移动到回收站。

### <a name="default-expiration-time"></a>默认过期时间

所有新创建的会议录制都将默认过期 120 天：启用此功能后创建的所有录制将在创建日期后 120 天内删除。

> [!NOTE]
> A1 用户的最大默认过期时间为 30 天。

#### <a name="changing-default-expiration-time"></a>更改默认过期时间

管理员可以在 PowerShell 或 Teams 管理中心编辑默认过期时间设置。 任何更改只会影响新创建的会议录制，从该时间点开始;它们不会影响在该日期之前创建的任何录制。

管理员无法更改现有会议录制的过期时间。 这样做是为了保护拥有录制内容的用户的决定。 会议和通话都可以由此设置控制。

过期值是数天的整数。  可按如下所示设置：

- 最小值： **1**
- 最大值： **99999**
- 还可以在 PowerShell 中将过期时间设置为 **-1** ，以便录制不会过期。

示例 PowerShell 命令：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>合规性

不应依赖会议过期设置来获得法律保护，因为最终用户可以修改他们控制的任何录制的过期日期。

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>在 Microsoft Purview 中记录过期设置和 Microsoft 365 保留策略

文件保留优先于文件删除。 在保留期完成之前，Teams 会议记录过期策略无法删除使用 Purview 保留策略录制的 Teams 会议。 例如，如果你有 Purview 保留策略，该策略显示文件将保留 5 年，并且 Teams 会议录制过期策略设置为 60 天，则 Teams 会议录制过期策略将在五年后删除录制。

如果 Teams 会议记录过期策略和 Purview 删除策略具有不同的删除日期，则将在两个日期中最早删除该文件。 例如，如果你有 Purview 删除策略，该策略显示文件将在一年后删除，并且 Teams 会议记录过期时间设置为 120 天，则 Teams 会议记录过期策略将在 120 天后删除该文件。

用户可以在过期日期之前手动删除其录制内容，除非存在阻止录制的 Purview 保留策略。

### <a name="deletion-of-recordings"></a>删除录制内容

录制通常在过期日期后的一天内删除，但在极少数情况下可能需要长达五天的时间。 文件所有者将在录制过期时收到电子邮件通知，并将定向到回收站以恢复录制。

> [!NOTE]
> 在到期日期，记录将移入回收站，并清除过期日期字段。 如果从回收站恢复录制，则此功能不会再删除该记录，因为过期日期已清除。

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>从Stream (经典) 迁移的录音过期

从Stream (经典) 迁移的录制不会附带过期设置。 相反，我们鼓励管理员只迁移要保留的录制。 有关更多详细信息，请参阅[Stream (经典) 迁移文档](/stream/streamnew/stream-classic-to-new-migration-overview)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>将录制内容存储在国家或地区之外

此策略控制会议记录是否可以永久存储在另一个国家或地区。 如果已启用，则无法迁移录制内容。 有关云会议和记录存储位置的详细信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="related-topics"></a>相关主题

- [管理 Teams 中的会议策略](meeting-policies-overview.md)
- [在 Teams 中为用户分配策略](policy-assignment-overview.md)
- [云会议录制](cloud-recording.md)
- [管理谁可以安排会议](manage-who-can-schedule-meetings.md)
