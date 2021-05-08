---
title: 使用监督聊天
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 了解会议中监督Microsoft Teams聊天。
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506675"
---
# <a name="supervised-chats-in-microsoft-teams"></a>在对话中监督Microsoft Teams

教育机构为学生提供安全、健康的数字空间。 数字空间包括电子邮件、联机会议和呼叫，以及电子邮件Teams。 为了防止不适当的消息传送行为，许多学校禁止在Teams。 遗憾的是，禁用聊天也会阻止教师私下联系学生进行个性化学习。 禁用聊天后，学生不希望在课堂团队中公开发布消息时，无法与教师联系。

监督式聊天允许指定的教师发起与学生的聊天，并阻止学生开始新聊天，除非有合适的教师。 启用聊天监督后，主管不允许离开聊天，不允许其他参与者删除聊天，从而确保涉及学生的聊天受到适当的监督。

这些限制仅适用于在完全启用监督聊天后创建的新私人聊天。 它们不适用于现有私人聊天、会议聊天或频道。 若要详细了解会议聊天、频道安全和确保学生安全的最佳做法，请观看使用视频时确保学生[Teams。](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> 监督聊天保护在强制实施该功能后创建的新聊天。  它不会保护现有聊天。

## <a name="review-use-cases-for-supervised-chats"></a>查看监督聊天的用例

以下示例介绍何时需要监督聊天。

- 当学生不喜欢共享或公开提问时，与教师进行 1.1 跟进。

- 教师通过 1.1 向学生介绍作业、最近的课堂 (或缺少) 或其他主题。

- 教师监视的学生组讨论。

- 允许非教职员工在受监督的环境中与学生聊天。

## <a name="enable-supervised-chat"></a>启用监督聊天

> [!Note]
> 在为机构启用聊天之前，请确保设置聊天权限角色和基于角色的聊天权限策略，以避免不需要的学生访问不受监督的聊天。

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>为环境中每个用户定义聊天权限角色

要正常使用监督聊天，需要为环境中每个用户分配正确的聊天权限角色。 用户可以分配三个角色：

- *完全权限* - 此角色非常适合应具有学生和其他教职员工成员的完全访问权限的教师。 他们可以开始与环境中的任何用户聊天。 具有完全权限的用户应监督他们参与的聊天。 他们不能离开或从他们启动的聊天或他们在联合租户中监督的聊天中删除。

- *受限权限* - 此角色非常适合仅对学生拥有监督访问权限且对其他教职员工和教师具有完全访问权限的员工。 他们可以开始与任何完整或受限用户聊天，但不能开始与受限用户聊天。 如果具有完全权限的用户开始与受限用户聊天，可以将受限用户带到对话中。 发生此访问的原因是具有完全权限的用户可以监督受限和受限用户之间的协作。

- *受限权限* - 此角色非常适合需要监督的学生。 他们只能与具有完全权限的用户开始聊天。 他们可以参与具有完全权限的用户邀请他们参与的任何对话。 在联合聊天案例中，只有具有完全权限的用户（来自受限用户的租户）才能将受限用户添加到聊天中。

若要设置用户的聊天权限角色，请使用管理员门户中消息策略选项内找到的聊天权限Teams策略。 可以使用 PowerShell 通过 ChatPermissionRole 策略定义角色，其值为 Full、Limited 或 Restricted。 此策略位于 CsTeamsMessagingPolicy 下。

详细了解设置。 Teams策略，Teams适用于教育的策略和策略包和向大量用户分配策略指南。

无法将角色分配给租户中的来宾。 为来宾分配受限角色。

### <a name="allow-supervised-chat"></a>允许监督聊天

默认情况下，你的租户禁用了监督聊天。 为用户设置聊天权限角色后，可以通过访问组织范围的设置 Teams 设置 将基于角色的聊天权限策略设置为"开 &gt; **"，** 在租户中启用监督式 *聊天。* 还可将 AllowRoleBasedChatPermissions 设置为 True，使用 PowerShell 启用监督式聊天。 此 cmdlet 位于 CsTeamsClientConfiguration 下。

必须为租户中的所有用户启用监督聊天，并且不能仅为部分用户启用。

### <a name="enable-chat"></a>启用聊天

使用管理中心内提供的现有聊天策略为所有用户Teams聊天。

## <a name="maintain-supervised-chats"></a>维护监督聊天

最初启用监督聊天后，需要执行一些操作以确保环境中聊天保持监督状态：

- 向加入租户的任何新用户分配相应的角色。 默认情况下，将为用户分配受限角色。

- 如果拥有完全权限的用户离开或从租户中删除，他们监督的聊天将无人参与。 删除原始用户之前，请确保向这些对话添加具有完全权限的另一个用户，以便聊天可以保持监督状态。 删除原始监督者后，无法将新参与者添加到对话中，但当前参与者可以继续通信。

## <a name="related-topics"></a>相关主题

[在教育中Teams监督聊天](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
