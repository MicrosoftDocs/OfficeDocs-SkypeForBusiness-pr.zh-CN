---
title: 进行用户试点以评估和测试Microsoft Teams在组织中的工作原理
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 在继续使用Skype for Business时，有关启动Microsoft Teams试点以探索Teams为组织提供的所有功能的指南
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823221"
---
# <a name="conduct-a-user-pilot"></a>执行用户试点

![升级旅程图，突出显示部署和实现。](media/upgrade-banner-deployment.png "升级过程的阶段，重点是部署和实施阶段")

本文是升级过程的部署和实施阶段的一部分，并分享有关运行有效试点的见解。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解Skype for Business和Teams的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备好环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)

通过部署新技术，你的组织可以实现业务价值，如成本节约、安全合规性、员工满意度和运营效率，但也可能影响用户的工作效率和组织基础结构 (网络) 。 在组织中启用新技术之前，请进行正式的用户试点。 就像在绘制整个房间之前在墙上画一小块颜色一样，通过进行试点来验证技术和用户的就绪情况，识别和缓解问题，并帮助确保组织范围内的成功实施，可以更小地测试广泛推出。

为了实现最现实的结果，试点应涉及实际用户，模拟他们沟通和协作方式，并验证技术和用户体验。 无论是组织考虑运行Skype for Business并排Teams，将来升级到Teams，还是部署调用或会议等新功能，试点都可以帮助确定组织前进的正确路径。 有时被视为推出的第 1 阶段，理想的试点利用你已启动的准备，并与目标用户组一起实现定义的计划。

|&nbsp; | &nbsp;|
|---|---|
| ![描述决策点的图标。](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>如何使用试点通知项目方向？</li></ul> |
| ![描述下一步的图标。](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>使用以下指南设计和执行正式试点。</li></ul>|

> [!Tip]
> 使用示例 [试点资源](https://aka.ms/UpgradeSuccessKit) 来帮助设计通信、测试计划和反馈调查。

## <a name="1-outline-pilot-logistics"></a>1. 试点物流大纲

成功的试点定义了开始日期和结束日期，并 [明确定义了](upgrade-define-project-scope.md#project-goals) 衡量成功的目标。 这些目标应与更广泛的项目范围保持一致，如定义 [项目范围](upgrade-define-project-scope.md)时所述，并将用于在试点结束后通知前进的道路。 还应确保在项目持续时间内包含正确的利益干系人。 你将希望确保有足够的时间运行试点并评估其影响：建议至少 30 天。

"开始"菜单小，并根据需要添加到试点（无论是通过添加工作负荷或功能，还是通过其他用户），以便在迭代时有时间评估结果和调整试点。 甚至可以选择运行后续试点，因为根据路线图发布了新的Teams功能。

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2.选择试点参与者和测试方案

试点计划最重要的任务之一是仔细选择参与者。 请记住，Teams针对团队合作进行了优化，因此请务必选择试点参与者，不仅基于角色或角色，还基于他们的项目和跨团队工作。 一个很好的起点是向利益干系人和部门经理询问可在Teams中验证的实际项目。 基于角色项目的一个示例可能是将Teams用于销售组织，以确保字段代表可以轻松访问所需的资源，并与其他字段成员共享见解。 基于项目的一个工作示例可能是与营销、培训、公共关系和事件规划团队协调产品启动活动。 无论选择哪种方案，试点都应扩展到 IT、培训和帮助人员中的关键人员，以便在完全优化项目管理资源的同时彻底验证解决方案。

> [!Tip]
> 选择Teams试点组参与者时，请务必包括Skype for Business的热门用户。 请与这些用户联系，了解他们目前如何使用Skype for Business，然后构建测试计划，验证Teams是否可以满足其当前需求。

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3.设计测试计划和反馈调查

为了获得成功的试点体验，请为参与者提供明确定义的任务，并让他们分享反馈。 将任务分组在一起，为用户提供真实场景，从而显示与日常活动的相关性。 让在 [评估组织更改就绪情况](./upgrade-org-change-readiness.md) 中定义的用例指导测试计划。

你的组织可能会选择一次性试用所有功能，或者使用逐步方法（例如，先试点协作，然后是会议，然后聊天和通话）。 确保你有一个开放的反馈渠道来跟踪进度和衡量结果。 使用预定义的调查作为捕获和评估试点结果的简便方法;调查设计应基于测试计划中的方案和功能。

## <a name="4-create-your-communications-plan"></a>4. 创建通信计划

对飞行员的成功至关重要，你让飞行员参与者了解所发生的情况、时间、原因以及对他们的预期。 若要推动兴奋和最大程度的参与，除了培训和支持的链接外，请务必包括用户价值消息传送，用户可以在试点过程中获取其他信息。 下面是一些示例资源，可让你开始使用试点通信计划：

- [试点资源](https://aka.ms/UpgradeSuccessKit)，包括电子邮件模板和示例反馈调查问题
- [从Skype for Business切换到Teams](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)，这是一个快速入门指南，旨在帮助Skype for Business用户开始使用Teams

## <a name="5-conduct-your-pilot"></a>5. 进行试点

随着所有物流的到位，你现在已准备好开始你的试点。 进行试点包括与用户沟通、监视网络和使用情况，以确保网络性能和呼叫质量保持正常，收集参与者的反馈，以及查看与Teams相关问题的支持人员票证。

### <a name="tips-for-pilot-success"></a>试点成功的使用技巧

以下提示可帮助确保试点成功：

- 在开始试点之前，请确认所有试点参与者都已启用适当的 [共存模式]
- 要验证 (https://aka.ms/SkypeToTeams-SetCoexistence) 。
- 在试点期间，每周都会与项目利益干系人会面，查看用户反馈、使用情况数据、网络数据和支持人员票证，以确保试点顺利运行。 根据需要进行任何调整。

### <a name="suggested-timeline"></a>建议的时间线

下面是 30 天试点的建议时间线：

- 试点启动前一周：向试点用户发送初始通信。
- 第 1 天：向试点用户发送启动通信。
- 第 7 天：举行第一次每周项目团队检查点会议。
- 第 14 天：向试点用户发送中点通信，每周举行项目团队检查点会议。
- 第 21 天：每周举行项目团队检查点会议。
- 第 30 天：向试点用户发送最终通信。
- 第 31-45 天：评估试点结果，并规划后续步骤。

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. 评估学习并评估你的前进计划

试点完成后，可以收集所有反馈调查、最终网络统计信息和支持针对目标进行分析的票证，并确定是否实施你的前进计划。 你可能会发现，你的组织已准备好进行广泛的部署，或者你希望将试点扩展到更多用户，或者希望在你确定的任何问题得到缓解后，在以后重新访问试点。 请记住，试点是预测 _受控_ 环境中技术和用户结果的好方法：考虑跳得太快。

如果结果显示：

- **试点目标 (例如，用户满意度和网络质量) 已实现**，应该可以继续下一阶段的推出。 根据项目的目标，这可能是下列操作之一：
  - 将试点扩展到其他参与者
  - [为组织中的某些或全部) 启用Skype for Business (**岛** 模式Teams](./setting-your-coexistence-and-upgrade-settings.md)
  - [将用户从Skype for Business升级到仅 **Teams (Teams** 模式) 某些组织或所有组织](./setting-your-coexistence-and-upgrade-settings.md)
- **试点未达到你希望的结果 (例如，用户满意度和网络质量)**，请花时间对计划进行适当的调整，然后重新访问试点。

> [!Tip]
> 将试点参与者登记为对等冠军，以帮助传福音和加入新用户以Teams。 对等冠军可以轻松地与其他用户相关联，分享他们自己的体验和学习，并向同事提供支持和指导。 详细了解 [冠军](
https://adoption.microsoft.com/become-a-champion/) 以及如何在自己的推出中使用它们。