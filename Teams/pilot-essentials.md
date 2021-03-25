---
title: 开展用户试点，评估和测试 Microsoft Teams 在你的组织中如何工作
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 有关启动 Microsoft Teams 试点的指南，探索 Teams 为组织提供的所有功能，同时继续使用 Skype for Business
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e2d909722674f23e253d0ae937efddb14d96d7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108368"
---
# <a name="conduct-a-user-pilot"></a>执行用户试点

![升级过程图，突出显示"部署和实现"](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文是升级旅程的部署和实施阶段的一部分，分享有关运行有效试点的见解。 在继续之前，请确认已经完成了以下活动:

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解 Skype for Business 和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [准备环境](./upgrade-prepare-environment.md)
- [准备组织](./upgrade-prepare-organization.md)

通过部署新技术，组织可以实现成本节省、安全合规性、员工满意度和操作效率等业务价值，但也可能影响用户的工作效率和组织基础结构 (网络) 。 在整个组织中启用新技术之前，请进行正式用户试点。 就像在绘制整个房间之前在墙壁上画一小片颜色一样，通过开展试点来验证技术和用户就绪性、识别和缓解问题，并帮助确保组织范围内的实施成功，从而在小规模上测试广泛推出。

要实现最现实的结果，试点应涉及实际用户，模拟他们沟通和协作的方式，并验证技术和用户体验。 无论你的组织考虑并行运行 Skype for Business 和 Teams、将来升级到 Teams，还是部署呼叫或会议等新功能，试点都可以帮助确定适合你的组织的前进方向。 有时被视为实施的第 1 阶段，理想的试点利用已启动的准备工作，通过目标用户组实施定义的计划。

| | |
|---|---|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>如何使用试点来告知项目方向？</li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>使用以下指南设计和执行正式试点。</li></ul>|

> [!Tip]
> 使用示例 [试点资源](https://aka.ms/UpgradeSuccessKit) 来帮助设计通信、测试计划和反馈调查。

## <a name="1-outline-pilot-logistics"></a>1. 概述试点物流

成功的试点已定义开始日期和结束日期，以及 [用于衡量成功的](upgrade-define-project-scope.md#project-goals) 明确目标。 这些目标应该与更广泛的项目范围保持一致，如定义项目范围时所记录，[](upgrade-define-project-scope.md)并且将用于在试点结束后通知你前进的路径。 此外，应确保在项目持续期间包含适当的利益干系人。 你需要确保留出足够的时间来运行试点并评估其影响：我们建议至少 30 天。

从小规模开始，并根据需要向试点添加内容（无论是通过添加工作负荷或功能，还是通过添加其他用户）来花时间评估结果，并调整试运行方式。 根据路线图发布新的 Teams 功能时，甚至可以选择运行后续试运行。

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. 选择试点参与者和测试方案

试点计划最重要的任务之一是仔细选择参与者。 请记住，Teams 针对团队合作进行了优化，因此，请确保不仅基于角色或角色，还基于其项目和跨团队工作选择试点参与者。 一个很好的起点是要求利益干系人和部门经理提供可在 Teams 中验证的实际项目。 基于角色的项目的一个示例可能是将 Teams 与销售组织一起使用，以确保现场代表可以轻松访问所需的资源，并与其他现场成员共享见解。 基于项目的工作的一个示例可能是将产品发布活动与营销、培训、公共关系和事件规划团队协调。 无论选择哪种方案，试点都应扩展到 IT、培训和支持人员中的关键人员，以便你可以全面验证解决方案，同时完全优化项目管理资源。

> [!Tip]
> 选择 Teams 试点组参与者时，请务必包括 Skype for Business 的顶级用户。 请与这些用户核实以了解他们当前如何使用 Skype for Business，然后制定测试计划来验证 Teams 是否能够满足其当前需求。

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. 设计测试计划和反馈调查

若要获得成功的试点体验，请为参与者提供明确定义的任务来完成，并帮助他们分享反馈。 将任务组合在一起，为用户提供实际方案，表明其日常活动的相关性。 让在评估组织变更准备 [情况指南中定义的](./upgrade-org-change-readiness.md) 用例用于测试计划。

组织可能选择一次试用所有功能，或者使用渐进式方法-例如，先试运行协作，然后进行会议，然后聊天和通话。 确保你有一个开放的反馈渠道来跟踪进度和衡量结果。 使用预定义的调查作为捕获和评估试点结果的简便方法;调查设计应基于测试计划中的方案和功能。

## <a name="4-create-your-communications-plan"></a>4. 创建通信计划

让试点参与者了解情况、时间、原因以及预期结果，对试点的成功至关重要。 若要促进兴奋和最大程度的参与，除了培训和支持的链接外，请确保包括用户价值消息，用户可以在试点进行时获取其他信息。 下面是一些示例资源，可让你开始使用试点通信计划：

- [试点资源](https://aka.ms/UpgradeSuccessKit)，包括电子邮件模板和示例反馈调查问题
- [从 Skype for Business 切换到 Teams，](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)这是一个快速入门指南，旨在帮助 Skype for Business 用户开始使用 Teams

## <a name="5-conduct-your-pilot"></a>5. 开展试点

准备好所有物流后，即可开始试点。 试点包括与用户通信、监视网络和使用情况以确保网络性能和呼叫质量保持正常、从参与者收集反馈，以及查看与 Teams 相关的问题的支持票证。

### <a name="tips-for-pilot-success"></a>试点成功的提示

以下提示有助于确保试点成功：

- 在开始试验之前，请确认所有试点参与者都启用了适当的 [共存模式]
-  (https://aka.ms/SkypeToTeams-SetCoexistence) 要验证的证书。
- 每周在试点期间与项目利益干系人会面，查看用户反馈、使用情况数据、网络数据和支持票证，确保试点顺利运行。 根据需要做出任何调整。

### <a name="suggested-timeline"></a>建议的日程表

下面是 30 天试点的建议时间线：

- 试点启动前的一周：向试点用户发送初始通信。
- 第 1 天：向试点用户发送启动通信。
- 第 7 天：召开第一次每周项目团队检查点会议。
- 第 14 天：向试点用户发送中间点通信，召开每周项目团队检查点会议。
- 第 21 天：召开每周项目团队检查点会议。
- 第 30 天：向试点用户发送最终通信。
- 第 31-45 天：评估试点结果，并规划下一步。

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. 评估学习和评估前进计划

试点完成后，可以收集所有反馈调查、最终网络统计信息和支持票证，以便针对目标进行分析，并确定是否实施前向计划。 你可能会发现，你的组织已准备好进行广泛部署，或者希望将试点扩展到更多用户，或者想要在发现的任何问题得到缓解后，在以后重新访问试点。 请记住，试点是在受控环境中预测技术和用户结果 _的一种好_ 方法;考虑过快地跳转。

如果结果指示：

- **试点目标 (** 例如，用户满意度和网络质量) 已实现，应准备好继续进行下一阶段的推出。 根据项目的目标，这可能是下列其中一项：
  - 将试点扩展到其他参与者
  - [为部分或所有组织 (Teams for Business ) 和 Skype for Business 模式](./setting-your-coexistence-and-upgrade-settings.md)
  - [将用户从 Skype for Business (**Teams**) 部分或所有组织使用 Teams 模式](./setting-your-coexistence-and-upgrade-settings.md)
- **试运行未达到** 预期效果，例如 (满意度和网络质量) ，请花些时间对计划进行适当的调整，然后重新访问试点。

> [!Tip]
> 将试点参与者登记为对等支持者，以帮助向 Teams 宣传新用户并加入 Teams。 对等支持者可以轻松地与其他用户关联、分享其自己的体验和知识，以及向同事提供支持和指导。 详细了解冠军 [以及如何](https://go.microsoft.com/fwlink/?linkid=859068) 在你自己的推出中使用它们。