---
title: Microsoft 团队的通信合规性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 了解有关通信合规性的信息，即 "预览体验成员" 解决方案集的一部分，从 Microsoft 团队的角度来看，这是 M365 通信合规性功能的一部分。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121692"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Microsoft 团队的通信合规性

通信合规性是 Microsoft 365 中新的预览体验计划解决方案集的一部分，可帮助你对组织中的不当邮件检测、捕获和采取补救措施，从而减少通信风险。 它有助于识别团队频道或1:1 和群组聊天中的攻击性语言和反骚扰。 您还可以设置策略以查看是否有任何敏感信息被共享为团队频道或1:1 和群组聊天的一部分。 有关不同类型的策略以及如何设置[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)的详细信息，请参阅 ""。

## <a name="how-to-use-communication-compliance-in-teams"></a>如何使用团队中的通信合规性

### <a name="identify-inappropriate-messages"></a>标识不适当的邮件

如果要标识在 Microsoft 团队中发送的任何消息（1:1、群组聊天或频道对话）包含冒犯性的语言或反骚扰，则可以启用策略来标识此邮件，并且审阅者可以查看邮件并执行必要的步骤，如发送培训资料或升级到适当的机构。

### <a name="identify-sensitive-or-regulatory-information"></a>标识敏感或法规信息

如果要扫描 Microsoft 团队中发送的邮件（1:1、群组聊天或频道对话）以了解敏感信息或法规类型，可以选择支持预定义的敏感或法规类型的策略。

> [!NOTE]
> 通信合规性不支持专用通道。

### <a name="custom-policy"></a>自定义策略

使用此模板配置特定通信通道、单个检测条件以及你的组织中要监视和查看的内容量。

### <a name="custom-trainable-classifier"></a>自定义 Trainable 分类器

当一个框中的某个分类器不能满足您的需要时，请使用 trainable 分类器。 Microsoft 365 分类器是一种工具，可通过提供示例来训练以识别各种类型的内容。 培训分类器首先需要为其提供人工挑选的示例，并正确匹配该类别。 然后，在处理这些示例之后，你可以通过给它混合使用正和负样本来测试预测。 有关详细信息，请参阅[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier)了解有关本主题的详细信息。

> [!NOTE]
> 通信合规性现在支持 Exchange 混合部署。

通信合规性支持与策略匹配的任何消息的对话历史记录。 这提供了调查管理员的上下文。

:::image type="content" source="media/communication-compliance-1.png" alt-text="用于在 Microsoft 团队中进行通信合规性的屏幕。":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>可在团队中应用通信策略的位置

可以为在以下级别的团队中发送的邮件设置通信合规性策略：

- 用户级别：管理员可以在单个用户级别设置策略，或将策略应用到租户上的所有用户。 这仅涵盖用户在1:1 或群组聊天中发送的消息。
- 团队级别：管理员还可以设置团队的策略。 这将涵盖该团队频道中发送的所有消息（不支持专用信道消息）。
