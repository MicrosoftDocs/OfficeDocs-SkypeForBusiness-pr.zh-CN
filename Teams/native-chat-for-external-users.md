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
ms.openlocfilehash: 3d94c55dc184d80edbc22be53f1df18c256423c5aa04b7e342b8964463db1aa7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350594"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>针对本地用户 (联合) 的本机聊天Microsoft Teams

当Microsoft Teams用户与联合 (外部) 聊天时，聊天体验仅限于文本。 但是，如果你的 Teams 用户和另一个组织中的人员都采用 TeamsOnly 升级模式，则你可以拥有"本机 Teams 聊天体验"，其中包括丰富的格式、@mentions 和其他聊天功能。 本机Teams仅与其他组织人员进行 1 对 1 聊天。

为其他组织中的人员启用的本机聊天体验针对所有租户Teams，但并非所有人员都符合条件。 若要提供本机聊天体验，需为发送方和接收者配置 TeamsOnly 升级模式。 若要详细了解升级策略，请阅读 [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

若要在外部访问中查看外部访问用户的功能Teams，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我是否参与本机聊天？

如果只能与其他组织人员交换聊天中的文本，则你使用标准外部访问 (联合) 聊天。 如果你具有其他聊天功能，包括格式、@mentions、表情符号等，则你使用本机聊天Teams聊天。 

Teams针对其他组织中的人员定期检查升级模式，当发现他们在 TeamsOnly 升级模式下运行 Teams 时，它会提示你切换到本机 Teams 聊天并锁定原始聊天。

当你切换到本机聊天Teams，Teams不会合并这两个对话。 相反，你将在聊天源中看到这两个聊天。 新的本机Teams聊天处于活动状态，但旧的纯文本聊天已锁定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果用户不再在"仅Teams模式，会发生什么情况？

如果你与其他组织中的Teams进行了本机 Teams 聊天，然后其中一人退出 TeamsOnly 升级模式，Teams 会锁定本机 Teams 聊天，并为你提供仅限文本的有限聊天的链接。 你将无法继续本机聊天Teams聊天。 你仍然可以阅读本机Teams聊天，但无法继续在那里聊天。

如果Teams找到了与此人的旧纯文本聊天，它将恢复该聊天。 否则，Teams创建新的纯文本聊天。


## <a name="related-topics"></a>相关主题

[管理 Teams 中的外部Teams](manage-external-access.md)
