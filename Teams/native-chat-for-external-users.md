---
title: Microsoft Teams 中外部 (联合) 用户的本机聊天体验
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解两个用户都 (处于 TeamsOnly 升级模式的 Microsoft Teams 中联合) 用户进行外部访问的本机 Teams 聊天体验。
ms.openlocfilehash: 134216364fdd7397d8a7d72a2ae6684cfa9f90b4
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198874"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams 中外部 (联合) 用户的本机聊天体验

当Microsoft Teams 用户与外部 (联合) 用户聊天时，聊天体验仅限于文本。 但是，如果你的 Teams 用户和其他组织中的人员都处于 TeamsOnly 升级模式，则可以获得“本机 Teams 聊天体验”，其中包括丰富的格式设置、@mentions和其他聊天功能。

其他组织中的人员的本机聊天体验已为所有 Teams 租户启用，但并非所有人员都符合条件。 若要提供本机聊天体验，需要为 TeamsOnly 升级模式配置发送方和接收方。 若要详细了解升级策略，请阅读 [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

若要查看 Teams 中外部访问用户的功能列表，请参阅 [比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何实现知道我是否在本机聊天中？

如果只能在聊天中与其他组织中的人员交换文本，则处于标准外部访问 (联合) 聊天中。 如果你有其他聊天功能，包括格式设置、@mentions、表情符号等，则你正在进行本机 Teams 聊天。 

Teams 会定期检查其他组织中的人员的升级模式，当发现他们在 TeamsOnly 升级模式下运行 Teams 时，系统会提示你切换到本机 Teams 聊天并锁定原始聊天。

切换到本机 Teams 聊天时，Teams 不会合并这两个对话。 相反，你将在聊天源中看到这两个聊天。 新的本机 Teams 聊天处于活动状态，但旧的纯文本聊天已锁定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果用户不再处于“仅 Teams”模式，会发生什么情况？

如果你与其他组织中的人员进行了本机 Teams 聊天，然后你们中的一个人被切换出 TeamsOnly 升级模式，Teams 会锁定本机 Teams 聊天，并为你提供一个链接，用于有限的纯文本聊天。 你将无法在本机 Teams 聊天中继续。 你仍然可以阅读本机 Teams 聊天，但无法继续在那里进行对话。

如果 Teams 发现与此人进行旧的纯文本聊天，它将恢复该聊天。 否则，Teams 会创建新的纯文本聊天。


## <a name="related-topics"></a>相关主题

[在 Teams 中管理外部访问](manage-external-access.md)
