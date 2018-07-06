---
title: 什么是团队策略中的特殊字符限制？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: 请参阅有与特殊字符的策略和解决办法可以执行的操作的名称中哪些问题。
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205075"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>什么是团队策略中的特殊字符限制？

**虽然可以使用 PowerShell 创建团队策略使用特殊字符，您将在管理这些策略限制。 因此，我们强烈建议策略名称不包含特殊字符。**

策略名称创建会议使用 PowerShell 和聊天中团队可以如具有特殊字符 @，#、 $。 但是，如果您希望编辑业务管理中心中的 Microsoft 团队和 Skype 的策略，将看不到。 您必须使用 Windows PowerShell 和正确的策略 cmdlet 进行更改。

如果您具有特殊字符的策略对象和您想要移除的特殊字符，以便更好地管理业务管理中心中的 Microsoft 团队和 Skype 的策略，您将需要使用以下过程。 

注意： 明确提出的过程在此处使用的消息策略的示例。  通过 subsituting 相关的 cmdlet，将为另一种策略类型 （例如会议） 使用相同的过程。 

1) 调用 Get-CSMessagingPolicy-identity < old_policy_name > 和捕获的策略的输出。
2)。 呼叫设置 CSMessagingPolicy-identity < new_policy_name > 具有相同的配置的原始策略但不包含任何特殊字符，在名称中创建新策略。
3)。 呼叫删除 CSMessagingPolicy-要删除的策略的标识 < old_policy_name >。  如果此命令成功执行，在您完成，并可以开始将用户分配给业务管理中心的使用 PowerShell 或 Microsoft 团队和 Skype 的新策略。
4。) 如果以上命令不成功，这是因为旧策略已分配给用户。  运行取消分配 cmdlet，以取消该策略分配给用户，分配新的策略，然后再次运行 dwlete。


