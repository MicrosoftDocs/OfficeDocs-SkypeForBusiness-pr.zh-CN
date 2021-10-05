---
title: 流Teams会议
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 了解如何为会议设置和管理流Teams流。
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127540"
---
# <a name="stream-teams-meetings"></a>流Teams会议

本文将帮助你为会议设置Teams流。

## <a name="what-is-streaming-and-how-does-it-work"></a>什么是流式处理？它如何工作？

通过流式处理，您的组织可以扩大你的市场范围，为与会者提供更多会议选项。 启用流式传输时，组织者可以通过向 Teams 中的内置自定义流式处理应用提供 Real-Time 消息传送协议 (RTMP) URL 和密钥，将会议和网络研讨会流式传输到外部终结点。

> [!NOTE]
> 无法流式传输实时事件。

## <a name="set-up-streaming-with-powershell"></a>使用 PowerShell 设置流式处理

可以使用 PowerShell 为组织设置流式处理。 目前，此策略在管理中心Teams可用。 按用户策略用于指定 **谁** 可以启用实时流式处理。 默认情况下处于禁用状态。

可以在 **Set-CsTeamsMeetingPolicy** cmdlet Windows PowerShell 以下属性来设置流式处理。 有关 cmdlet 详细信息，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

- LiveStreamingMode

将 **LiveStreamingMode** 设置为 **Enabled，** 为一个或多个用户启用流式处理功能。

> [!IMPORTANT]
> 必须启用会议注册，组织者才能流式传输网络研讨会。 有关详细信息，请参阅 [设置网络研讨会](set-up-webinars.md)。

### <a name="assign-the-policy"></a>分配策略

若要详细了解如何使用 PowerShell 分配策略，请参阅在 Teams[中分配策略](policy-assignment-overview.md)。

## <a name="related-topics"></a>相关主题

- [在 Teams 中分配策略](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [快速入门 - 会议、网络研讨会和直播活动](quick-start-meetings-live-events.md)