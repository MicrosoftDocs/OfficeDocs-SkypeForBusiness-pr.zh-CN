---
title: 面板上的签入和Microsoft Teams释放
ms.author: czawideh
author: cazawideh
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
description: 本文提供有关如何在面板设备上启用签入和Teams发布的指导。
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689052"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>面板上的签入和Microsoft Teams释放

启用签入和会议室释放后，用户Teams会议开始时预订的会议室的面板上登录。 如果用户未在会议开始时间后的一定时间内签入，会议室将拒绝会议邀请，向会议组织者发送取消消息，会议室可供其他人保留。  

## <a name="requirements"></a>要求 

此功能可在独立部署面板部署Teams使用。 还可以将 Teams 面板与 Android 上的 Teams 会议室 与应用版本 1449/1.0.96.2022011305 或更高版本配对，了解其他功能，如签入通知。  

## <a name="enable-check-in-and-room-release"></a>启用签入和房间释放 

默认情况下，签入和房间释放已关闭。 若要将其打开，  

1. 在Teams"面板上，使用管理员凭据登录。  

2. 转到"**设置 >"设置 >"设置 >"应用设置 >会议"**。

3. 如果没有人检查，请打开"发布空间"。

4. 若要调整用户在房间释放前必须签入的时间量，请转到"发布后" **，** 然后从下拉列表中选择一个选项。  

当Teams面板与 Android Teams会议室配对时，用户可以在会议室中签入加入Teams会议。  

## <a name="turn-on-check-in-notifications"></a>打开签入通知

> [!NOTE]
> 此功能目前仅在与 Android Teams会议室配对的 Teams 面板上可用。 Teams面板Teams聊天室必须登录到同一资源帐户。 若要[了解Teams，](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)请参阅将 Teams 面板与 Android Microsoft Teams会议室配对。  

当会议继续超过其保留的时间段时，将发送签入通知。 下一次会议中的用户进入后，通知将显示在预定的会议开始时间的会议室显示前，让以前的会议参与者知道他们的预订已结束，并且用户正在等待空间。  

若要打开签入通知，  

1. 在Teams"面板上，使用管理员凭据登录。 

2. 转到"**设置 >"设置 >"设置 >"应用设置 >会议"**。

3. 转到 **"签入"并** 打开" **发送签入通知"**。

## <a name="related-topics"></a>相关主题

- [如何使用Microsoft Teams面板](use-teams-panels.md)

- [Microsoft Teams面板](teams-panels.md)