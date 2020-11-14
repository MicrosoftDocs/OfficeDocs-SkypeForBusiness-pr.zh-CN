---
title: Microsoft 团队中的外部 (联盟) 用户的本机聊天体验
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Microsoft 团队中的外部 access (联盟) 用户在 TeamsOnly 升级模式下可用的外部用户之间的本地团队聊天体验。
ms.openlocfilehash: d3ff414420f8d1d68965307e9303aed4b5cf00ff
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030598"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft 团队中的外部 (联盟) 用户的本机聊天体验
======================================

当 Microsoft 团队用户与外部 (联合) 用户聊天时，聊天体验仅限于文本。 但是，如果你的团队用户和外部用户都在 TeamsOnly 升级模式下，你可以拥有 "本机团队聊天体验"，其中包括丰富的格式、@mentions 和其他聊天功能。 换句话说，你可以与符合条件的外部用户进行相同的丰富的1:1 团队聊天体验，就像在你的组织中的用户一样。 与外部用户的本机团队聊天仅限于1:1 聊天 (外部用户无法) 群组聊天。

适用于外部用户的本机聊天体验已针对所有团队租户启用，但并非所有用户都符合资格。 若要提供本机聊天体验，需要为 TeamsOnly 升级模式配置发送方和接收方。 若要了解有关升级策略的详细信息，请阅读 [设置你的共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

若要查看团队外部 access 用户的功能列表，请参阅 [比较外部和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我是否正在进行本机聊天？

如果你只能与外部用户交换你的聊天中的文本，则你使用的是标准的外部访问 (联合) 聊天。 如果您已获得所有其他聊天功能，包括格式、@mentions、表情符号等，则您正在使用您的外部用户进行本地团队聊天。 

团队会定期检查外部用户的升级模式，当它在 TeamsOnly 升级模式中找到运行团队的外部用户时，它将提示你切换到本机团队聊天并锁定原始聊天。

切换到本机团队聊天时，团队不会合并这两个对话。 你可以在聊天源中看到这两个聊天。 新的本机团队聊天处于活动状态，但旧的、纯文本的聊天已被锁定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果用户不再属于 "仅工作组" 模式，会发生什么情况？

如果您有一个本机团队与外部用户聊天，然后您将其中一个 TeamsOnly 升级模式切换出，则团队会锁定本机团队聊天，并为您提供仅限文本的有限聊天的链接。 你将无法继续参与本机团队聊天。 您仍然可以阅读本机团队聊天，但不能继续对话。

如果团队发现此外部用户的旧的纯文本聊天，它将恢复该聊天。 否则，团队会创建新的纯文本聊天。


## <a name="related-topics"></a>相关主题

[管理团队中的外部访问](manage-external-access.md)
