---
title: 实时事件录制策略
author: cichur
ms.author: v-mahoffman
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
ms.openlocfilehash: 01fe1b00a4c8367dfd9c1274e3591a03b3c09634
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769800"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>实时事件录制策略Microsoft Teams

你有几个选项用于录制实时Microsoft Teams活动。 录制选项是使用录制策略设置的。 本文介绍各种设置。

录制选项是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 设置的](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)。

## <a name="scheduling-and-option-behaviors"></a>计划和选项行为

安排实时事件录制时，有两个组织者选项：

- 录制者与演示者可用

  - 录制文件：提供录制文件，制作者和演示者可在事件结束后下载该文件。

- 可用于与会者的录制

  - DVR：使用 DVR (数字) ，与会者可以在活动期间后退和暂停

  - VOD：使用 VOD (点播) ，与会者可以在活动结束后观看

## <a name="broadcast-recording-policy-setting"></a>广播录制策略设置

作为广播策略的一部分，有一个设置可以切换为为实时事件打开或关闭录制。

| &nbsp;| 录制者与演示者可用 | 可用于与会者的录制 |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| 始终记录               | 已禁用和已选择                                | 启用和选择         |
| 组织者可以录制或不录制 | 默认情况下启用和选择                  | 默认情况下启用和选择   |
| 从不录制               | 已禁用且未选中                            | 已禁用且未选中      |

## <a name="storage-and-persistence-behavior"></a>存储和持久性行为

| 选项                                       | 省/市/自治区   | DVR                                                   | VOD                                                     | 录制                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 可用于与会者的录制 | 选中     | DVR 可用，AZURE 媒体服务 (AMS) 资产存储 180 天 | 与会者可以访问和观看活动                     |                              |
|                                                  | 未选中 | DVR 可用，AMS 资产存储 180 天 | 结束后，与会者无法访问事件 |                              |
||已禁用 (未选中) |DVR 可用，事件后将删除 AMS 资产|结束后，与会者无法访问事件||
| 可供制作者和演示者使用的记录 | 选中     |                                                           |                                                             | 创建并存储 MP4 |
|                                                  | 未选中 |                                                           |                                                             | 未创建任何文件           |

### <a name="related-topics"></a>相关主题

- [什么是 Teams 实时活动?](what-are-teams-live-events.md)
- [规划 Teams 实时事件](plan-for-teams-live-events.md)
- [配置 Teams 实时事件设置](configure-teams-live-events.md)
- [Teams云会议录制](../cloud-recording.md)
