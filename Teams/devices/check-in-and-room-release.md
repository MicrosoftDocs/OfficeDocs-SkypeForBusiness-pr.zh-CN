---
title: Microsoft Teams 面板上的签入和会议室发布
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
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: 本文提供有关如何启用签入和会议室发布 Teams 面板设备的指南。
ms.openlocfilehash: d5998049faf1e3c8c25b3e49470291bb20f97eea
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801853"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Microsoft Teams 面板上的签入和会议室发布

启用签入和会议室发布后，用户在会议开始时预留的会议室中签入 Teams 面板。 如果用户在会议开始时间后的设定时间内未签入，会议室将拒绝会议邀请，向会议组织者发送取消消息，并且会议室可供其他人预订。  

## <a name="requirements"></a>要求 

此功能可用于独立Teams 面板部署。 你还可以将 Android 上具有 Teams 会议室 的 Teams 面板与应用版本 1449/1.0.96.2022011305 或更高版本配对，以获取其他功能，例如签入通知。

与Teams 面板关联的共享邮箱需要设置正确的时区才能使此功能正常工作。 有关如何为共享邮箱设置时区的信息，请参阅 [Outlook 网页版 中共享邮箱的时区设置](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting)。

## <a name="enable-check-in-and-room-release"></a>启用签入和会议室发布 

默认情况下，“签入”和“会议室释放”处于关闭状态。 若要将其打开，  

1. 在Teams 面板，使用管理员凭据登录。  

2. 转到 **“设置>设备设置> 管理员设置> Teams 管理员设置>会议**”。

3. **如果没有人签入，请打开“发布室**”。

4. 若要调整用户在释放会议室之前必须签入的时间，请转到“ **之后的发布：** ”，然后从下拉列表中选择一个选项。  

当 Teams 面板与 Android 上的 Teams 会议室配对时，用户可以签入 Teams 会议室中的会议。  

## <a name="turn-on-check-in-notifications"></a>启用签入通知

> [!NOTE]
> 此功能目前仅在与 Android 上的 Teams 会议室配对的 Teams 面板上可用。 Teams 面板和 Teams 会议室必须登录到同一资源帐户。 有关详细信息[，请参阅将Teams 面板与 Android 上的 Microsoft Teams 会议室配对](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)。  

当会议继续超过其保留的时间段时，将发送签入通知。 下一个会议中的用户签入后，通知将显示在其计划会议开始时间的会议室屏幕的正面，以便让上一个会议参与者知道他们的预留已结束，并且人们正在等待空间。  

若要打开签入通知，  

1. 在Teams 面板，使用管理员凭据登录。 

2. 转到 **“设置>设备设置> 管理员设置> Teams 管理员设置>会议**”。

3. 转到 **“签入”** 并打开 **“发送签入通知**”。

## <a name="related-topics"></a>相关主题

- [如何使用 Microsoft Teams 面板](use-teams-panels.md)

- [Microsoft Teams 面板](teams-panels.md)
