---
title: 消息委派
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 了解状态为“离开”或“请勿打扰”的用户如何在其状态消息中明确将其他用户设置为代理人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 967ed83f89d991ad001dbac9001d4d20b412efec80f0edb5bf4caca77e487a87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276527"
---
# <a name="message-delegation"></a>消息委派

用户可将其状态明确设置为“离开”或“请勿打扰”，并提供自定义文本。 消息委派功能的工作原理如下：

1. 用户 @username 在文本状态消息中提及另一个用户，表明当自己没空时，想要联系他们的人可联系 @username 提及的用户。
2. 被指派为代理人的用户将收到通知，知晓自己被指定为代理人。
3. 随后，试图联系第一个用户的某人将鼠标悬停在指定的代理人上，即可轻松地向代理人发送消息。  

这是用户在客户端中启动的过程，无需管理员参与即可启用该功能。 

## <a name="delegation-use-scenario-in-healthcare"></a>医疗保健方面的委派使用方案

*未设置代理人的使用示例：* Franco Piccio 医生正在放射科值班。 他接到一个紧急私人电话，不得不在接下来的几个小时离开。 他请放射科的一位同事 Lena Ehrle 医生在他离开后顶替他值班。 他非正式地将其寻呼机移交给 Ehrle 医生，Ehrle 医生除了本职工作之外，还要负责接听寻呼机上的紧急消息和传呼，并代表 Piccio 医生回复它们。 团队的其他成员可能并未意识到发生了非正式委派，并且患者医治混乱随之而来。

*设置代理人的使用示例：* Franco Piccio 医生正在放射科值班。 他接到一个紧急私人电话，不得不在接下来的几个小时离开。 他请放射科的一位同事 Lena Ehrle 医生在他离开后顶替他值班。 他更改了自己的自定义状态消息，文字类似于“我接下来的几个小时没空。 如有任何紧急情况，请联系 @DrEhrle。”  团队的其他成员在尝试联系 Piccio 医生时会意识到发生了委派，因此他们现在知道在此期间应联系 Ehrle 医生。 患者医治方面很少甚至不会发生混乱。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>共存模式对 Teams 客户端中的用户状态的影响

管理员应注意，状态备注和委派提及行为取决于用户的共存模式。 此列表显示了可能性：

|共存模式 | 预期行为|
|---|---|
|TeamsOnly |用户只能从 Teams 设置备注。 <br> 用户的 Teams 备注在Teams 和 SfB 中可见。 |
|Islands | 在 Teams 中设置的用户备注仅在 Teams 中可见。 <br> 在 SfB 中设置的用户备注仅在 SfB 中可见 |
|SfB* 模式 | 用户只能从 SfB 设置备注。 <br> 用户的 SfB 备注在 SfB 和 Teams 中可见。  |
|||

只有当用户的模式是 TeamsOnly 或 Islands 时，才能在 Teams 中设置备注。  

### <a name="displaying-notes-set-in-skype-for-business"></a>显示 Skype for Business 中设置的备注
  
没有直观的迹象表明备注是从 Skype for Business 设置的。

Skype for Business 对于状态备注不强制实施字符限制。 Microsoft Teams 将仅显示从 Skype for Business 设置的备注的前 280 个字符。 备注末尾的省略号 (…) 表示截断。
  
Skype for Business 不支持备注的过期时间。

当用户升级到 TeamsOnly 模式时，不支持将备注从 Skype for Business 迁移到 Teams。

## <a name="related-topics"></a>相关主题

[与 Skype for Business 共存](../../coexistence-chat-calls-presence.md)
