---
title: 针对本地用户 (联合) 的本机聊天Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 了解在两Teams TeamsOnly 升级模式下 (联合) 用户Microsoft Teams外部访问的本机聊天聊天体验。
ms.openlocfilehash: 992b4dd28d17f1ba8abf7217d622da18813c3118
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138228"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>针对本地用户 (联合) 的本机聊天Microsoft Teams

当Microsoft Teams用户与外部用户 (聊天) ，聊天体验仅限于文本。 但是，如果你的 Teams 用户和另一个组织中的人员都采用 TeamsOnly 升级模式，则你可以拥有"本机 Teams 聊天体验"，其中包括丰富的格式、@mentions 和其他聊天功能。

为其他组织中的人员启用所有租户的本机聊天Teams，但并非所有人员都有资格。 若要提供本机聊天体验，需要为发送方和接收者配置 TeamsOnly 升级模式。 若要详细了解升级策略，请阅读 [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

若要在外部访问中查看外部访问用户的功能Teams，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我是否参与本机聊天？

如果只能与其他组织中的人员交换聊天中的文本，则你使用标准外部访问 (联合) 聊天。 如果你有其他聊天功能，包括格式、@mentions、表情符号等，则你使用本机聊天Teams聊天。 

Teams组织内部人员定期检查升级模式，当发现他们在 TeamsOnly 升级模式下运行 Teams 时，它会提示切换到本机 Teams 聊天并锁定原始聊天。

当你切换到本机聊天Teams，Teams不会合并这两个对话。 相反，你将在聊天源中看到这两个聊天。 新的本机Teams聊天处于活动状态，但旧的纯文本聊天已锁定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果用户不再在"仅Teams模式，会发生什么情况？

如果你与其他组织中的Teams进行本机 Teams 聊天，然后你中的一个人退出 TeamsOnly 升级模式，Teams 会锁定本机 Teams 聊天，并为你提供仅限文本的有限聊天的链接。 你将无法继续本机聊天Teams聊天。 你仍然可以阅读本机Teams聊天，但无法继续在那里聊天。

如果Teams找到了与此人的旧纯文本聊天，它将恢复该聊天。 否则，Teams创建新的纯文本聊天。


## <a name="related-topics"></a>相关主题

[在 Teams 中管理外部Teams](manage-external-access.md)
