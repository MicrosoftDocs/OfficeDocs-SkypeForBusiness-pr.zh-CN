---
title: 管理用于录制和听录的会议策略
author: KarliStites
ms.author: kastites
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
description: 了解如何在录制和听录Teams管理会议策略设置。
ms.openlocfilehash: c89fc88c46ae8b614021417ab2aa02832f64fce1
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973174"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>用于录制听录&会议策略设置

本文介绍特定于录制和听录的会议策略设置，包括以下内容：

- [允许转录](#allow-transcription)
- [允许云录制](#allow-cloud-recording)
- [在自己国家/地区之外存储录制内容](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>允许转录

这是按组织者和按用户策略的组合。 此设置控制播放会议录制内容期间是否提供字幕和转录功能。 如果关闭此设置，则播放会议录制期间，"搜索"和"抄送"选项将不可用。  启动录制的人员需要打开此设置，以便录制内容也包含脚本。

目前仅录制的会议的听录功能仅支持在会议中设置其语言或Teams英语的用户。

## <a name="allow-cloud-recording"></a>允许云录制

此设置是按组织者和按用户策略的组合，用于控制是否可以录制会议。 如果为参与者打开策略设置，并且他们是同一组织的经过身份验证的用户，则会议组织者或其他会议参与者可以启动录制。

组织之外的人员，如联合和匿名用户，无法启动录制。 来宾用户无法启动或停止录制。

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

查看以下示例。

|用户 |会议策略  |允许云录制 |
|---------|---------|---------|
|Daniela | 全局   | 关闭 |
|Amanda | Location1MeetingPolicy | 开|
|John (外部用户) | 不适用 | 不适用|

- 无法录制由 Daniela 组织的会议。
- Amanda 无法录制 Daniela 组织的会议。
- 可以录制 Amanda 组织的会议。
- Daniela 无法录制 Amanda 组织的会议。
- John 无法录制 Amanda 组织的会议。

若要了解有关云会议记录的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>在自己国家/地区之外存储录制内容

此策略控制会议记录是否可以永久存储在另一个国家/地区。 如果已启用，则不能迁移录制内容。 有关云会议和录制内容存储位置详细信息，请参阅Teams[录制的云会议](cloud-recording.md)。

## <a name="related-topics"></a>相关主题

- [向用户分配策略Teams](policy-assignment-overview.md)
- [云会议录制](cloud-recording.md)