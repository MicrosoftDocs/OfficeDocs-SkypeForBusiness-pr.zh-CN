---
title: Microsoft Teams面板上的签入和会议室发布
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: 本文提供有关如何启用签入和会议室发布Teams面板设备的指导。
ms.openlocfilehash: a1fc01b349a2189ab2f5ca09ff6b856338fbcdbb
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761274"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Microsoft Teams面板上的签入和会议室发布

启用签入和会议室释放后，用户会在会议开始时保留的会议室内签入Teams面板。 如果用户在会议开始时间之后的一定时间内未签入，会议室会拒绝会议邀请，向会议组织者发送取消消息，并且会议室可供其他人保留。  

## <a name="requirements"></a>要求 

此功能可在独立Teams 面板部署中使用。 还可以使用应用版本 1449/1.0.96.202011305 或更高版本Android Teams 会议室配对 Teams面板，以获取其他功能，如签入通知。  

## <a name="enable-check-in-and-room-release"></a>启用签入和会议室发布 

默认情况下，签入和会议室版本处于关闭状态。 若要将其打开，  

1. 在Teams 面板上，使用管理员凭据登录。  

2. 转到 **设置 >会议>管理设置> 管理员设置> Teams设备设置**。

3. 如果没有人签入，请打开发布室。

4. 若要调整用户在会议室发布前必须签入的时间量，请转到 **“发布”后：** 从下拉列表中选择一个选项。  

当Teams面板与Android上的Teams会议室配对时，用户可以在Teams会议室中签入会议。  

## <a name="turn-on-check-in-notifications"></a>打开签入通知

> [!NOTE]
> 此功能目前仅适用于与Android上的Teams会议室配对的Teams面板。 Teams 面板和Teams室必须登录到同一资源帐户。 有关详细信息，请参阅[Android上将Teams 面板与Microsoft Teams会议室配对](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)。  

当会议继续超过其预留时间段时，将发送签入通知。 下一次会议的用户签入后，通知将显示在其计划的会议开始时间的会议室前部显示，以便上一个会议参与者知道他们的预订已结束，用户正在等待空间。  

若要打开签入通知，请执行以下操作：  

1. 在Teams 面板上，使用管理员凭据登录。 

2. 转到 **设置 >会议>管理设置> 管理员设置> Teams设备设置**。

3. 转到 **签入** 并打开 **“发送签入通知**”。

## <a name="related-topics"></a>相关主题

- [如何使用Microsoft Teams面板](use-teams-panels.md)

- [Microsoft Teams面板](teams-panels.md)
