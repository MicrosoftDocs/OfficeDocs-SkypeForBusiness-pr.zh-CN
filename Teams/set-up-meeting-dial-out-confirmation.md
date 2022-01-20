---
title: 在"会议"中为用户设置会议拨出Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何设置Teams以请求拨出确认，以防止呼叫者无法接听呼叫时语音邮件系统连接到会议。
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32cdc63f2b129e7d925fed46a8b89ac90944926e
ms.sourcegitcommit: bb302109886a4b853a8e493fb0ffafad4bc4f86b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2022
ms.locfileid: "62085231"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>在"会议"中为用户设置会议拨出Microsoft Teams

会议拨出和呼叫我是邀请参与者加入会议以及让现有参与者使用传统或移动电话加入会议非常有用的方法。 但是，当被呼叫者无法接听呼叫并且呼叫由语音邮件系统应答时，语音邮件系统将连接到会议。 参与者将能够收听它，直到从会议中删除它。

若要防止将会议拨出发送到电话号码且被呼叫者无法接听呼叫时语音邮件系统连接到会议，你可以设置 Teams 以请求被呼叫者确认他们加入会议。 如果被呼叫者无法接听呼叫且呼叫由语音邮件系统应答，则语音邮件系统不会连接到会议，因为它不会提供加入会议确认。

启用此功能后，收到拨出或呼叫我呼叫的人必须通过在传统电话或移动电话上按 1 或说"确定"来确认他们想要加入会议。 确认将阻止用户的语音邮件加入会议。

若要为组织的所有会议启用此功能，请设置 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数 ```true``` 。 若要设置此参数，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相关主题

- [为用户设置“致电我”功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
