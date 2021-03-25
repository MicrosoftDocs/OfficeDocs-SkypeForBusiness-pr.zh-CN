---
title: 与 Microsoft Teams 的通信符合性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 从 Microsoft Teams 的角度了解通信符合性（内部风险解决方案集的一部分） (这是 M365 通信合规性功能) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121530"
---
# <a name="communication-compliance-with-microsoft-teams"></a>与 Microsoft Teams 的通信符合性

通信合规性是 Microsoft 365 中的一个预览体验成员风险解决方案，可帮助检测、捕获和操作组织中不适宜的邮件，帮助最大程度地降低通信风险。

对于 Microsoft Teams，通信符合性有助于在[](/microsoft-365/compliance/communication-compliance-feature-reference)Teams 频道或 1：1 和群组聊天中识别以下不适宜的内容类型：

- 冒犯性、亵渎和攻击性语言
- 成人、不性与成人图像
- 共享敏感信息

有关通信符合性以及如何为组织配置策略的信息，请参阅 [Microsoft 365](/microsoft-365/compliance/communication-compliance)中的通信符合性。

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>如何在 Microsoft Teams 中使用通信符合性

通信合规性与 Microsoft Teams 紧密集成，有助于最大程度地降低组织的通信风险。 配置第一个通信符合性策略后，可以主动管理在警报中自动标记的不适宜的 Microsoft Teams 消息和内容。

### <a name="getting-started"></a>入门

Microsoft Teams 中的通信符合性入门首先规划和创建[](/microsoft-365/compliance/communication-compliance-plan)预定义或自定义策略，以识别 Teams 频道或 1：1 和组中不适宜的用户活动。 请记住，需要在配置过程中配置一些权限[](/microsoft-365/compliance/communication-compliance-configure)和基本先决条件。

Teams 管理员可以在下列级别配置通信符合性策略：

- **用户级别**：此级别的策略适用于单个 Teams 用户，也可以应用于组织的所有 Teams 用户。 这些策略涵盖这些用户可以在 1：1 或群组聊天中发送的消息。 用户的聊天通信会在用户作为成员的所有 Microsoft Teams 中自动受到监视。
- **团队级别**：此级别的策略适用于 Microsoft 团队频道。 这些策略仅涵盖在 Teams 频道中发送的消息。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>在 Microsoft Teams 中处理不当消息

配置策略并收到 Microsoft Teams 消息的通信符合性警报后，组织中的合规性评审者可以针对这些消息采取措施。 审阅者可以通过在 Microsoft Teams 中查看通信合规性警报和从视图中删除已标记的邮件来帮助保护组织。

![在 Teams 中删除消息](./media/communication-compliance-remove-teams-message.png)

已删除的消息和内容将被替换为通知，供查看者说明邮件或内容已删除以及适用于删除的策略。 已删除邮件或内容的发送者也会收到删除状态通知，并针对与删除相关的上下文提供原始邮件内容。 发送方还可以查看应用于邮件删除的特定策略条件。

发送方看到的策略提示示例：

![发件人的策略提示](./media/communication-compliance-warning-1.png)

发件人看到的策略条件通知示例：

![发件人的策略条件信息](./media/communication-compliance-warning-2.png)

收件人看到的策略提示示例：

![收件人的策略提示](./media/communication-compliance-warning-3.png)