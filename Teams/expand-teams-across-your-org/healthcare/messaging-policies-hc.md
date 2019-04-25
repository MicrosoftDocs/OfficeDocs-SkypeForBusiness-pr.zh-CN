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
ms.openlocfilehash: 2de10ef2d36dce991e6f1cd122a624e17ff7a918
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298681"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>适用于医疗保健组织的安全邮件入门

消息策略用于控制哪些聊天和消息功能的通道供 Microsoft 团队中的用户和医院、 培训班或医生办公室，如医疗保健机构安全消息的总体部署一部分其中具有一条消息，选取并及时地采取行动至关重要，如了解何时读取至关重要的邮件。

您可以使用默认策略，或在组织中的人员创建一个或多个自定义的邮件策略。 创建策略后，您将其分配用户组的组织中。 例如，您可以选择仅允许某些作业角色使用这些功能 （也许医生和仅护理） 和其他工作人员 （如保洁或厨房人员） 以获取一组更有限的功能。 决定为您自己组织中具有哪些需求，此处的指南最多为建议。

策略可以轻松管理中[的 Microsoft 团队管理中心](http://admin.teams.microsoft.com)，通过使用管理员凭据日志记录和左侧的导航窗格中选择**消息的策略**。

 ![团队中的邮件策略](../../media/messaging-policies-image1.png)

若要编辑您的组织的现有默认消息策略，请单击**全局 （组织范围内默认值）** 行中，然后进行更改。 若要创建新的自定义邮件策略，单击**新建策略**，然后选择您的设置。 完成后，请选择**保存**。

![医疗保健消息策略设置](../../media/hc-message-policy.png)

医疗保健应用程序感兴趣的设计医疗保健字段中使用的自定义策略时，应考虑以下设置：

## <a name="read-reciepts"></a>读取收货

- ![数字 1](../../media/sfbcallout1.png) **已读回执**已读回执允许发件人知道收件人阅读其消息的时的聊天消息。 使用此设置指定是否读回执是用户控制、 每个人、 启用或禁用每个人。 邮件阅读回执非常重要医疗保健组织中的因为它们确定性删除有关是否已阅读邮件。

  对于医疗保健应用程序，选择**用户控制**或**的所有人都已启用**。 请注意，当使用**的所有人都启用**设置时，回执为整个租户的唯一方式对整个租户 （名为"全局 （组织范围内默认值）"的默认策略） 拥有只有一个邮件策略，或具有所有消息租户中的策略的回执使用相同的设置。

  > [!NOTE]
  > 当读回执一大组中使用聊天 （与 100 多个用户，例如），消息可以淹没实际邮件，并导致聊天用户失望回执。 这是您将需要使用户知晓内容。 较小的群聊 (可能是 20 个用户或更少) 更好地利用此功能。

 *没有已读回执的用法示例：* Jakob Roth，高风险患者，是到医院获准加入会议。索非亚 Krause 是护士一部分医疗工作者，包括不同专家间专业团队 (IDT) 的工作分配作为主护理协调器此患者负责。  索非亚向护理和医生使用各种消息客户端和应用程序的组发送电子邮件和其他即时消息和通常获取未响应或指示是否已阅读工作组成员的邮件。 由于 tangled 的通信流程 Jakob 的用药被误用，并扩展其医院保持。

  *与已读回执的用法示例：* Jakob Roth，高风险患者，是到医院获准加入会议。索非亚 Krause 是护士一部分医疗工作者，包括不同专家间专业团队 (IDT) 的工作分配作为主护理协调器此患者负责。  索非亚从一组医生和其他护理将使用患者来协调护理并启动紧急会审开始群聊。护理和医生通信和协作通过患者的医护计划在整个护理协调过程。  重要和紧急邮件发送通过 1:1 和群聊对话。 索非亚使用已读的回执功能来确定发送的邮件是否请求支持的传递和读取由目标的医生或护理。 Jakob 的患者的产出体现附近最佳，他而转家庭会更快，因为他的医护团队顺利地进行通信。

## <a name="priority-notifications"></a>优先级通知

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

- ![第二](../../media/sfbcallout2.png)**用户可以发送优先级通知**使用此设置允许用户向其他用户发送优先级聊天消息。 此功能可帮助时关键事件需要其注意通知相互医院员工。 与常规"important"消息，不同优先级通知 20 分钟或直到邮件已选取一段反复通知用户，并读取的收件人，最大化邮件是选取并及时处理的可能性。

  管理员可以启用或禁用分配了此策略的用户能够发送优先级通知。 禁用默认设置。 优先级邮件的收件人可能不具有相同的邮件策略，并且将不会选项可以禁用接收优先级的消息。 对于医疗保健应用程序，我们建议启用的功能至少一些用户，但您需要确定要将哪些。

  *用法示例：* 索非亚 Krause readmitting 高风险患者 Jakob Roth。 有关此患者主护理医生 Manuela Carstens，医生。  索非亚发送到 Manuela 邮件标记为高优先级，需要立即帮助会审的 Jakob。  Manuela 的电话中接收的消息，但 Manuela 未感觉电话振动，并且不答复。 团队重新通知 Manuela，并且将继续永久重新通知之前她读取消息。 如果可以识别邮件已通过 Manuela 阅读的读回执也会启用，索非亚，甚至之前 Manuela 决定如何响应。

## <a name="related-topics"></a>相关主题

- [在 Teams 中管理消息传递策略](../../messaging-policies-in-teams.md)
- [适用于医疗保健组织的 Teams 入门](teams-in-hc.md)
