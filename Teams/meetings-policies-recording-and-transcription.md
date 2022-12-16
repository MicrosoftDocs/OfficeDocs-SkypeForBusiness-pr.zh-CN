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
ms.openlocfilehash: 06a05d2eb8a8c1542b79fa4c37b68ea4a3aa6d32
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436759"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>用于录制&听录的会议策略设置

本文介绍 Teams 会议中特定于录制和听录的会议策略设置。 可以在团队管理中心的会议 **会议** > **策略** 下找到这些设置。

## <a name="transcription"></a>转录

这是按组织者和按用户策略的组合。 此设置控制播放会议录制内容期间是否提供字幕和转录功能。 启动录制的人员需要打开此设置，才能使用这些功能进行录制。

启用此设置将创建与会议记录一起存储的脚本，它在会议录制内容中启用“**搜索**”、“**CC**”和“**脚本**”。

## <a name="cloud-recording"></a>云录制

此设置是按组织者和按用户策略的组合，控制是否可以录制会议。 如果为参与者启用了策略设置，并且他们是来自同一组织的经过身份验证的用户，则会议组织者或其他会议参与者可以开始录制。

组织之外的人员，如联合和匿名用户，无法启动录制。 来宾无法启动或停止录制。

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

查看以下示例。

| 用户                 | 会议策略         | 允许云录制 |
|----------------------|------------------------|-----------------------|
| Daniela              | 全局                 | 关闭                   |
| Amanda               | Location1MeetingPolicy | 开                    |
| John (外部)  | 不适用         | 不适用        |

- 无法录制由 Daniela 组织的会议。
- 阿曼达无法录制丹尼尔拉组织的会议。
- 可以录制由 Amanda 组织的会议。
- 丹妮拉无法录制阿曼达组织的会议。
- 约翰不能录制阿曼达组织的会议。

若要了解有关云会议记录的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="meetings-automatically-expire"></a>会议自动过期

此设置控制会议录制内容是否自动过期。 启用此设置后，你将获得设置默认过期时间（以天为单位）的选项。

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Teams 管理中心的屏幕截图，其中显示了自动会议过期设置。":::

此设置提供了一个简单的工具，可减少旧录制使用的存储量。 OneDrive 和 SharePoint 系统将监视所有会议录制的过期设置，并在过期日期自动将录制内容移动到回收站。

### <a name="default-expiration-time"></a>默认过期时间

所有新创建的会议录制的默认到期时间为 120 天;启用此功能后创建的所有录制内容将在创建日期后的 120 天后删除。

> [!NOTE]
> A1 用户的最大默认过期时间为 30 天。

#### <a name="changing-default-expiration-time"></a>更改默认过期时间

管理员可以在 PowerShell 或 Teams 管理中心中编辑默认过期时间设置。 任何更改将仅影响从该点开始新建的会议录制;它们不会影响在该日期之前创建的任何录制。

管理员无法更改现有会议录制的过期时间。 这样做是为了保护拥有录制内容的用户的决定。 此设置可以控制会议和通话。

过期值是天数的整数。  可按如下所示设置：

- 最小值： **1**
- 最大值： **99999**
- 还可以在 PowerShell 中将过期时间设置为 **-1** ，以便录制永不过期。

示例 PowerShell 命令：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>合规性

不应依赖会议过期设置来获得法律保护，因为最终用户可以修改他们控制的任何录制的到期日期。

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>在 Microsoft Purview 中记录过期设置和Microsoft 365 个保留策略

文件保留优先于文件删除。 在保留期结束后，Teams 会议录制过期策略无法删除具有 Purview 保留策略的 Teams 会议录制。 例如，如果你有一个 Purview 保留策略，其中指出文件将保留五年，并且 Teams 会议录制过期策略设置为 60 天，Teams 会议录制过期策略将在五年后永久删除录制内容。

如果 Teams 会议录制过期策略和 Purview 删除策略具有不同的删除日期，则会在两个日期中的最早删除该文件。 例如，如果你有一个 Purview 删除策略，指出文件将在一年后删除，并且 Teams 会议录制过期设置为 120 天，Teams 会议录制过期策略将在 120 天后删除该文件。

用户可以在过期日期之前手动删除其录制内容，除非存在阻止录制的 Purview 保留策略。 如果用户手动删除了仍在保留期内的录制内容，则录制内容将保存在保留库中。 但是，录制内容将显示为已删除给最终用户。 若要了解详细信息，请参阅 [了解 SharePoint 和 OneDrive 的保留期](/microsoft-365/compliance/retention-policies-sharepoint#how-retention-works-for-sharepoint-and-onedrive)。

### <a name="deletion-of-recordings"></a>删除录制内容

记录通常会在到期日期后的一天内删除，但在极少数情况下可能需要长达五天的时间。 录制内容过期时，文件所有者将收到电子邮件通知，并会定向到回收站以恢复录制内容。

> [!NOTE]
> 在到期日期，录制内容将移至回收站，并清除过期日期字段。 如果从回收站恢复录制内容，则此功能不会再次删除该记录，因为过期日期已清除。

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>从Stream (经典) 迁移的录制的过期

从Stream (经典) 迁移的录制内容不会对其设置过期。 相反，我们鼓励管理员仅迁移他们想要保留的录制内容。 可以在[Stream (经典) 迁移文档中](/stream/streamnew/stream-classic-to-new-migration-overview)找到更多详细信息。

## <a name="store-recordings-outside-of-your-country-or-region"></a>将录制内容存储在国家或地区之外

此策略控制是否可以将会议记录永久存储在另一个国家或地区。 如果已启用，则无法迁移录制内容。 有关云会议以及录制内容存储位置的详细信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="related-topics"></a>相关主题

- [管理 Teams 中的会议策略](meeting-policies-overview.md)
- [将策略分配给 Teams 中的用户](policy-assignment-overview.md)
- [云会议录制](cloud-recording.md)
- [管理谁可以安排会议](manage-who-can-schedule-meetings.md)
