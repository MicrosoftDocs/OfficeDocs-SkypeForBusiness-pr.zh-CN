---
title: 适用于非标准用户的 Teams 应用行为
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解 Microsoft Teams 中的应用对于非标准用户的行为方式。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617845"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>适用于非标准用户的 Microsoft Teams 应用行为

本文介绍 Teams 中的应用在 Teams 上下文中存在来宾 (外部) 和匿名用户时的行为。

- **来宾用户** 不是组织的员工、学生或成员。 他们在贵组织没有学校或工作帐户。

- 外部 **(联合)** 用户属于另一个域，无法访问组织的团队或团队资源。

  > [!Note]
  > 有关来宾用户与外部用户的详细比较， [请参阅与其他组织的用户通信](./communicate-with-users-from-other-organizations.md)。

- 匿名 **用户** 是 Teams 会议中的概念，用户通过链接加入会议。 用户尚未使用其 Microsoft 或组织的帐户登录。

## <a name="guest-user-access"></a>来宾用户访问

### <a name="install-update-and-delete-for-guest-users"></a>为来宾用户安装、更新和删除

来宾无法安装、更新或删除共享上下文中的应用，例如聊天、频道或会议。 他们可以使用消息扩展和直接链接在个人范围内安装、更新或删除应用。 来宾无法访问 Teams 应用商店。

### <a name="usage-behavior-and-policy-for-guest-users"></a>来宾用户的使用行为和策略

如果应用是由本机用户安装的，则来宾可以使用应用。

机器人可以主动向来宾用户发送消息，但来宾无法与机器人交互。 来宾无法向机器人发送消息 1：1、@ 提及机器人，或与与机器人通信的自适应卡交互。

来宾将遵循为任何应用的主机租户设置的全局和组织范围权限策略。 换言之，如果整个宿主组织阻止了应用，则来宾也不可能使用该应用。

设置策略不适用于来宾用户。 这意味着默认策略中的管理员固定应用不会影响来宾用户。

## <a name="external-federated-user-access"></a>联合 (外部) 用户访问权限

### <a name="install-update-and-delete-for-external-users"></a>为外部用户安装、更新和删除

外部用户无法在任何上下文中安装、更新或删除应用，例如个人、聊天、频道或会议。 他们无法访问 Teams 应用商店。

### <a name="usage-behavior-and-policy-for-external-users"></a>外部用户的使用行为和策略

外部用户不能使用任何 Teams 应用，将外部用户添加到具有本机用户的上下文时，所有用户（本机用户和外部用户）都无法再使用应用。

外部用户不会受到应用策略的影响，因为他们无法使用 Teams 应用。

## <a name="anonymous-user-in-meetings-access"></a>会议访问中的匿名用户

### <a name="install-update-and-delete-for-anonymous-users"></a>为匿名用户安装、更新和删除

匿名用户无法安装、更新或删除会议中的应用。

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>匿名用户的使用行为和策略

匿名用户不能直接在会议中使用应用。 如果存在匿名用户，本机用户可以继续使用会议应用。 如果应用在聊天中发送自适应卡片，匿名用户可以与卡交互。有关详细信息，请参阅允许匿名 [用户加入会议](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。

匿名用户将继承用户级全局默认权限策略。 如果用户级权限策略已启用应用，他们可以在 Teams 会议中与应用交互。 匿名用户只能与已在会议中可用的应用交互，并且无法获取和/或管理这些应用。
