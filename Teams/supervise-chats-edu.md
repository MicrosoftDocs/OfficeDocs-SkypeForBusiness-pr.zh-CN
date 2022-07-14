---
title: 使用监督式聊天
author: DaniEASmith
ms.author: danismith
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
description: 了解 Microsoft Teams 会议中监督式聊天。
ms.openlocfilehash: c355730424ec164c2853d4f4dc55956fb7554ce2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789977"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Microsoft Teams 中的监督聊天

教育机构为学生提供安全、健康的数字空间。 数字空间包括 Teams 中的电子邮件、联机会议和呼叫以及消息传递。 为了防止不适当的消息传送行为，许多学校在 Teams 中禁用私人聊天。 不幸的是，禁用聊天也阻碍了教师私下与学生接触以进行个性化学习的机会。 禁用聊天后，学生不愿在课堂团队中公开发布消息时，无法与教师联系。

监督式聊天允许指定的教师发起与学生的聊天，并阻止学生开始新的聊天，除非有合适的教师。 启用聊天监督后，不允许主管离开聊天，不允许其他参与者删除聊天，确保对涉及学生的聊天进行适当监督。

这些限制仅适用于在完全启用监督聊天后创建的新专用聊天。 它们不适用于现有的私人聊天、会议聊天或频道。 若要详细了解会议聊天、频道安全以及确保学生安全的最佳做法，请在 [使用 Teams 时查看“确保学生安全](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)”。

> [!Note]
> 监督式聊天可保护在强制实施功能后创建的新聊天。  它不保护现有聊天。

## <a name="review-use-cases-for-supervised-chats"></a>查看监督式聊天的用例

以下示例介绍了何时需要监督聊天。

- 当学生不愿意分享或公开提问时，请与教师进行 1.1 跟进。

- 教师就作业、最近的课堂交互 (或缺乏) 或其他主题向学生联系 1.1。

- 由教师监视的学生组讨论。

- 允许非教职员工在监督的环境中与学生聊天。

## <a name="enable-supervised-chat"></a>启用监督式聊天

> [!Note]
> 在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不需要的学生访问不受监督的聊天。

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>为环境中的每个用户定义聊天权限角色

若要使监督式聊天按预期工作，需要为环境中的每个用户分配正确的聊天权限角色。 用户可以分配三个角色：

- *完全权限* - 此角色非常适合应具有学生和其他教职员工完全访问权限的教师。 他们可以开始与环境中的任何用户聊天。 具有完全权限的用户应监督他们参与的聊天。 他们不能离开或从聊天中删除，他们开始或聊天，他们正在监督联合租户。

- *有限权限* – 此角色非常适合只对学生具有监督访问权限并完全访问其他教职员工和教师的工作人员。 他们可以开始与任何完整或受限用户聊天，但不能与受限用户开始聊天。 如果具有完全权限的用户开始与受限用户聊天，则可以将受限用户引入聊天。 之所以进行此访问，是因为存在具有完全权限的用户来监督受限用户与受限用户之间的协作。

- *受限权限* - 此角色非常适合需要监督的学生。 他们只能与拥有完全权限的用户开始聊天。 他们可以参与具有完全权限的用户启动的任何对话，然后邀请他们加入。 在联合聊天情况下，受限用户只能由具有来自受限用户租户的完全权限的用户添加到聊天中。

若要设置用户的聊天权限角色，请使用 Teams 管理门户中消息传送策略选项中找到 **的聊天权** 限 **角色** 策略。 可以使用 PowerShell 使用具有“完整”、“有限”或“受限”值的 ChatPermissionRole 策略来定义角色。 此策略位于 CsTeamsMessagingPolicy 下。

了解有关设置的详细信息。 Teams 策略会看到适用于教育的 Teams 策略和策略包，并向大量用户分配策略指南。

无法将角色分配给租户中的来宾。 为来宾分配受限角色。

### <a name="allow-supervised-chat"></a>允许监督聊天

默认情况下，租户禁用监督聊天。 为用户设置聊天权限角色后，可以通过转到 **Teams Teams** &gt; **设置** 并将 **基于角色的聊天权限** 策略设置为 *“打开”*，在租户中启用监督式聊天。 还可以使用 PowerShell 通过将 AllowRoleBasedChatPermissions 设置为 True 来启用监督聊天。 此 cmdlet 位于 CsTeamsClientConfiguration 下。

必须为租户中的所有用户启用监督聊天，并且不能仅为部分用户启用监督聊天。

### <a name="enable-chat"></a>启用聊天

使用 Teams 管理中心中可用的现有聊天策略为所有用户启用聊天。

## <a name="maintain-supervised-chats"></a>维护监督式聊天

最初启用监督式聊天后，需要执行一些操作，以确保环境中的聊天保持受监督：

- 为加入租户的任何新用户分配适当的角色。 默认情况下，将为用户分配受限角色。

- 如果具有完全权限的用户离开或从租户中删除，则他们监督的聊天将无人参与。 在删除原始用户之前，请确保向这些对话添加具有完全权限的另一个用户，以便聊天可以保持受监督。 删除原始主管后，无法将新参与者添加到对话中，但当前参与者可以继续进行通信。

## <a name="related-topics"></a>相关主题

[教育中 Teams 的监督聊天](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
