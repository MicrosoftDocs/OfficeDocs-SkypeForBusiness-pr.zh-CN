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
ms.openlocfilehash: 12f8be910c713a9ce023ac17c956ef50f5889792
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268977"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>记录&听录的会议策略设置

本文介绍特定于录制和听录的会议策略设置，包括：

- [允许转录](#allow-transcription)
- [允许云录制](#allow-cloud-recording)
- [将录制内容存储在国家或地区之外](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>允许转录

这是按组织者和按用户策略的组合。 此设置控制播放会议录制内容期间是否提供字幕和转录功能。 启动录制的人员需要打开此设置，才能使用这些功能进行录制。

启用此设置将创建与会议记录一起存储的脚本，它在会议录制内容中启用“**搜索**”、“**CC**”和“**脚本**”。

录制会议的听录目前仅支持在 Teams 会议中将其语言设置为或说英语的用户。

## <a name="allow-cloud-recording"></a>允许云录制

此设置是每个组织者和每个用户策略的组合，并控制是否可以记录会议。 如果为参与者启用了策略设置，并且他们是来自同一组织的经过身份验证的用户，则会议组织者或其他会议参与者可以启动录制。

组织之外的人员，如联合和匿名用户，无法启动录制。 来宾用户无法启动或停止录制。

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

查看以下示例。

|用户 |会议策略  |允许云录制 |
|---------|---------|---------|
|Daniela | 全局   | 关闭 |
|Amanda | Location1MeetingPolicy | 开|
|John (外部用户) | 不适用 | 不适用|

- 达妮拉组织的会议无法录制。
- 阿曼达无法录制丹妮拉组织的会议。
- 可以录制阿曼达组织的会议。
- 丹妮拉无法录制阿曼达组织的会议。
- 约翰无法录制阿曼达组织的会议。

若要了解有关云会议记录的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>将录制内容存储在国家或地区之外

此策略控制会议记录是否可以永久存储在另一个国家或地区。 如果已启用，则无法迁移录制内容。 有关云会议和记录存储位置的详细信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

## <a name="related-topics"></a>相关主题

- [在 Teams 中为用户分配策略](policy-assignment-overview.md)
- [云会议录制](cloud-recording.md)
- [Microsoft Teams 中的会议策略和会议过期](meeting-expiration.md)
