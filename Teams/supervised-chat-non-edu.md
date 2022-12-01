---
title: 对非教育租户使用监督聊天
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解 Microsoft Teams 会议中非教育版租户的监督式聊天。
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc7ddf23b600ec2a7f4d4f02c2328587627572fc
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198284"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>非教育租户的监督式聊天

监督式聊天允许指定的主管与其组织中的任何人发起聊天，并阻止受限用户启动新聊天，除非有相应的主管。 启用聊天监督后，主管不得离开聊天，其他参与者也不允许将其删除，从而确保对涉及受限用户的聊天进行适当的监督。

这些限制仅适用于在完全启用监督聊天后创建的新私人聊天。 它们不适用于现有的私人聊天、会议聊天或频道。

监督式聊天是针对教育机构需求定制的，但也可供非教育租户使用。

> [!NOTE]
> 监督式聊天保护在强制实施该功能后创建的新聊天。 它无法保护现有聊天。

## <a name="enable-supervised-chat"></a>启用监督聊天

> [!NOTE]
> 在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不必要的受限用户访问无监督聊天。

**为环境中的每个用户定义聊天权限角色**：

若要按预期运行监督式聊天，需要为环境中的每个用户分配正确的聊天权限角色。 用户可以分配三个角色：

- 完全权限：应将此角色分配给环境中的聊天主管。 他们可以开始与环境中的任何用户聊天。 具有完全权限的用户应监督他们参与的聊天。 他们不能离开或从他们启动的聊天或他们在联合租户中监督的聊天中删除。

- 受限权限：此角色非常适合仅对受限用户具有监督访问权限的员工。 他们可以开始与任何完整用户或受限用户聊天，但无法开始与受限用户聊天。 如果具有完全权限的用户开始与受限用户的聊天，则可以将受限用户引入对话。 发生此访问是因为具有完全权限的用户用于监督受限用户和受限用户之间的协作。

- 受限权限：此角色非常适合需要监督的用户。 他们只能开始与具有完全权限的用户聊天。 他们可以参与具有完全权限的用户邀请他们参与的任何对话。 在联合聊天案例中，受限用户只能由来自受限用户的租户且具有完全权限的用户添加到聊天中。

若要设置用户的聊天权限角色，请使用 Teams 管理门户中消息策略选项中的 **聊天权限角色** 策略。 可以使用 PowerShell 通过 ChatPermissionRole 策略定义角色，其值为 Full、Limited 或 Restricted。 此策略位于 [CsTeamsMessagingPolicy 下](/powershell/module/skype/set-csteamsmessagingpolicy)。

不能将角色分配给租户中的来宾。 为来宾分配有限角色。

## <a name="allow-supervised-chat"></a>允许监督聊天

默认情况下，租户禁用监督式聊天。 为用户设置聊天权限角色后，可以通过转到 **Teams** \> **Teams 设置** 并将 **基于角色** 的聊天权限策略设置为 **“开**”，在租户中启用监督聊天。 还可以使用 PowerShell 通过将 AllowRoleBasedChatPermissions 设置为 True 来启用监督式聊天。 此 cmdlet 位于 [CsTeamsClientConfiguration 下](/powershell/module/skype/set-csteamsclientconfiguration)。

必须为租户中的所有用户启用监督式聊天，并且不能仅为部分用户启用。

**启用聊天**：

使用 Teams 管理中心中提供的现有聊天策略为所有用户启用聊天。

**维护监督聊天**：

最初启用监督式聊天后，需要执行一些操作以确保环境中的聊天保持受监督：

- 为加入租户的任何新用户分配适当的角色。 默认情况下，将为用户分配受限角色。

- 如果具有完全权限的用户离开租户或从租户中删除，则他们正在监督的聊天将无人参与。 在删除原始用户之前，请确保向这些对话添加另一个具有完全权限的用户，以便聊天可以保持受监督。 删除原始主管后，无法将新参与者添加到对话，但当前参与者可以继续通信。
