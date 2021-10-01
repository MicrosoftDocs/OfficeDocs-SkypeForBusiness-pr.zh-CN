---
title: 使用 Microsoft Teams 的医疗保健组织的安全消息传递
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 了解如何为 Microsoft Teams 自定义安全消息传递策略，其中可包括已读回执和优先级通知。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ededfabcca1ab61ec822f201502658f4d8ac498a
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045514"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>医疗保健组织的安全消息传递

消息传递策略用于控制 Microsoft Teams 中的用户可以使用哪些聊天和频道消息传递功能，并且它们是医疗保健组织（如医院、门诊部或医生诊所）的安全消息传递整体部署的一部分，其中，及时阅读和处理消息至关重要，同时了解关键消息何时得到阅读也是如此。

你可以使用全局（组织范围的默认设置）策略，也可以为组织中的人员创建一个或多个自定义消息传递策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。 在创建自定义策略后，可为其分配组织中的一个或多个用户。 例如，你可以选择只允许某些工作角色使用这些功能（也许仅是医生和护士），而其他工作人员（如门卫或厨房工作人员）只能使用较为有限的一组功能。 你可自行决定组织需要满足的需求，此处的指导最多只是建议。

通过使用管理员凭据登录并在左侧导航窗格中选择“**消息传递策略**”，可以在 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)中轻松管理策略。

 :::image type="content" source="../../media/hc-messaging-policy-admin-center-new.png" alt-text=""消息策略"页的屏幕截图。" lightbox="../../media/hc-messaging-policy-admin-center-new.png":::
 
 若要为组织编辑现有默认消息传递策略，请单击“**全局（组织范围的默认设置）**”，然后进行更改。 若要创建新的自定义消息传递策略，请单击“**添加**”，然后选择你的设置。 完成后，选择“**保存**”。

![消息策略设置的屏幕截图。](../../media/hc-messaging-policy.png)

以下设置对于医疗保健应用程序特别有意义，在设计医疗保健领域使用的自定义策略时应考虑这些设置：

## <a name="read-receipts"></a>已读回执

通过已读回执，聊天消息的发件人可以知道收件人（一对一聊天和人员不超过 20 的群聊）何时阅读了其消息。 使用此设置可指定已读回执是由用户控制、对所有人打开还是对所有人关闭。 消息已读回执在医疗保健组织中非常重要，因为有了它们就不必再怀疑消息是否已被阅读。

对于医疗保健应用程序，请选择“**用户控制**”或“**面向所有人打开**”。 请注意，在使用“**面向所有人打开**”设置时，为整个租户设置回执的唯一方法是为整个租户仅设置一个消息传递策略（名为“全局（组织范围的默认设置）”的默认策略），或使租户中的所有消息传递策略都使用相同的回执设置。 当已读回执功能启用为“**面向所有人打开**”时，该功能最有效。

*没有已读回执的使用示例：* 高危患者 Jakob Roth 被送进医院。  Sofia Krause 是一名护士，隶属医务工作者专业间团队 (IDT)（包括不同专家），她被指派为接洽此患者的初级护理协调员。  Sofia 向使用各种消息传递客户端和应用的一组护士和医生发送了电子邮件和其他即时消息，并且通常没有任何响应或指示表明消息是否已被团队成员阅读。 由于沟通过程混乱，Jakob 的药物使用不当，住院时间延长了。

*有已读回执的使用示例：* 高危患者 Jakob Roth 被送进医院。  Sofia Krause 是一名护士，隶属医务工作者专业间团队 (IDT)（包括不同专家），她被指派为接洽此患者的初级护理协调员。  Sofia 开始与一组医生和其他护士进行群聊，这些医生和护士将与患者合作协调护理并开始急诊分诊。  在整个护理协调过程中，护士和医生们将就患者的护理计划进行沟通和协作。  重要和紧急消息将通过一对一和群聊对话发送。 Sofia 使用已读回执功能来确定为请求支援而发送的消息是否已传送并被目标医师或护士阅读。 Jakob 的患者治疗效果几乎最佳，由于他的医疗团队沟通顺畅，他很快出院了。

## <a name="send-urgent-messages-using-priority-notifications"></a>使用优先级通知发送紧急消息

在向其他用户发送聊天消息时，用户可以将消息标记为“*紧急*”。 此功能可帮助医院工作人员在有重要事件需要他们关注时互相提醒。 与常规 *重要* 消息不同，[优先级通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)每两分钟通知用户一次，持续长达 20 分钟，直到收件人接收并阅读该消息为止，从而最大程度提高了及时处理消息的可能性。

管理员可以为分配了此策略的用户启用或禁用发送优先级通知的功能。 默认情况下，启用此功能。 优先级消息的收件人可能没有相同的消息传递策略，并且没有禁用接收优先级消息的选项。 对于医疗保健应用程序，我们建议至少为某些用户启用该功能，但是你需要确定具体用户。

*使用示例：* Sofia Krause 再次负责接洽高危患者 Jakob Roth 入院。 医生 Manuela Carstens 是该患者的初级保健医生。  Sofia 使用优先级通知向 Manuela 发送了一条消息，要求立即对 Jakob 进行分诊。  Manuela 的电话收到了该消息，但 Manuela 并未感觉到电话振动，因此没有回复。 Teams 将重新通知 Manuela，并且会持续不断地重新通知，直到她阅读了该消息。 如果还启用了已读回执，则即使在 Manuela 决定如何响应之前，Sofia 就会知道 Manuela 已阅读该消息。

## <a name="related-topics"></a>相关主题

- [在 Teams 中管理消息传递策略](../../messaging-policies-in-teams.md)
- [适用于医疗保健组织的 Teams 入门](teams-in-hc.md)
