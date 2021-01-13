---
title: 在 Microsoft Teams 中为用户设置会议拨出确认
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何设置 Teams 以请求拨出确认，以防止当被呼叫者无法接听呼叫时语音邮件系统连接到会议。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806142"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>在 Microsoft Teams 中为用户设置会议拨出确认

会议拨出和呼叫我是非常有用的方法，用于邀请参与者加入会议，以及让现有参与者使用传统或移动电话加入会议。 但是，当被呼叫者无法接听呼叫并且呼叫由语音邮件系统应答时，语音邮件系统将连接到会议，参与者将能够收听它，直到从会议中删除它。

若要防止当会议拨出发送到电话号码且被呼叫者无法接听呼叫时语音邮件系统连接到会议，你可以设置 Teams 以请求被呼叫者确认他们加入会议。 如果被呼叫者无法接听呼叫，并且呼叫由语音邮件系统应答，则语音邮件系统不会连接到会议，因为它不会提供加入会议确认。

启用此功能后，接听电话拨出或呼叫我的人必须通过在传统电话或移动电话上按 1 确认他们想要加入会议。

若要为组织的所有会议启用此功能，请设置 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数 ```true``` 。 要执行此操作，请运行以下命令：

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相关主题

- [为用户设置“致电我”功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)