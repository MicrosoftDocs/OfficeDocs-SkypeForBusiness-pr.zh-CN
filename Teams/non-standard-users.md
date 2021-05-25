---
title: Teams标准用户的应用行为
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解应用Microsoft Teams标准用户的行为方式。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628921"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams标准用户的应用行为

本文介绍当来宾Teams外部用户 (联合用户) 和匿名用户时，Teams的行为。

- **来宾用户** 不是组织的员工、学生或成员。 他们在贵组织没有学校或工作帐户。

- 外部 **(联合)** 用户属于另一个域，无法访问组织的团队或团队资源。

  > [!Note]
  > 有关来宾用户与外部用户的详细比较， [请参阅与其他组织的用户通信](./communicate-with-users-from-other-organizations.md)。

- 匿名 **用户** 是用户通过Teams加入会议的会议中的概念。 用户尚未使用其 Microsoft 或组织的帐户登录。

## <a name="guest-users"></a>来宾用户

### <a name="install-update-and-delete-for-guest-users"></a>为来宾用户安装、更新和删除

来宾无法安装、更新或删除应用到共享上下文（如聊天、频道或会议）中，但他们可以使用消息扩展和直接链接访问其个人范围。 来宾无法从桌面Teams访问 Teams应用商店，但可以使用直接链接访问它。

### <a name="usage-behavior-and-policy-for-guest-users"></a>来宾用户的使用行为和策略 

如果应用是由本机用户安装的，则来宾可以使用应用。

#### <a name="bots-installed-to-a-channel"></a>安装到通道的机器人

机器人可以主动向来宾用户发送消息，但来宾无法与机器人交互。 来宾无法一对一地向机器人发送消息、提及机器人，或与与机器人通信的自适应卡交互。

#### <a name="personal-bots-installed-with-policies"></a>使用策略安装的个人机器人

- 来宾将遵循为任何应用的主机租户设置的全局和组织范围权限策略。 如果整个主机组织阻止了应用，则来宾也不可能使用该应用。
- 还会为来宾安装全局默认应用设置策略中包含的任何机器人。
- 安装机器人后，机器人可以主动与来宾通信，来宾可以与机器人重新通信。
- 无法从全局默认应用设置策略中删除来宾。
- 若要避免来宾访问机器人，可以创建更多应用设置策略，将其分配给内部用户，然后使用自定义策略安装机器人。

## <a name="external-federated-users"></a>外部 (联合) 用户

### <a name="install-update-and-delete-for-external-users"></a>为外部用户安装、更新和删除

外部用户无法在任何上下文中安装、更新或删除应用，例如个人、聊天、频道或会议。 他们无法访问应用商店Teams应用。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部用户的使用行为和策略

- 外部用户不能使用任何Teams，并且当将外部用户添加到具有本机用户的上下文中时，所有用户（本机用户和外部用户）都无法再使用应用。
- 外部用户不会受到应用策略的影响，因为他们不能Teams应用。

## <a name="anonymous-users"></a>匿名用户

### <a name="install-update-and-delete-for-anonymous-users"></a>为匿名用户安装、更新和删除

匿名用户无法安装、更新或删除会议中的应用。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名用户的使用行为和策略

匿名用户不能直接在会议中使用应用。 如果存在匿名用户，本机用户可以继续使用会议应用。 如果应用在聊天中发送自适应卡，匿名用户可以与该卡交互。 有关详细信息，请阅读 [允许匿名用户加入会议](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。

匿名用户将继承用户级全局默认权限策略。 如果用户级权限策略已启用Teams，他们可以与会议中的应用交互。 匿名用户只能与已在会议中可用的应用交互，并且无法获取和/或管理这些应用。
