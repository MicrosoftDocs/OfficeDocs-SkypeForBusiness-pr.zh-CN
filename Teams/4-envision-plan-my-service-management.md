---
title: 规划 Microsoft Teams 服务管理
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 通过规划运营角色并分配质量保证者，提供和维护高质量的部署。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: df7d051f6ea140ab74532904994ea3ed5914d066
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624864"
---
# <a name="plan-my-service-management"></a>规划服务管理

本文概述了提供和维护高质量部署所需的Microsoft Teams要求。 在首次试点或生产部署之前，可以通过在展望阶段规划服务管理和质量来帮助确保部署得以成功。

## <a name="service-management-for-teams"></a>服务管理Teams

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams服务包括Microsoft 365或Office 365部署在本地的基础结构组件，例如 (网络) 。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已经实施了与现有服务关联的流程和任务。 尽管如此，当你现在规划服务管理以在将来支持 Microsoft Teams 时，你可能会扩大已实施的方面。

服务管理包含管理 Microsoft Teams 端到端时涉及的所有活动和流程。 服务管理的某些组件（Microsoft 365 或 Office 365 服务本身包含的基础结构组件）由 Microsoft 负责，而客户对其用户负责管理 Teams、网络和他们提供的终结点的各个方面。
有关客户对服务管理的责任Teams及其与影响用户体验质量的关键组件之间的关联，请参阅服务管理和质量[规划](./prepare-network.md)。

![质量的三个组件示意图](media/plan-my-service-management-image1.png "质量的三个组件（Microsoft 365或Office 365、网络和终结点）的示意图，以及服务管理如何与这三个组件重叠。")

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a>《操作指南》简介 

**什么内容**、**什么人** 和 **什么方式** 是在讨论服务质量时需要回答的三个重要问题。

你可以使用《[操作指南](./1-drive-value-operate-my-service.md)》帮助你解决所有这三个问题。 该指南提供了每天、每周、每月及按需执行的活动列表。 这些活动和任务对于维护高质量 Teams 部署至关重要。 确定谁将负责在服务管理中执行特定活动是在展望阶段早期需要执行以确保部署得以成功的规划的关键方面。 在确定了任务和活动后，需要你将其分配到的小组或个人了解并遵循这些任务和活动。 《操作指南》提供了有关如何执行每个任务的知识和指导，以及/或外部内容的参考。

## <a name="plan-for-operational-role-mapping"></a>规划操作角色映射

早期规划服务管理是一个关键的里程碑，因为在启用首批试点用户时即开始操作阶段。 项目团队必须审阅并同意所需的任务和活动，确定负责每个运营任务的团队，以及得到各个团队的承诺和签字认可。

在完成签字认可后，负责团队必须开始执行这些角色和职责。 这可能包括培训和就绪工作、更新人员配置模型或确保外部合作伙伴已准备好交付。

在"构想"阶段的早期映射操作角色可让所有团队在试点期间启动其操作任务并提升操作，并确保部署开始后一切准备就绪。

《操作指南》提供了映射到在大多数方案中应该会有效的典型角色的常见任务列表。 你需要自定义这些职责以适用于你的组织。

>[!TIP]
>下面是一个模板示例，用于记录为支持此项目而执行的操作角色映射练习的结果。


|操作角色 |说明 |团队 |联系人详细信息 |
|---------|---------|---------|---------|
|服务所有者|服务所有者，与业务部门的界面，策略|TBA|TBA|
|音频会议操作|日常操作、用户和设备帐户移动/添加/更改、监视|TBA| TBA| 
|租户管理员|更改租户范围的设置，启用新功能|TBA|TBA|
|技术支持|用于获取支持的用户界面|TBA|TBA|
|网络操作|运行 LAN、WAN、Wi-Fi 和 Internet 访问|TBA|TBA|
|客户端&终结点团队|管理桌面部署|TBA|TBA|
|标识操作|管理 Active Directory (Active Directory、Active Directory 联合身份验证服务、Azure AD) |TBA|TBA|
|采用/更改管理|管理解决方案的认知、培训和采用|TBA|TBA|
|Exchange操作|管理Exchange环境|TBA|TBA|
|电话操作|管理 SBC 和电话号码|TBA|TBA|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a>质量支持者角色

在所有组织中，都需要小组或个人为质量负责。
这是服务管理中最重要的角色。 质量冠军是一个客户角色，分配给对用户体验充满热情的人或组。 此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。
质量冠军的最佳候选者通常是客户服务所有者，根据组织的大小和复杂程度，他们可能是任何对用户体验充满热情的人或组。

质量保证者利用现有工具和记录的流程（例如呼叫质量仪表板 (CQD) 和质量体验评审指南）来监视用户体验、识别质量趋势，并根据需要推动修正。 质量冠军会与相应的团队协作，推动补救措施，向指导委员会报告进度并解决问题。

操作指南中记录了与该角色关联的任务和活动。 应在展望阶段早期分配此角色。 执行质量支持者角色时的一个主要步骤是获取该角色所需的知识，以及确保在执行任务时满足先决条件。 此角色的一个主要任务是运行定期质量体验评审。

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a>《体验质量评审指南》简介

质量体验评审指南具有一组活动，评估对改善用户体验影响最大的主要领域并提供修正指南，如下图所示。

![说明在质量体验评审过程中要检查的关键问题](media/plan-my-service-management-image2.png "在质量体验评审期间要检查的关键问题：音频、可靠性和用户测试结果。")

通过持续评估并修正本文档中所述的方面，你可以降低其对用户体验的潜在负面影响。 在部署中遇到的大多数用户体验问题可以分为以下类别：

-   防火墙或代理配置不完整

-   Wi-Fi 覆盖范围较小

-   带宽不足

-   VPN

-   使用了未优化或内置的音频设备

-   子网或网络设备存在问题

《体验质量评审指南》主要指导如何将通话质量仪表板 (CQD) 作为主要工具进行在线使用来报告和调查所述的每个方面，且重点在音频方面，以最大限度地提高采用率和作用。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

我们强烈建议你尽早提名质量冠军。 获得提名后，应开始熟悉质量体验评审指南 [中的内容](./quality-of-experience-review-guide.md)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定谁对组织中云语音操作负责。</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>下载服务管理规划完整指南。</li><li>下载质量体验评审指南。</li><li>完整查看操作指南。</li><li>向每个运营团队成员提供所有指南，以便查看并熟悉操作要求。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->