---
title: 实时事件录制策略
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 了解实时事件录制策略。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: abe4cb004ada98021e74823495e6208fc31c28fb
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486552"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Microsoft Teams 中的实时事件录制策略

有多个用于录制 Microsoft Teams 实时事件的选项。 录制选项是使用录制策略设置的。 本文介绍各种设置。

录制选项是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 设置的](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)。

## <a name="scheduling-and-option-behaviors"></a>计划和选项行为

安排实时事件录制时，有两个组织者选项：

- 可用于制作人和演示者的录制

  - 录制文件：提供制作者和演示者在活动结束后可以下载的录制文件。

- 适用于与会者的录制

  - DVR：数字视频录制器 (DVR) 允许与会者在活动期间倒带和暂停

  - VOD：按需视频 (VOD) 允许与会者在活动结束后观看

## <a name="broadcast-recording-policy-setting"></a>广播录制策略设置

作为广播策略的一部分，有一个设置，你可以切换以打开或关闭直播活动的录制。

| &nbsp;| 可用于制作人和演示者的录制 | 适用于与会者的录制 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Always record               | 已禁用并选中                                | 启用并选中         |
| 组织者可以记录与否 | 默认启用并选择                  | 默认启用并选择   |
| 从不记录               | 已禁用且未选中                            | 已禁用且未选中      |

## <a name="storage-and-persistence-behavior"></a>存储和持久性行为

| 选项                                       | 省/市/自治区   | Dvr                                                   | Vod                                                     | 录制                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 适用于与会者的录制 | 选中     | DVR 可用，Azure 媒体服务 (AMS) 资产存储 180 天 | 与会者可以访问和观看活动                     |                              |
|                                                  | 未选中 | DVR 可用，AMS 资产存储 180 天 | 与会者在活动结束后将无法访问 |                              |
||已禁用 (未选择) |DVR 可用，并在事件后删除 AMS 资产|与会者在活动结束后将无法访问||
| 对制作人和演示者可用的录制 | 选中     |                                                           |                                                             | 创建并存储 MP4 180 天 |
|                                                  | 未选中 |                                                           |                                                             | 未创建文件           |

### <a name="related-topics"></a>相关主题

- [什么是 Teams 实时活动?](what-are-teams-live-events.md)
- [规划 Teams 直播活动](plan-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
- [Teams 云会议录制](../cloud-recording.md)
