---
title: Microsoft Teams 中外部用户 (联合) 的本机聊天体验
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
description: 了解 Microsoft Teams 中两个用户都 (Teams) 用户进行外部访问的本机 Teams 聊天体验。
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055654"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams 中外部用户 (联合) 的本机聊天体验

当 Microsoft Teams 用户与联合 (外部用户) 时，聊天体验仅限于文本。 但是，如果你的 Teams 用户和另一个组织中人员都采用 TeamsOnly 升级模式，则你可以拥有"本机 Teams 聊天体验"，其中包括丰富的格式、@mentions和其他聊天功能。 换言之，可以与其他组织中符合条件的人员具有相同的 1：1 Teams 聊天体验，就像与组织中用户一样。 与其他组织中的人员进行本机 Teams 聊天仅限于 1：1 聊天。

为其他组织中的人员启用针对所有 Teams 租户的本机聊天体验，但并非所有人员都符合条件。 若要提供本机聊天体验，需为发送方和接收者配置 TeamsOnly 升级模式。 若要了解有关升级策略的信息，请阅读["设置共存和升级设置"。](setting-your-coexistence-and-upgrade-settings.md)

若要在 Teams 中查看外部访问用户的功能列表，请参阅["比较外部访问和来宾访问"。](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我是否参与本机聊天？

如果只能在与其他组织人员聊天中交换文本，则使用标准外部访问 (联合) 聊天。 如果你已获得了所有其他聊天功能（包括格式、@mentions、表情符号等），则你正在本机 Teams 聊天中。 

Teams 会定期检查其他组织中的人员升级模式，当发现他们在 TeamsOnly 升级模式下运行 Teams 时，它会提示你切换到本机 Teams 聊天并锁定原始聊天。

切换到本机 Teams 聊天时，Teams 不会合并这两个对话。 相反，你将在聊天源中看到这两个聊天。 新的本机 Teams 聊天处于活动状态，但旧式纯文本聊天已锁定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果用户不再使用"仅 Teams"模式，会发生什么情况？

如果你与其他组织中的人员进行了本机 Teams 聊天，然后其中一人退出 TeamsOnly 升级模式，则 Teams 会锁定本机 Teams 聊天，并为你提供仅限文本的有限聊天的链接。 你将无法继续本机 Teams 聊天。 你仍然可以阅读本机 Teams 聊天，但无法继续在那里的对话。

如果 Teams 找到了与此人的旧纯文本聊天，它将恢复该聊天。 否则，Teams 会创建新的纯文本聊天。


## <a name="related-topics"></a>相关主题

[在 Teams 中管理外部访问](manage-external-access.md)
