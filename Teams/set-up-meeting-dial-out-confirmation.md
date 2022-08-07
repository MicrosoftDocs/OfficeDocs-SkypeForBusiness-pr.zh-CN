---
title: 在 Microsoft Teams 中为用户设置会议拨出确认
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何设置 Teams 以请求拨出确认，以防止语音邮件系统在呼叫人员无法接听呼叫时连接到会议。
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271557"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>在 Microsoft Teams 中为用户设置会议拨号确认

会议拨号和呼叫我是邀请参与者加入会议和现有参与者使用传统或移动电话加入会议的有用方式。 但是，当被调用者无法接听呼叫并且呼叫由语音邮件系统接听时，语音邮件系统将连接到会议。 参与者将能够听它，直到它从会议中删除。

若要防止语音邮件系统在会议拨号发送到电话号码且被调用人员无法接听呼叫时连接到会议，可以设置 Teams 以请求被调用人员的确认，以便他们加入会议。 如果被调用的人员无法接听呼叫，并且呼叫由语音邮件系统接听，则语音邮件系统将无法连接到会议，因为它不会提供加入会议的确认。

启用此功能后，接收拨号或拨打我电话的用户必须通过在传统或移动电话上按 1 或说“好吧”来确认自己是否要加入会议。 确认将阻止用户的语音邮件加入会议。

若要为组织中的所有会议启用此功能，请将 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数设置```EnableDialOutJoinConfirmation```为 ```true```。 若要设置此参数，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相关主题

- [为用户设置“致电我”功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
