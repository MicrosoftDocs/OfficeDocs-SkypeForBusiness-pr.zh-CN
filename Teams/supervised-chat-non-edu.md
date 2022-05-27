---
title: 对非教育租户使用监督式聊天
author: SerdarSoysal
ms.author: serdars
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
description: 了解Microsoft Teams会议中非教育租户的监督聊天。
ms.openlocfilehash: 4076a2dfa93a037912649bbac88c876c498f1586
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681563"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>非教育租户的监督聊天

监督式聊天允许指定的主管与其组织中的任何人启动聊天，并阻止受限用户启动新聊天，除非存在适当的主管。 启用聊天监督后，不允许主管离开聊天，并且不允许其他参与者删除聊天，确保适当监督涉及受限制用户的聊天。

这些限制仅适用于在完全启用监督聊天后创建的新专用聊天。 它们不适用于现有的私人聊天、会议聊天或频道。

监督聊天是根据教育机构的需求量身定制的，但也适用于非教育租户。

> [!NOTE]
> 监督式聊天可保护在强制实施功能后创建的新聊天。 它不保护现有聊天。

## <a name="enable-supervised-chat"></a>启用监督式聊天

> [!NOTE]
> 在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不必要的受限用户访问不受监督的聊天。

**为环境中的每个用户定义聊天权限角色**：

若要使监督式聊天按预期工作，需要为环境中的每个用户分配正确的聊天权限角色。 用户可以分配三个角色：

- 完全权限：此角色应分配给环境中的聊天主管。 他们可以开始与环境中的任何用户聊天。 具有完全权限的用户应监督他们参与的聊天。 他们不能离开或从聊天中删除，他们开始或聊天，他们正在监督联合租户。

- 受限权限：此角色非常适合仅对受限用户具有受监督访问权限的员工。 他们可以开始与任何完整或受限用户聊天，但不能与受限用户开始聊天。 如果具有完全权限的用户开始与受限用户聊天，则可以将受限用户引入聊天。 之所以进行此访问，是因为存在具有完全权限的用户来监督受限用户与受限用户之间的协作。

- 受限权限：此角色非常适合需要监督的用户。 他们只能与拥有完全权限的用户开始聊天。 他们可以参与拥有完全权限的用户邀请他们参加的任何对话。 在联合聊天情况下，受限用户只能由具有来自受限用户租户的完全权限的用户添加到聊天中。

若要设置用户的聊天权限角色，请使用在Teams管理门户中的消息传送策略选项中找到 **的聊天** 权限角色策略。 可以使用 PowerShell 使用具有“完整”、“有限”或“受限”值的 ChatPermissionRole 策略来定义角色。 此策略位于 [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) 下。

无法将角色分配给租户中的来宾。 为来宾分配受限角色。

## <a name="allow-supervised-chat"></a>允许监督聊天

默认情况下，租户禁用监督聊天。 为用户设置聊天权限角色后，可以通过转到 **组织范围的设置** \> **Teams 设置** 并将 **基于角色的聊天权限** 策略设置为 **“打开”**，在租户中启用监督式聊天。 还可以使用 PowerShell 通过将 AllowRoleBasedChatPermissions 设置为 True 来启用监督聊天。 此 cmdlet 位于 [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration) 下。

必须为租户中的所有用户启用监督聊天，并且不能仅为部分用户启用监督聊天。

**启用聊天**：

使用Teams管理中心提供的现有聊天策略为所有用户启用聊天。

**维护监督式聊天**：

最初启用监督式聊天后，需要执行一些操作，以确保环境中的聊天保持受监督：

- 为加入租户的任何新用户分配适当的角色。 默认情况下，将为用户分配受限角色。

- 如果具有完全权限的用户离开或从租户中删除，则他们监督的聊天将无人参与。 在删除原始用户之前，请确保向这些对话添加具有完全权限的另一个用户，以便聊天可以保持受监督。 删除原始主管后，无法将新参与者添加到对话中，但当前参与者可以继续进行通信。
