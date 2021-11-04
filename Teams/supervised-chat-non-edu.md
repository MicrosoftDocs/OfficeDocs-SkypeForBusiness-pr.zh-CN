---
title: 对非教育租户使用监督式聊天
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解非教育性租户在会议中进行Microsoft Teams聊天。
ms.openlocfilehash: d56a41e3c168aea1d5454fb38ae2aac0c033fe64
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745478"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>非教育租户的监督式聊天

监督式聊天允许指定的主管启动与组织中任何人的聊天，并阻止受限用户启动新聊天，除非有合适的主管。 启用聊天监督后，主管不允许离开聊天，不允许其他参与者删除聊天，从而确保涉及受限用户的聊天受到适当的监管。

这些限制仅适用于在完全启用监督聊天后创建的新私人聊天。 它们不适用于现有私人聊天、会议聊天或频道。

监督式聊天是专门针对教育机构需求定制的，但也可供非教育租户使用。

> [!NOTE]
> 监督聊天保护在强制实施该功能后创建的新聊天。 它不会保护现有聊天。

## <a name="enable-supervised-chat"></a>启用监督聊天

> [!NOTE]
> 在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不需要的受限用户访问不受监督的聊天。

**为环境中每个用户定义聊天权限角色**

要正常使用监督聊天，需要为环境中每个用户分配正确的聊天权限角色。 用户可以分配三个角色：

- 完全权限：此角色应分配给环境中聊天主管。 他们可以开始与环境中的任何用户聊天。 具有完全权限的用户应监督他们参与的聊天。 他们不能离开或从他们启动的聊天或他们在联合租户中监督的聊天中删除。

- 受限权限：此角色非常适合仅对受限用户拥有监督访问权限的员工成员。 他们可以开始与任何完整或受限用户聊天，但不能开始与受限用户聊天。 如果具有完全权限的用户开始与受限用户聊天，可以将受限用户带到对话中。 发生此访问的原因是具有完全权限的用户可以监督受限和受限用户之间的协作。

- 受限权限：此角色非常适合需要监督的用户。 他们只能与具有完全权限的用户开始聊天。 他们可以参与具有完全权限的用户邀请他们参与的任何对话。 在联合聊天案例中，只有具有完全权限的用户（来自受限用户的租户）才能将受限用户添加到聊天中。

若要设置用户的聊天权限角色，请使用管理员门户中消息策略选项内找到的聊天权限Teams策略。 可以使用 PowerShell 通过 ChatPermissionRole 策略定义角色，其值为 Full、Limited 或 Restricted。 此策略位于 [CsTeamsMessagingPolicy 下](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。

无法将角色分配给租户中的来宾。 为来宾分配受限角色。

## <a name="allow-supervised-chat"></a>允许监督聊天

默认情况下，你的租户禁用了监督聊天。 为用户设置聊天权限角色后，可以通过访问组织范围的设置 Teams 设置将基于角色的聊天权限策略设置为"开  >  **"，在** 租户中启用监督 **式聊天**。  也可将 AllowRoleBasedChatPermissions 设置为 True，使用 PowerShell 启用监督式聊天。 此 cmdlet 位于 [CsTeamsClientConfiguration 下](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)。

必须为租户中的所有用户启用监督聊天，并且不能仅为部分用户启用。

**启用聊天**

使用管理中心内提供的现有聊天策略为所有用户Teams聊天。

**维护监督聊天**

最初启用监督聊天后，需要执行一些操作以确保环境中聊天保持监督状态：

- 向加入租户的任何新用户分配相应的角色。 默认情况下，将为用户分配受限角色。

- 如果拥有完全权限的用户离开或从租户中删除，他们监督的聊天将无人参与。 删除原始用户之前，请确保向这些对话添加具有完全权限的另一个用户，以便聊天可以保持监督状态。 删除原始监督者后，无法将新参与者添加到对话，但当前参与者可以继续通信。
