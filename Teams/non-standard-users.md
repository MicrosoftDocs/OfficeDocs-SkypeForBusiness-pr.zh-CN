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
ms.openlocfilehash: d7b79371cdc8ff5109bf67b1c78639106a83a95e
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796645"
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

外部用户无法在任何上下文中安装、更新或删除应用，例如个人、聊天、频道或会议。 他们无法访问托管组织的Teams应用商店。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部用户的使用行为和策略

- 其他组织中的人员遵守托管组织的全局 (组织范围内的默认) 策略
- 托管组织中的用户可以在与其他组织人员的会议聊天中添加应用。 其他组织中的人员不能在会议聊天中添加应用，但一旦添加到聊天中，就可以与机器人、选项卡和消息扩展进行交互。
- 在会议聊天中安装机器人后，它可以主动与参与该聊天的其他组织中的人员通信，并且这些用户可以与机器人通信。
- 将应用托管组织的数据策略，以及该用户的组织共享的任何第三方应用的数据共享做法。

## <a name="anonymous-users"></a>匿名用户

### <a name="install-update-and-delete-for-anonymous-users"></a>为匿名用户安装、更新和删除

匿名用户无法安装、更新或删除会议中的应用。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名用户的使用行为和策略

匿名用户不能直接在会议中使用应用。 如果存在匿名用户，本机用户可以继续使用会议应用。 如果应用在聊天中发送自适应卡，匿名用户可以与该卡交互。 有关详细信息，请阅读 [允许匿名用户加入会议](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。

匿名用户将继承用户级全局默认权限策略。 如果用户级权限策略已启用Teams，他们可以与会议中的应用交互。 匿名用户只能与已在会议中可用的应用交互，并且无法获取和/或管理这些应用。
