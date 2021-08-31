---
title: Microsoft Teams 管理快速入门
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
ms.localizationpriority: medium
search.appverid: MET150
description: 快速入门，介绍为采用计划的第 2 阶段Microsoft Teams关键决策。
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
ms.openlocfilehash: eaeec25c90e800fcc688dad924ecac8de687841a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733711"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft Teams 管理快速入门

以下活动将同时发生，并且可能涉及关键团队的一部分或所有部分。 最佳做法是，完成初始试验后，推迟针对 的大规模治理和安全Teams。 请务必了解治理决策如何影响最终用户体验，并简化以后需要做出的决策。 在此阶段，需要做出一些决策。 若要成功创建它们，首先需要回答以下问题：

- 之前评估中的哪个利益干系人是参与此有限业务载入的不错候选者？
- 此个人或 (组) 建议适合此阶段的用例？  
- 他们是否对组织中员工有足够的兴趣，能够成为早期采用者，并定期提供有意义的反馈？ 

若要了解有关详细信息[，请阅读规划](plan-teams-governance.md)Teams[中的监管](plan-teams-lifecycle.md)和规划 Teams。

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![表示决策点的图标。](media/teams-adoption-decision-icon.png)决策

此时做出以下 (，这些决策仅适用于第 2 阶段) ：

### <a name="decision-1-who-can-create-teams"></a>决策 1：Who团队 

就此阶段来说，除了核心项目团队外，还可以将能够创建团队的人限制为早期采用者群体。 这样，早期采用者可根据需要创建其他团队。 监视此行为将为广泛部署提供关键信息。

### <a name="decision-2-teams-naming-conventions"></a>决策 2：Teams命名约定 

你可能希望实现一些命名约定来广泛部署 Teams，并检查重复的名称。 在阶段 2 中，建议仅为初始项目实施手动命名约定。 为此，最佳做法是与早期采用者项目团队开展互动载入，并允许他们选择自己的名称。 这可让你深入了解员工对工作的想法，并且对于以后创建更大的规模命名约定至关重要。  (本指南稍后将介绍有关交互式载入元素的其他信息。) 

### <a name="decision-3-guest-access"></a>决策 3：来宾访问

根据项目的范围和类型以及行业的性质，启用与合作伙伴或供应商的安全协作可能是要测试的基本功能。 可以使用适当的租户控件限制哪些人可以将来宾添加到团队，使用敏感度标签限制向来宾开放的团队。 此外，还可确保来宾遵守组织安全要求，例如使用多重身份验证 (MFA) 。

### <a name="decision-4-approved-apps"></a>决策 4：批准的应用

最佳方案Teams包括将其他应用集成到体验中。 技术团队至少应该在体验中启用第一方和特色Teams应用。 根据你的用例和组织中使用的其他应用，你可以选择在受控试验中包括其他应用。 请务必检查任何第三方应用，确保它们符合组织的安全性和符合性要求。

### <a name="decision-5-are-meetings-included-in-your-test"></a>决策 5：测试是否包含会议？ 

Teams会议体验是高质量的，支持视频聊天，并且让员工聚在一起，提高效率。 请咨询技术团队，确保环境已准备好包含简单的 VoIP 会议。 启用音频会议或语音服务通常排除在试验的此阶段;但是，这取决于核心项目团队、技术准备情况以及组织中其他语音/会议服务的状态。 技术准备情况应包括会议室设备、最终用户设备和附件以及网络等内容。 我们建议在试验中包括视频聊天和 VoIP 会议，以从你的游戏实现Teams价值。 

### <a name="decision-6-content-management-and-structure"></a>决策 6：内容管理和结构
Teams在平台中端到端工作（而不是要求他们不断切换回旧系统和服务）时，此模式效果最佳，并提供不同于用户习惯的新工作方式。 作为试验的一部分，与参与者合作，考虑采用多模式协作方式的团队结构和频道，Teams 中协作，避免仅复制现有的文件夹和存储结构。 此外，请考虑存储在现有受支持系统（如记录管理或备份系统）之外的内容的任何合规性要求。

### <a name="decision-7--data-security"></a>决策 7：数据安全性

为广泛部署做准备，可以选择使用安全标签对环境中的团队类型进行分类。 出于此实验的目的，建议参考 Teams 中的监管计划[，](plan-teams-governance.md)并确保已针对 Microsoft 365 中的 Teams 数据设置了基本保留策略。 您可能需要与技术团队协调此工作，因为Microsoft 365需要管理员权限才能完成此工作。

### <a name="decision-8-length-of-your-experiment"></a>决策 8：试验的长度

成功Teams实施工作会以正常的速度进行，以确保获得适当的发展动力、专注和学习成果。 我们建议项目的此阶段长度为 60 天，以确保早期采用者能够完成足够的业务周期。 将试验时间延长过长会增加更改计划失败的风险;但是，这一时间因每个组织而异。  

![表示下一步骤的图标。](media/teams-adoption-next-icon.png) 下一 [步：定义使用方案](teams-adoption-define-usage-scenarios.md)
