---
title: 邮件委派
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 用户可以在其状态消息中将另一用户显式设置为代理人。
ms.openlocfilehash: be7092d2a68010d00a2d214f12bfe9011d44bbc5
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "35119481"
---
# <a name="set-a-delegate-in-a-status-message"></a>在状态邮件中设置代理人

用户可以已将其状态显式设置为 "离开" 或 "请勿打扰", 并提供自定义文本。 委派功能允许他们在文本状态消息中 @username 提及另一个用户, 并建议在文本状态消息中提及另一用户, 而不是希望与他们联系的人与 @username 的用户联系。 尝试联系它们的人可以将其悬停在命名委派上, 并轻松地将其发送给他们。  被分配为代理人的人员将收到通知, 告知他们已被命名为代理人。

这是客户端中的用户启动的进程, 不需要管理员参与。

## <a name="delegation-use-scenario-in-healthcare"></a>医疗保健中的委派使用方案

*没有设置代理人的用法示例:* Franco Piccio 在放射科的部门通话。 他收到了一次紧急个人通话, 并且在接下来的几个小时内必须退出。 他在放射科的 Lena Ehrle 中询问了他的某位同事, 以便在他离开时覆盖他。 他在 Ehrle 上, 他一直在上监听紧急消息和 ping 并在 Piccio 上代表, 并在她的当前责任的同时作出响应。 团队中的其他人可能无法实现非正式委派, 并且 ensues 患者的护理造成混淆。

*设置代理人的用法示例:* Franco Piccio 在放射科的部门通话。 他收到了一次紧急个人通话, 并且在接下来的几个小时内必须退出。 他在放射 Lena Ehrle 时, 他将向他提出他的一位同事。 他将更改其自定义状态消息, 以表达类似于 "我在今后几小时内不可用的内容。 请联系 @DrEhrle, 获取任何紧急情况。 "  团队中的其他人在尝试联系 Piccio 时遇到委派问题, 因此他们现在知道立即联系 Dr. Ehrle。 Ensues 患者的护理很少, 不会造成混淆。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>团队客户端中的用户状态的共存模式的影响

管理员应注意, 状态说明和委托提及将部分地依赖于用户的共存模式。 此矩阵显示了可能性:

|共存模式 | 预期行为|
|---|---|
|TeamsOnly |用户只能从团队设置笔记。 <br> 用户的团队备注在团队 & SfB 中可见。 |
|群岛 | 仅在团队中可见的团队中的用户备注集。 <br> SfB 中的用户备注集仅在 SfB 中可见 |
|SfB * 模式 | 用户只能从 SfB 设置笔记。 <br> 用户的 SfB 备注在 SfB & 团队中可见。  |
|||

如果用户的模式为 TeamsOnly 或孤岛, 则用户仅可在团队中设置注释。  

### <a name="displaying-notes-set-in-skype-for-business"></a>在 Skype for Business 中显示备注集
  
不显示从 Skype for Business 设置笔记的视觉指示。

Skype for Business 不会对状态注释强制执行字符限制。 Microsoft 团队将仅显示 Skype for Business 中的笔记集的前280个字符。 末尾的省略号 (...) 指示截断。
  
Skype for Business 不支持对笔记的到期时间。

当用户升级到 TeamsOnly 模式时, 不支持从 Skype for Business 迁移到团队的笔记。

## <a name="configure-allowing-clients-to-use-delegates"></a>配置允许客户使用代理人

此功能不需要 Microsoft 团队管理中心的配置或使用 PowerShell。 在支持它的租户中, 默认情况下, 它在团队客户端中可用。

## <a name="related-topics"></a>相关主题

[与 Skype for Business 共存](../../coexistence-chat-calls-presence.md)
