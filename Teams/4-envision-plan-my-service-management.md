---
title: 规划 Microsoft Teams 服务管理
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 通过规划运营角色和分配质量支持者来交付和维护高质量的部署。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f581a2b78c60783de809873fcb85e4b5173724
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241779"
---
# <a name="plan-my-service-management"></a>规划服务管理

本文概述了交付和维护高质量的 Microsoft Teams 部署需要达到的要求。 在首次试点或生产部署之前，可以通过在展望阶段规划服务管理和质量来帮助确保部署得以成功。

## <a name="service-management-for-teams"></a>Teams 服务管理

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams 服务包括 Microsoft Office 365 和在本地部署的基础结构组件（例如网络）。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已经实施了与现有服务关联的流程和任务。 尽管如此，当你现在规划服务管理以在将来支持 Microsoft Teams 时，你可能会扩大已实施的方面。

服务管理包含管理 Microsoft Teams 端到端时涉及的所有活动和流程。 服务管理的一些组件（构成 Office 365 服务自身的基础结构组件）属于 Microsoft 的职责范围，而客户负责为其用户管理自己提供的 Teams、网络和终结点的各个方面。
有关客户的 Teams 服务管理职责及其与用户体验质量所基于的主要组件的相关程度的详细讨论，请参阅[规划服务管理和质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide)。

![此示意图质量的三个组成部分（Office 365 服务、网络和终结点）以及服务管理如何贯穿于这三个组成部分。](media/plan-my-service-management-image1.png "此示意图显示了质量的三个组成部分（Office 365 服务、网络和终结点）以及服务管理如何贯穿于这三个组成部分。")

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a>《操作指南》简介 

**什么内容**、**什么人**和**什么方式**是在讨论服务质量时需要回答的三个重要问题。

你可以使用《[操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)》帮助你解决所有这三个问题。 该指南提供了每天、每周、每月及按需执行的活动列表。 这些活动和任务对于维护高质量 Teams 部署至关重要。 确定谁将负责在服务管理中执行特定活动是在展望阶段早期需要执行以确保部署得以成功的规划的关键方面。 在确定了任务和活动后，需要你将其分配到的小组或个人了解并遵循这些任务和活动。 《操作指南》提供了有关如何执行每个任务的知识和指导，以及/或外部内容的参考。

## <a name="plan-for-operational-role-mapping"></a>规划运营角色映射

早期规划服务管理是一个关键的里程碑，因为在启用首批试点用户时即开始操作阶段。 项目团队必须审阅并同意所需的任务和活动，确定负责每个可操作任务的团队，以及得到各个团队的承诺和签字认可。

在完成签字认可后，负责团队必须开始执行这些角色和职责。 这可能包括培训和就绪工作、更新人员配置模型或确保外部合作伙伴已准备好交付。

在展望阶段早期映射运营角色可让所有团队在试点期间开始执行其运营任务、扩大运营以及确保在部署开始后一切都已准备好。

《操作指南》提供了映射到在大多数方案中应该会有效的典型角色的常见任务列表。 你需要自定义这些职责以适用于你的组织。

>[!TIP]
>下面是用于记录你为了支持此项目而执行的运营角色映射行动的结果的模板示例：


|运营角色 |说明 |团队 |联系详细信息 |
|---------|---------|---------|---------|
|服务所有者|服务所有者、与业务部门的接口、策略|TBA|TBA|
|音频会议运营|日常运营、用户和设备帐户移动/添加/更改、监控|TBA| TBA| 
|租户管理员|更改租户范围的设置、启用新功能|TBA|TBA|
|支持|供用户获取支持的接口|TBA|TBA|
|网络运营|运行 LAN、WAN、Wi-Fi 和 Internet 访问|TBA|TBA|
|客户端和终结点团队|管理桌面部署|TBA|TBA|
|身份操作|管理身份基础结构 (Active Directory、Active Directory 联合身份验证服务、Azure AD)|TBA|TBA|
|采用/变更管理|管理解决方案的认知、培训和采用|TBA|TBA|
|Exchange 运营|管理 Exchange 环境|TBA|TBA|
|电话服务操作|管理 SBC 和电话号码|TBA|TBA|

为了便于完成更加详细的运营角色映射（包括与每个运营角色关联的任务），你可以使用[运营角色映射工作簿](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16)获取将明确角色和职责的详细信息以支持云语音工作负荷。

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a>质量支持者角色

在所有组织中，都需要小组或个人为质量负责。
这是服务管理中最重要的角色。 质量支持者是分配给关心其用户体验的个人或小组的客户角色。 此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。
质量支持者的最佳候选人通常是客户服务所有者，根据组织的规模和复杂程度，可以是关心用户体验的任何个人或小组。

质量支持者利用现有的工具和记录的流程（例如通话质量仪表板 (CQD) 和《体验质量评审指南》）来监控用户体验、识别质量趋势以及在需要的情况下推动修正。 质量支持者与各个团队合作以推动采取修正措施，并就进度和未解决的问题向指导委员会报告。

《操作指南》中记录了与该角色关联的任务和活动。 应在展望阶段早期分配此角色。 执行质量支持者角色时的一个主要步骤是获取该角色所需的知识，以及确保在执行任务时满足先决条件。 此角色的一个主要任务是运行定期质量体验评审。

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a>《体验质量评审指南》简介

《体验质量评审指南》中包含一组活动，用于评估影响最大的主要方面并提供修正指导以改进用户体验，如下图所示。

![在质量体验评审过程中要检查的主要方面：音频、可靠性和用户调查结果。](media/plan-my-service-management-image2.png "在质量体验评审过程中要检查的主要方面：音频、可靠性和用户调查结果。")

通过持续评估并修正本文档中所述的方面，你可以降低其对用户体验的潜在负面影响。 在部署中遇到的大多数用户体验问题可以分为以下类别：

-   防火墙或代理配置不完整

-   Wi-Fi 覆盖范围较小

-   带宽不足

-   VPN

-   使用了未优化或内置的音频设备

-   子网或网络设备存在问题

《体验质量评审指南》主要指导如何将通话质量仪表板 (CQD) 作为主要工具进行在线使用来报告和调查所述的每个方面，且重点在音频方面，以最大限度地提高采用率和作用。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

强烈建议尽早指定质量支持者。 在被指定为质量支持者后，这些人应开始了解[《体验质量评审指南》](https://aka.ms/qerguide)中的内容。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>确定负责贵组织的云语音操作的人员。</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>下载规划服务质量完整指南。</li><li>下载《体验质量评审指南》。</li><li>仔细查看操作指南。</li><li>向所有操作团队成员提供所有指南以进行查看并熟悉操作要求。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->