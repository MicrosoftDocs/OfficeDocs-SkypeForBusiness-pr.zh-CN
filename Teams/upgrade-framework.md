---
title: 关于升级框架 - Skype for Business Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用经过验证的成功框架来帮助组织从Skype for Business升级到Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cfc8a3855da45b80ac5cd97d273b9f6c1d90ded
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681963"
---
# <a name="about-the-upgrade-framework"></a>关于升级框架

为了帮助你完成升级过程的猜测，我们采用了一个经过验证的框架来实现更改。 如下所示，框架中的每个步骤都基于前面的步骤，为了获得最佳结果，我们建议按顺序执行步骤。  

首先，将正确的利益干系人聚集在一起， (定义升级计划，例如范围、目标和时间线) 。 制定计划后，请确认技术环境和最终用户已准备好进行Teams。 然后，分阶段实现升级，在准备就绪时从试点升级到组织范围的升级。 组织Teams后，建立一个操作计划，用于监视质量并加快用户采用速度。

![升级旅程框架的插图。](media/upgrade-banner-main.png "确保你的项目已设置为使用正确的项目团队成功。定义项目范围、目标和时间线。确认技术和用户就绪情况。执行你的推出计划。保持势头以最大化结果。")

在相关页面上查找此框架图形，以确定你在升级过程中所处的位置。

## <a name="sample-upgrade-timeline"></a>升级时间线示例

升级过程在开始规划更改时开始。 下面是一个示例时间线，它以成功框架为指导，从升级前阶段开始，在升级过程中规划和准备升级，并进入帖子升级操作阶段，旨在维持和放大结果。 

> [!NOTE]
> 我们了解，你Teams的过程可能涉及到在不同时间利用多个[模式](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)和升级用户组，这使你可以控制用户升级体验，同时保持Teams的势头。  

为了帮助演示升级旅程的展开方式，我们提供了下面的示例计划，用于定义从 Skype for Business Online 到 Islands 模式到仅Teams的旅程。 此外，示例计划概述了将其用户划分为四个升级组或队列的组织。 使用此模板，自定义计划以包含特定的Teams旅程，并结合要使用的各种[模式](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)以及要将用户分段到的升级组的数量。 

## <a name="pre-upgrade"></a>升级前

**为组织准备Teams**。 为了帮助确保成功升级到Teams，请务必分配足够的时间进行准备。 你的组织不仅能够快速开始实现Teams的价值，而且一旦Teams准备就绪，你将能够从Skype for Business加速升级。 如果已在Skype for Business一起启用Teams，请在将用户升级到Teams之前，使用这些升级前活动作为检查点来验证组织的就绪情况。 

> [!TIP]
> 除了示例升级项目计划和试点测试计划外，还下载用于模板用户就绪情况材料（例如通信和用户调查）的 [升级成功工具包](https://aka.ms/UpgradeSuccessKit) 。 工具包中可用的项在下面的列表中标记有星号 (*) 。

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>计划：创建升级计划，以帮助确保组织设置为长期成功

| 步骤 |&nbsp;| 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **定义利益干系人** | 分配负责推动升级成功的项目团队成员。 | [登记利益干系人](upgrade-enlist-stakeholders.md) |
| **2** | **定义项目愿景和范围** | 设计“大局”愿景和当前项目范围，为升级旅程创建蓝图。 | [Project视觉](upgrade-define-project-scope.md#project-vision) <br> <br>[Project范围](upgrade-define-project-scope.md#project-scope) |
| **3** | **定义项目目标** | 设置目标目标，使你能够衡量进度和项目成功。 | [Project目标](upgrade-define-project-scope.md#project-goals) |
| **4** | **确定风险和缓解计划** | 制定缓解计划，确保在出现问题时可以快速使项目恢复正轨。 | [风险和缓解](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **定义时间线** | 设置时间线和关键里程碑，帮助项目保持按时和按预算。 | [时间表](upgrade-define-project-scope.md#timeline) <br><br> [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **6** | **定义适当的Skype for Business和Teams升级和共存策略** | 映射你的旅程，以确保为组织提供从Skype for Business到Teams的最佳路径。 | [了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[了解电话系统和 PSTN 连接选项](cloud-voice-landing-page.md)<br><br>  [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>准备：评估组织的Teams准备情况

| 步骤 |&nbsp;  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **评估环境并完成Teams技术载入** | 确保环境已准备好Teams，以帮助优化用户体验，并随时间推移促进升级。 | [在升级到Teams之前评估环境](upgrade-plan-journey-evaluate-environment.md)。<br><br> [准备服务以升级到Teams](upgrade-prepare-environment-prepare-service.md) |
| **2** | **针对Teams优化网络，特别是针对实时媒体方案** | 如果要部署音频、视频或会议，请执行以下附加步骤来优化网络以实现该功能。 | [准备网络以升级到Teams](prepare-network.md) |
| **3** | **评估组织更改就绪情况并定义团队合作方案** | 了解用户基础，以准备正确的价值消息传送和教育水平，以促进和加速用户采用。 | [组织更改就绪情况](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **准备用户就绪性计划，以定义如何与用户进行通信、训练和支持** | 个性化你的通信、培训和支持计划，以确保最优地接受新技术。 | [准备用户就绪性计划](upgrade-user-readiness.md)<br><br>[升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **5** | **宣布即将启动的Microsoft Teams** | 尽早沟通，帮助用户感到被包容、减少混乱和产生兴奋。 | [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **6** | **为 IT 人员准备Teams** | 确认你的技术和支持人员已准备好所需的一切，并支持你的技术环境进行Teams。 | [为 IT 人员准备Microsoft Teams](upgrade-prepare-it-pros.md) <br><br> [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>试点：运行试点以确认组织已准备就绪，并告知最佳Teams

| 步骤 | &nbsp; | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **试点物流大纲** | 定义正式的试点物流，以帮助验证组织升级或共存的准备情况。 | [试点物流大纲](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **选择试点参与者和测试方案** | 确定可以帮助验证团队合作方案并验证Teams就绪情况的用户。 | [选择试点参与者和测试方案](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **设计测试计划和反馈调查** | 确定为参与者完成的明确定义的任务，以及一种让他们分享反馈的方式。 | [设计测试计划和反馈调查](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **创建试点通信计划** | 教育试点参与者了解发生了什么、何时以及为什么以及对他们的预期。 | [创建通信计划](pilot-essentials.md#4-create-your-communications-plan)<br><br>[升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **5** | **进行试点** | "开始"菜单试点，跟踪进度并根据需要循环访问，以优化试点结果。 | [进行试点](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **评估学习并评估你的前进计划** | 收集用户反馈、网络统计信息和支持票证，以便根据目标进行分析，并确定你的前进计划。 | [评估学习并评估你的前进计划](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>部署：运行与Skype for Business共存的Teams

| 步骤 |&nbsp;  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **宣布正式推出Teams** | 当Teams准备就绪时，发送正式发布公告，从而产生兴奋和动力。 | [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **2** | **实现升级** | 执行的步骤取决于当前部署的Skype for Business。 | [实现升级](upgrade-to-teams.md) |
| **3** | **随时了解Teams路线图** | 监视Teams路线图，确定组织迁移到Teams的合适时间。 | [Teams路线图](https://aka.ms/teamsroadmap) |
| **4** | **发送更多的沟通，并与Teams冠军接触，以推动兴奋和采用Teams** | 鼓励用户采用，并保持兴奋Teams与正在进行的沟通和冠军。 | [Microsoft 365冠军计划](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>升级 

**正式转向Teams**。 升级用户时，将用户移动到仅Teams模式。 Teams成为聊天、会议、通话和协作的主要应用，并且禁用了对Skype for Business应用的访问。 虽然此阶段的技术方面很简单，但请考虑更改可能对用户体验的影响，并留出时间让用户将活动从Skype for Business正式过渡到Teams。 若要减少具有不同客户端的不同体验的用户，请尝试将端到端升级窗口限制为 45 天左右。

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>升级：实现从Skype for Business升级到Teams

| 步骤 |&nbsp;  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **确认已完成上述升级前活动** | 通过确认所有规划和准备活动的完成，帮助确保升级成功。 | 以上所有内容 |
| **2** | **启动与第一个升级组中的用户的通信** | 通知用户升级正在开始，并在整个过程中通知他们。 | [准备用户就绪性计划](upgrade-user-readiness.md) <br><br> [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **3** | **使共存模式仅针对第一个升级组中的用户Teams** | 按照适用于Skype for Business环境的步骤执行技术用户迁移。 | [从 Skype for Business Online 升级到 Teams](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[从本地Skype for Business升级到Teams](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **在滚动周期中对其余升级组重复上述升级活动** | 继续根据计划推动正在进行的通信计划和升级用户组。 | |
| **5** | **向所有用户发送帖子升级反馈调查** | 使用反馈调查来捕获来自用户的反馈和见解。 | [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>升级后

**使用Teams最大化业务价值**。 组织完全升级到Teams后，请花时间根据目标评估成功，并实施计划以继续推进势头。 

### <a name="operate-measure-the-success-of-your-upgrade"></a>操作：度量升级成功

| 步骤 | &nbsp; | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **评估初始升级成功** | 根据在升级前阶段建立的目标评估进度。 | [Project目标](upgrade-define-project-scope.md#project-goals) |
| **2** | **为未走上正轨的任何目标实施缓解计划** | 为未达到的目标定义缓解或课程更正策略。 | [Project目标](upgrade-define-project-scope.md#project-goals) |
| **3** | **监视网络运行状况和质量** | 实施质量检查和监视计划，以帮助确保用户体验良好，并减少对支持人员的调用。 | [监视网络运行状况和质量](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **推动用户势头和采用** | 通过正在进行的采用计划，鼓励用户采用并保持对Teams的兴奋。 | [推动用户势头和采用](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **准备新功能** | 通过为新的创新和产品改进建立更改周期，实现最大价值。 | [准备新功能](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> 我们的升级内容不断演变。 请务必查看最新指南，并阅读[Teams博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)。 

> [!Important]
> Skype for Business在线于2021年7月31日停用。 为了最大程度地实现利益并确保组织有适当的时间实现升级，我们鼓励你今天开始Microsoft Teams。 请记住，成功升级符合技术和用户准备情况，因此，在导航到Microsoft Teams的旅程时，请务必利用此处的指导。