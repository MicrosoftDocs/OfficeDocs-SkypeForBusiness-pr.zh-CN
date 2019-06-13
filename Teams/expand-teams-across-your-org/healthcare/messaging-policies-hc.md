---
title: 适用于医疗保健组织的安全邮件入门
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 适用于医疗保健组织的安全邮件入门
ms.openlocfilehash: da9bc348a52cf8e4ceacdec36594c81386186c0e
ms.sourcegitcommit: f5b6270e64752298687a1abff49da58acde8e107
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "34912861"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>适用于医疗保健组织的安全邮件入门

邮件策略用于控制 Microsoft 团队中的用户可以使用哪些聊天和频道消息功能, 以及针对医疗保健组织 (如医院、诊所或医生的办事处) 的整体部署的一部分按及时的方式选取和处理邮件非常重要, 因为了解何时阅读重要邮件。

你可以使用默认策略或为组织中的人员创建一个或多个自定义消息策略。 创建策略后, 您将为其分配您的组织中的一个或多个用户组。 例如, 您可以选择仅允许特定工作角色 (如医生和护士) 和其他工作人员 (如医生和护士) 和其他工作人员 (如医生和护士) 和其他工作人员 (如 janitorial 或厨房员工) 获取更有限的一组功能。 确定你的组织需要哪些内容, 此处的指南最多仅有一个建议。

通过使用管理员凭据登录并在左侧导航窗格中选择**消息策略**, 可以轻松地在[Microsoft 团队管理中心](http://admin.teams.microsoft.com)中管理策略。

 ![邮件策略页面的屏幕截图](../../media/messaging-policies-image1.png)

若要编辑你的组织的现有默认消息策略, 请单击 "**全局 (组织范围默认)** " 行, 然后进行更改。 若要创建新的自定义消息策略, 请单击 "**新建策略**", 然后选择您的设置。 完成后选择 "**保存**"。

![邮件策略设置的屏幕截图](../../media/hc-message-policy.png)

以下设置对医疗保健应用程序特别感兴趣, 在设计 "医疗保健" 字段中使用的自定义策略时, 应考虑以下设置:

## <a name="read-receipts"></a>已读回执

- ![数字1的图标, 引用上一个屏幕截图](../../media/sfbcallout1.png)中的标注已读**回执**已读回执允许收到聊天消息的发件人在1:1 和群组聊天20人或更少20人的邮件被收件人阅读。 使用此设置可指定 "已读" 回执是由用户控制、针对所有人还是 "关闭"。 邮件已读回执在医疗保健组织中很重要, 因为他们删除了有关是否已阅读邮件的 uncertainly。

  对于医疗保健应用程序, 请选择 "**由用户控制**" 或 **"针对所有人"**。 请注意, 为整个租户**** 设置收据的唯一方式是仅为整个租户设置一个消息策略 (名为 "Global (组织范围默认)" 的默认策略), 或在所有邮件策略中使用租户对收据使用相同的设置。当**为所有人**启用该功能时, "已读回执" 功能最有效。

    *没有已读回执的用法示例:* Dewei Roth (一种高风险患者) 获准给医院。Sofia Krause 是一位护士, 其中包括不同专业团队的专业团队 (IDT) (包括不同的专业人员), 作为本患者的主要护理协调员分配。  Sofia 将电子邮件和其他即时消息发送给使用各种邮件客户端和应用的护士和医生组, 并且通常不会收到任何答复或指示邮件是否由团队成员阅读。 由于 tangled 的通信流程, Dewei 的药物受到 misapplied, 其医院将持续扩展。

    已*读回执的用法示例:* Dewei Roth (一种高风险患者) 获准给医院。Sofia Krause 是一位护士, 其中包括不同专业团队的专业团队 (IDT) (包括不同的专业人员), 作为本患者的主要护理协调员分配。  Sofia 与一组医生和其他医护人员进行群组聊天, 这些医生和其他医护人员将与患者合作, 以协调护理并启动紧急会审。在整个护理协调流程中, 护士和医生通过患者的护理计划进行沟通和协作。  重要和紧急邮件通过1:1 和群组聊天对话发送。 Sofia 使用 "已读" 回执功能确定已发送请求支持的邮件是否由目标医生或医护人员提供和阅读。 Dewei 的患者成果接近最佳, 他将更快地开始, 因为他的护理团队顺利进行沟通。

## <a name="priority-notifications"></a>优先级通知

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![数字2的图标, 在上一个屏幕截图](../../media/sfbcallout2.png)中引用标注**用户可以发送优先级通知**使用此设置允许用户向其他用户发送优先级聊天消息。 此功能可帮助医院人员在关键事件需要关注时通知另一个人。 与常规的 "重要" 消息不同, 优先级通知重复通知用户一段20分钟的时间, 或直到邮件被接收并阅读邮件, 最大程度地提高邮件的获取和操作操作的可能性。

  管理员可以启用或禁用分配了此策略的用户发送优先级通知的能力。 默认情况下, 此功能处于打开状态。 优先级消息的收件人可能不具有相同的消息传递策略, 并且将不具有用于禁用优先级消息的选项。 对于医疗保健应用程序, 我们建议为至少某些用户启用该功能, 但你需要确定哪些用户。

  *使用示例:* Sofia Krause 是 readmitting 高风险患者, Dewei Roth。 Manuela Carstens (医生) 是此患者的主要护理医生。  Sofia 通过优先级通知向 Manuela 发送一条消息, 询问有关 Dewei 诊断的即时帮助。  Manuela 的手机接收邮件, 但 Manuela 不会感觉电话振动, 也不会回复。 团队会重新通知 Manuela, 并将继续持续重新通知, 直到她阅读邮件。 如果已启用 "已读" 回执, Sofia 可以知道邮件已被 Manuela 读取, 即使在 Manuela 决定如何响应之前也是如此。

## <a name="related-topics"></a>相关主题

- [在 Teams 中管理消息传递策略](../../messaging-policies-in-teams.md)
- [适用于医疗保健组织的 Teams 入门](teams-in-hc.md)
