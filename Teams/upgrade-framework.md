---
title: 关于升级框架 - Skype for Business Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用经过验证的成功框架来帮助组织从Skype for Business到Teams。
localization_priority: Normal
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
ms.openlocfilehash: 78215457177689b549112a19a9477fdd01c91de2
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282509"
---
# <a name="about-the-upgrade-framework"></a>关于升级框架

为了帮助从升级旅程中排除猜测，我们采用了经过验证的框架来实现更改。 如下图所示，框架中的每个步骤都基于之前的步骤，为获得最佳结果，我们建议按照以下步骤顺序操作。  

首先，将适当的利益干系人汇集在一起，并定义升级 (，例如范围、目标和日程表) 。 制定计划后，请确认技术环境，最终用户已准备好Teams。 然后，在准备就绪时分步实施升级，从试点升级迁移到组织范围的升级。 组织运营后，Teams运营计划来监视质量并加快用户采用速度。

![升级旅程框架插图](media/upgrade-banner-main.png "确保项目已设置好，以与合适的项目团队一起获得成功。定义项目范围、目标和日程表。确认技术和用户就绪性。执行推出计划。保持动力以最大化结果。")

在相关页面上查找此框架图形，确定在升级过程中位于何处。

## <a name="sample-upgrade-timeline"></a>示例升级时间线

开始规划更改时，升级过程将开始。 下面以成功框架为指南，从升级前阶段开始，你将从升级前阶段开始规划并准备升级，并进入升级后操作阶段，旨在维持和增强结果。 

> [!NOTE]
> 我们知道，Teams过程可能涉及利用多种模式并在不同的时间升级用户组 [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)，这使您能够控制用户升级体验，同时使用   Teams。  

为了帮助演示升级旅程的展开方式，我们在下面提供了一个示例计划，用于定义从 Skype for Business Online 模式到群岛模式Teams过程。 此外，该示例计划概述了一个组织，该组织已将用户分成四个升级组或队列。 使用此功能作为模板，自定义计划以包含到 Teams 的特定旅程，并合并将使用的各种模式以及将用户 [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)细分到的升级   组数。 

## <a name="pre-upgrade"></a>升级前

**为组织准备Teams。** 若要帮助确保成功升级到 Teams，必须分配足够的时间进行准备。 组织不仅能够快速开始意识到 Teams 的价值，并且只要准备就绪，Skype for Business Teams升级。 如果已与 Teams一Skype for Business，请使用这些升级前活动作为检查点，在将用户升级到 Teams。 

> [!TIP]
> 除了示例 [升级项目](https://aka.ms/UpgradeSuccessKit)计划和试点测试计划外，下载模板用户准备情况材料（例如通信和用户调查）的升级   成功工具包。 工具包中可用的项目标有星号 (*) 列表。

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>计划：创建升级计划，帮助确保组织已针对长期成功进行设置

| 步骤 |  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **定义利益干系人** | 为推动升级成功的项目工作组成员分配负责。 | [召集利益干系人](upgrade-enlist-stakeholders.md) |
| **2** | **定义项目愿景和范围** | 设计"大图"愿景和当前项目范围，为升级过程创建蓝图。 | [Project视觉](upgrade-define-project-scope.md#project-vision) <br> <br>[Project范围](upgrade-define-project-scope.md#project-scope) |
| **3** | **定义项目目标** | 设置目标目标，以便衡量进度和项目成功。 | [Project目标](upgrade-define-project-scope.md#project-goals) |
| **4** | **确定风险和缓解计划** | 制定缓解计划，确保在出现问题时可以快速让项目回到正轨。 | [风险和缓解措施](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **定义时间线** | 设置日程表和关键里程碑，帮助项目保持时间和预算。 | [时间线](upgrade-define-project-scope.md#timeline) <br><br> [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **6** | **定义适当的Skype for Business Teams和共存策略** | 映射旅程，确保从Skype for Business到Teams的最佳路径。 | [了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[了解电话系统 PSTN 连接选项](cloud-voice-landing-page.md)<br><br>  [选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>准备：评估组织的准备情况Teams

| 步骤 |  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **评估环境并完成Teams加入** | 确保环境已准备就绪，Teams用户体验优化，并随着时间的推移促进升级。 | [在升级到 Teams 之前，请评估Teams。](upgrade-plan-journey-evaluate-environment.md)<br><br> [准备服务以升级到 Teams](upgrade-prepare-environment-prepare-service.md) |
| **2** | **优化Teams网络，尤其是实时媒体方案** | 如果要部署音频、视频或会议，请执行这些附加步骤来优化网络以使用该功能。 | [准备网络以升级到 Teams](prepare-network.md) |
| **3** | **评估组织变更准备情况并定义团队协作方案** | 了解用户群，以准备正确的价值消息传递和教育程度，以便促进和加快用户采用。 | [组织变更就绪情况](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **准备用户准备计划，定义通信、培训和支持用户的方式** | 个性化你的通信、培训和支持计划，以确保以最佳方式利用新技术。 | [准备用户就绪性计划](upgrade-user-readiness.md)<br><br>[升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **5** | **宣布正在等待启动Microsoft Teams** | 尽早沟通，帮助用户感到被包含在内、减少混淆和产生兴奋感。 | [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **6** | **准备 IT 人员以Teams** | 确认技术和支持人员已准备好一切，并支持技术环境以Teams。 | [准备 IT 人员以Microsoft Teams](upgrade-prepare-it-pros.md) <br><br> [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>试点：运行试运行，确认组织已准备就绪，并告知最佳运行Teams

| 步骤 |  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **概述试点物流** | 定义正式的试点物流，帮助验证组织是否准备好升级或共存。 | [概述试点物流](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **选择试点参与者和测试方案** | 确定可帮助验证团队协作方案并验证Teams的用户。 | [选择试点参与者和测试方案](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **设计测试计划和反馈调查** | 确定明确定义的供参与者完成的任务，以及供他们分享其反馈的方法。 | [设计测试计划和反馈调查](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **创建试点通信计划** | 指导试点参与者了解发生的情况、时间、原因以及预期结果。 | [创建通信计划](pilot-essentials.md#4-create-your-communications-plan)<br><br>[升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **5** | **进行试点** | 启动试点，跟踪进度并根据需要进行跟踪，以优化试点结果。 | [进行试点](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **评估学习和评估前进计划** | 收集用户反馈、网络统计信息和支持票证，以便针对目标进行分析并确定前进计划。 | [评估学习和评估前进计划](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>部署：在Teams共存中运行Skype for Business

| 步骤 |  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **宣布正式发布Teams** | 准备就绪后，通过发送正式发布公告来Teams和动力。 | [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **2** | **实现升级** | 要执行的步骤取决于当前部署Skype for Business。 | [实现升级](upgrade-to-teams.md) |
| **3** | **随时了解Teams路线图** | 监视Teams路线图，确定适合组织移动到Teams。 | [Teams路线图](https://aka.ms/teamsroadmap) |
| **4** | **发送更多通信并Teams吸引支持者，以吸引观众的兴奋和Teams** | 鼓励用户采用，并保持对与Teams和支持者之间沟通的兴奋感。 | [Microsoft 365冠军计划](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>升级 

**让官方移动到 Teams。** 升级用户时，可将其移动到Teams模式。 Teams成为其主要应用，用于聊天、会议、呼叫和协作，以及Skype for Business应用的访问权限。 尽管此阶段的技术层面相当简单，但请考虑更改对用户体验的影响，并允许用户有时间将活动从 Skype for Business 转换为 Teams。 若要减少在不同客户端上拥有不同体验的用户，请尝试将端到端升级时段限制为 45 天左右。

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>升级：实现从Skype for Business到Teams

| 步骤 |  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **确认已完成上述升级前活动** | 确认完成所有规划和准备活动，帮助确保升级成功。 | 以上所有内容 |
| **2** | **启动与第一个升级组中用户的通信** | 通知用户升级正在启动，并在整个过程中随时通知他们。 | [准备用户就绪性计划](upgrade-user-readiness.md) <br><br> [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |
| **3** | **启用共存模式以Teams第一个升级组的用户** | 按照适用于用户Skype for Business的步骤执行技术用户迁移。 | [从 Skype for Business Online 升级到 Teams](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[从Skype for Business本地升级到 Teams](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **在滚动周期上为剩余的升级组重复上述升级活动** | 继续推动正在进行的通信计划，并基于计划升级用户组。 | |
| **5** | **向所有用户发送升级后反馈调查** | 使用反馈调查捕获用户的反馈和见解。 | [升级成功工具包](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>升级后

**使用 Teams 最大化业务Teams。** 组织完全升级到 Teams后，请花些时间根据目标评估成功，并实施计划以继续推动发展。 

### <a name="operate-measure-the-success-of-your-upgrade"></a>操作：衡量升级是否成功

| 步骤 |  | 摘要 | 资源 |
|------|--|---------|----------|
| **1** | **评估初始升级成功** | 根据升级前阶段制定的目标评估进度。 | [Project目标](upgrade-define-project-scope.md#project-goals) |
| **2** | **针对任何未实现的目标实施缓解计划** | 针对未达到的目标定义缓解或课程更正策略。 | [Project目标](upgrade-define-project-scope.md#project-goals) |
| **3** | **监视网络运行状况和质量** | 实施质量检查和监视计划，帮助确保获得积极的用户体验，并减少对技术支持的呼叫。 | [监视网络运行状况和质量](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **推动用户的发展和采用** | 通过持续采用计划鼓励Teams用户采用并保持对采用计划的兴奋。 | [推动用户的发展和采用](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **准备新功能** | 通过建立新创新和产品改进的变化周期来实现最大价值。 | [准备新功能](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> 我们的升级内容在不断发展。 请务必返回查看最新指南，并阅读 Teams[博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)。 

> [!Important]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。 为了最大程度地实现权益并确保组织有适当的时间来实施升级，我们鼓励你立即开始Microsoft Teams之旅。 请记住，成功的升级符合技术和用户准备情况，因此，在导航到 Microsoft Teams。