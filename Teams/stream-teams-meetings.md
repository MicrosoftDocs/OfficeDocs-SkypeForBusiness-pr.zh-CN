---
title: 流式传输Teams会议
author: mkbond007
ms.author: mabond
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
description: 了解如何为Teams会议设置和管理流式处理。
ms.openlocfilehash: 352a0c2e7a0584640e466b5e46456906e4912d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646341"
---
# <a name="stream-teams-meetings"></a>流式传输Teams会议

本文将帮助你为Teams会议设置流式处理。

## <a name="what-is-streaming-and-how-does-it-work"></a>什么是流式处理及其工作原理？

通过流式处理，组织可以扩展你的覆盖范围，并为与会者提供更多会议选项。 启用流式处理时，组织者可以通过向Teams中的内置自定义流式处理应用提供Real-Time消息传送协议 (RTMP) URL 和密钥，将会议和网络研讨会流式传输到外部终结点。

> [!NOTE]
> 无法流式传输实时事件。

## <a name="set-up-streaming-with-powershell"></a>使用 PowerShell 设置流式处理

可以使用 PowerShell 为组织设置流式处理。 目前，此策略在Teams管理中心不可用。 每个用户策略用于指定 **谁** 可以启用实时流式处理。 默认情况下处于禁用状态。

可以在 Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet 中使用以下属性来设置流式处理。 有关 cmdlet 的详细信息，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

- LiveStreamingMode

将 **LiveStreamingMode** 设置为 **“已启用** ”，以便为一个或多个用户启用流式处理功能。

> [!IMPORTANT]
> 你必须先启用会议注册，然后组织者才能流式传输网络研讨会。 有关详细信息，请参阅 [“设置网络研讨会](set-up-webinars.md)”。

### <a name="assign-the-policy"></a>分配策略

有关如何使用 PowerShell 分配策略的详细信息，请参阅 [Teams 中的分配策略](policy-assignment-overview.md)。

## <a name="related-topics"></a>相关主题

- [在Teams中分配策略](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [快速入门 - 会议、网络研讨会和直播活动](quick-start-meetings-live-events.md)