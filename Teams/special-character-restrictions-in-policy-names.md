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
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192161"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>什么是团队策略中的特殊字符限制？

**虽然可以在工作组中创建的策略的名称中使用特殊字符，我们强烈建议您不。**

策略名称为会议、 聊天和 prescense，创建并在团队中的其他事项可以具有特殊字符，如 @，#、 $。 但是，如果您想要更改业务管理中心中的 Microsoft 团队和 Skype 的名称，将看不到。 您必须使用 Windows PowerShell 和正确的策略 cmdlet 进行更改。

例如，如果您有一个会议策略与特殊字符，并且想要更改名称或名称中删除特殊字符，您需要使用集 CsMeetingPolicy cmdlet。 

下面是您可能需要执行此操作的策略 cmdlet 的列表：
1. 设置 CsMeetingPolicy
2. 设置 CsAppPolicy
3. Set-*


