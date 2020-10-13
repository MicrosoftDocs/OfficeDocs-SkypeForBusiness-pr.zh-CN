---
title: Microsoft Teams 管理快速入门
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: 快速入门，其中介绍了你将在 Microsoft 团队采纳计划的第2阶段中需要执行的关键决策。
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424552"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft Teams 管理快速入门

以下活动将同时发生，并且它们可能涉及所有或部分关键团队。 最佳做法是，在您完成对团队的初始实验后，推迟大规模管理和安全对话。 了解监管决策对最终用户体验有何影响，并将在此之后的日期简化所需决策，这一点非常重要。 在此阶段中，需要进行一些决策。 若要成功地进行设置，您首先需要回答以下问题：

- 以前评估的哪些风险承担者很好地参与此有限的企业版加入？
- 是否有此个人 (或一组个人) 建议的使用案例，这些使用案例将非常适合于此阶段？  
- 他们是否有足够的兴趣让组织中的员工获得更早的使用者，并为您提供有意义和定期的反馈意见？ 

若要了解详细信息，请阅读 [团队中用于管理的计划](plan-teams-governance.md) 和 [团队中的生命周期管理规划](plan-teams-lifecycle.md)。

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![代表决策点的图标](media/teams-adoption-decision-icon.png)判断

请按照以下决策 (，这些决策仅适用于第2阶段) ：

### <a name="decision-1-who-can-create-teams"></a>决策1：谁可以创建团队 

出于本阶段的目的，你可以限制哪些用户能够创建团队到你的核心项目团队之外的早期使用者填充。 这将允许你的早期采纳者根据需要创建其他团队。 监视此行为将为你的广泛部署提供关键信息。

### <a name="decision-2-teams-naming-conventions"></a>决策2：团队命名约定 

你可能需要为你的团队广泛部署实现一些命名约定，并检查重复的名称。 在第2阶段，我们建议你仅为初始项目实现手动命名约定。 执行此操作的最佳做法是与早期的使用者项目团队进行交互式式加入，并允许他们选择自己的姓名。 这样，你就可以深入了解员工对其工作的看法，并将在以后创建更大的规模命名约定时对其有必要的了解。 有关交互式加入的元素的 (其他信息将在本指南的后面部分显示。 ) 

### <a name="decision-3-guest-access"></a>决策3：来宾访问

与你的项目的范围和类型以及你的行业的性质不同，支持与合作伙伴或供应商进行安全协作可能是你想要测试的重要功能。 你可以通过使用相应的租户控件来限制哪些人可以向团队中添加来宾，并通过使用敏感度标签限制哪些团队向来宾开放。 您还可以确保来宾遵守组织的安全要求，例如使用多重身份验证 (MFA) 。

### <a name="decision-4-approved-apps"></a>决策4：已批准的应用

团队的最佳使用情形包括将其他应用集成到体验中。 你的技术团队至少应在你的团队体验中启用第一方和特色应用。 根据你的组织中使用的使用案例和其他应用，你可以选择包括其他应用，作为你的受控实验的一部分。 请务必 vet 任何第三方应用，以确保它们遵守组织的安全和合规性要求。

### <a name="decision-5-are-meetings-included-in-your-test"></a>决策5：测试中是否包含会议？ 

团队会议体验为高质量，支持视频聊天，并将员工放在一起以提高效率。 咨询您的技术团队，确保您的环境已准备好加入简单的 VoIP 会议。 启用音频会议或语音服务通常会在实验的这一阶段被排除;但是，这取决于你的核心项目团队、你的技术准备以及你的组织中其他语音/会议服务的状态。 技术准备工作应包括会议室设备、最终用户设备和附件等内容，以及网络。 我们建议在实验中包括视频聊天和 VoIP 会议，以便从团队实施中获取更多价值。 

### <a name="decision-6-content-management-and-structure"></a>决策6：内容管理和结构
当用户在平台内进行端到端处理时，团队的效果最佳，而不是要求它们不断切换回旧版系统和服务，并提供了不同于用户习惯的新工作方式。 作为实验的一部分，请与你的参与者协作，以考虑团队结构和通道，这些结构和通道接受多模式的团队协作，避免直接复制现有文件夹和存储结构。 此外，请考虑对存储在现有支持系统（如记录管理或备份系统）之外的内容的任何合规性要求。

### <a name="decision-7--data-security"></a>决策7：数据安全

为广泛部署做好准备，您可以选择使用安全标签对环境中的团队类型进行分类。 出于本次实验的目的，我们建议你参考 [团队中的管理计划](plan-teams-governance.md) ，并确保在 Microsoft 365 中为团队数据设置了基本保留策略。 您可能需要与您的技术团队协调此工作，因为需要 Microsoft 365 管理员权限才能完成此工作。

### <a name="decision-8-length-of-your-experiment"></a>判定8：实验的长度

成功的团队实施将以正常的步调，确保适当的动量、重点和发现。 我们建议你的项目的这一阶段的长度为60天，以确保早期的采纳者完成充足的业务周期。 延长时间太长的实验会增加更改程序失败的风险;但是，此时间将因每个组织而异。  

![表示下一步骤的图标 ](media/teams-adoption-next-icon.png) ： [定义使用方案](teams-adoption-define-usage-scenarios.md)
