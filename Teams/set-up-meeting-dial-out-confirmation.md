---
title: 为 Microsoft 团队中的用户设置会议拨出-确认
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何设置团队请求拨出确认，以防止语音邮件系统在呼叫的人员无法接听呼叫时连接到会议。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339468"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>为 Microsoft 团队中的用户设置会议拨出确认

"拨出" 和 "呼叫我来电" 是一种非常有用的方法，可邀请参与者加入会议，并让现有参与者使用传统电话或移动电话加入会议。 但是，当被呼叫的人员无法接听呼叫且呼叫由语音邮件系统接听时，语音邮件系统将连接到会议，参与者将能够收听该会议，直到将其从会议中删除。

若要防止语音邮件系统在将会议拨出发送到电话号码并且被呼叫人无法接听呼叫时连接到会议，您可以将团队设置为请求来自被呼叫人员的确认，以便他们加入会议。 如果被呼叫的人员无法接听呼叫，并且呼叫由语音邮件系统接听，则语音邮件系统不会连接到会议，因为它不会提供加入确认。

启用此功能后，接收拨出或呼叫我呼叫的人员必须确认他们希望通过在其传统电话或移动电话上按1加入会议。

若要为组织中的所有会议启用此功能，请```EnableDialOutJoinConfirmation```将[set-csonlinedialinconferencingtenantsettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数设置为```true```。 要执行此操作，请运行以下命令：

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相关主题

- [为用户设置“致电我”功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)