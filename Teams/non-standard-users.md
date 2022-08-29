---
title: 基于用户类型的 Teams 应用行为
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解 Microsoft Teams 中的应用如何以不同的方式为来宾、联合用户和匿名用户工作。
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 940c021b18c390a7b5c9ec0f8a3325c49c87dae5
ms.sourcegitcommit: 903abff4ce79c10bf1fb936b8ad71f6315a43c18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2022
ms.locfileid: "67278596"
---
# <a name="behavior-of-microsoft-teams-apps-based-on-types-of-in-meeting-users"></a>基于会议内用户类型的 Microsoft Teams 应用的行为

当来宾、外部 (联合) 和匿名用户出现在 Teams 上下文中时，Teams 应用的行为。

* **来宾用户** 不是组织的员工、学生或成员。 他们在贵组织没有学校或工作帐户。

* **外部 (联合) 用户** 来自另一个域，无法访问组织的 Teams 资源。

  > [!Note]
  > 有关来宾用户和外部用户之间的更详细比较，请参阅 [与其他组织的用户进行通信](./communicate-with-users-from-other-organizations.md)。

* **匿名用户** 是通过链接加入会议的用户。 用户未使用其 Microsoft 帐户或其组织的帐户登录。

## <a name="guests"></a>来宾

### <a name="install-update-and-delete-for-guests"></a>为来宾安装、更新和删除

来宾无法将应用安装、更新或删除到共享上下文中，例如聊天、频道或会议。 来宾可以使用消息扩展和直接链接在其个人范围内执行此操作。 来宾无法从 Teams 桌面应用访问 Teams 应用商店，但可以使用直接链接访问该应用商店。

### <a name="usage-behavior-and-policy-for-guests"></a>来宾的使用行为和策略

如果应用是由本机用户安装的，则来宾可以使用应用。

#### <a name="bots-installed-to-a-channel"></a>安装到通道的机器人

来宾可以提及机器人并与自适应卡片交互。

#### <a name="personal-bots-installed-with-policies"></a>使用策略安装的个人机器人

* 对于任何应用，来宾都遵循为主机组织设置的全局权限和组织范围的权限策略。 如果整个主机组织阻止了应用，则来宾也不能使用该应用。
* 还将为来宾安装全局默认应用设置策略中包含的任何机器人。
* 安装机器人后，机器人可以主动与来宾通信，来宾可以与机器人通信。
* 无法从全局默认应用设置策略中删除来宾。
* 为了避免来宾访问机器人，可以创建更多应用设置策略，将其分配给内部用户，并使用自定义策略安装机器人。

## <a name="federated-users"></a>联合用户

### <a name="install-update-and-delete-for-federated-users"></a>为联合用户安装、更新和删除

联合用户无法在任何上下文（例如个人、聊天、频道或会议）中安装、更新或删除应用。 他们无权访问托管组织的 Teams 应用商店。

### <a name="usage-behavior-and-policy-for-federated-users"></a>联合用户的使用行为和策略

* 来自其他组织的人员遵守托管组织的全局 (组织范围的默认) 策略
* 托管组织中的用户可以在与其他组织人员的会议聊天中添加应用。 来自其他组织的人员无法在会议聊天中添加应用，但可以在添加到聊天后与机器人、选项卡和消息扩展进行交互。
* 在会议聊天中安装机器人后，它可以主动与聊天中其他组织中的人员通信，并且这些用户可以与机器人通信。
* 将应用托管组织的数据策略。
* 应用该用户组织共享的任何第三方应用的数据共享做法。

## <a name="anonymous-users"></a>匿名用户

### <a name="install-update-and-delete-for-anonymous-users"></a>为匿名用户安装、更新和删除

匿名用户无法在会议中安装、更新或删除应用。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名用户的使用行为和策略

匿名用户不能直接在会议中使用应用。 如果应用在聊天中发送自适应卡片，匿名用户可以与该卡进行交互。 如果用户级别的权限策略启用了应用，则此类用户可以在 Teams 会议中与应用交互。 匿名用户继承用户级全局默认权限策略。

匿名用户只能与会议中已有可用但无法获取和管理此类应用的应用进行交互。 即使匿名用户正在参加会议，本机用户也可以继续使用会议应用。

## <a name="see-also"></a>另请参阅

* [允许匿名用户加入会议](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。
* [在 Microsoft Teams 中管理应用设置策略](teams-app-setup-policies.md)。
