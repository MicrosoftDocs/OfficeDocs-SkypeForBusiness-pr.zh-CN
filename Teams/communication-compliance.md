---
title: 与 Microsoft 团队的通信合规性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 了解有关通信合规性的知识合规性风险解决方案集的一部分，从 Microsoft 团队角度 (这是 M365 通信合规性功能的一部分) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597131"
---
# <a name="communication-compliance-with-microsoft-teams"></a>与 Microsoft 团队的通信合规性

通信合规性是 Microsoft 365 中的内幕风险解决方案，可帮助你检测、捕获和处理组织中不适当的邮件，从而帮助最大程度地减少通信风险。

对于 Microsoft 团队，通信合规性有助于标识团队频道或1:1 和群组聊天中的[以下类型](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference)的不当内容：

- 冒犯性、亵渎和 harassing 语言
- 成人、racy 和 gory 图像
- 敏感信息的共享

>[!IMPORTANT]
>通信合规性不支持专用 Microsoft 团队频道。 由来宾用户发送给不会对不适当内容进行监视的团队用户发送的聊天通信。

有关通信合规性以及如何为你的组织配置策略的详细信息，请参阅[Microsoft 365 中的通信合规性](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>如何在 Microsoft 团队中使用通信合规性

通信合规性和 Microsoft 团队紧密集成，有助于最大程度地减少组织中的通信风险。 配置您的第一个通信合规性策略后，您可以主动管理不合适的 Microsoft 团队邮件和自动标记为通知的内容。

### <a name="getting-started"></a>入门

Microsoft 团队中的通信合规性入门首先[计划](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan)和创建预定义或自定义策略，以在团队频道或1:1 和组中标识不适当的用户活动。 请记住，在配置过程中，你将需要[配置](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure)某些权限和基本先决条件。

团队管理员可以在以下级别配置通信合规性策略：

- **用户级别**：此级别的策略适用于单个团队用户或应用于你组织中的所有团队用户。 这些策略涵盖了这些用户可以在1:1 或群组聊天中发送的消息。 用户的聊天通信将在用户所属的所有 Microsoft 团队中自动监视。
- **团队级别**：此级别的策略适用于 Microsoft 团队频道。 这些策略涵盖仅在团队频道中发送的消息。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>对 Microsoft 团队中不恰当的邮件执行操作

配置策略并收到 Microsoft 团队邮件的通信合规性警报后，您的组织中的合规性审阅者可以对这些消息执行操作。 审阅者可以通过查看通信合规性警报和从 Microsoft 团队中删除已标记的邮件来帮助保护您的组织。

![删除团队中的邮件](./media/communication-compliance-remove-teams-message.png)

删除的邮件和内容被替换为查看者通知，说明邮件或内容已删除，以及哪些策略适用于删除。 已删除的消息的发件人也会收到删除状态的通知，并附带原始邮件内容与删除相关的上下文。 发件人还可以查看适用于邮件删除的特定策略条件。

由发件人查看的策略提示的示例：

![发件人的策略提示](./media/communication-compliance-warning-1.png)

发件人看到的策略条件通知的示例：

![发件人的策略条件信息](./media/communication-compliance-warning-2.png)

收件人显示的策略提示的示例：

![收件人的策略提示](./media/communication-compliance-warning-3.png)