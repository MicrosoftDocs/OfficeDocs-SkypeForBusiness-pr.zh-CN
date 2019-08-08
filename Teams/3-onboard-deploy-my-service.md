---
title: 部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下载网站支持行动手册以规划团队推出并加速和优化用户的采纳、质量和满意度的理解。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17b73629aa874232a449605b45f97ea10e445204
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232283"
---
# <a name="deploy-my-service"></a>部署服务

本文概述了正确部署云语音服务的要求。 通过遵循部署云语音服务的说明性指南, 你可以确保成功地考虑所有要求并提供可重复的结果。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Microsoft 团队的网站支持行动手册语音工作负载

使用本行动手册可帮助你的组织在逐个网站的基础上成功地计划和执行 Microsoft 团队语音功能的推出。

包括所有所需的活动、推荐的时间线和指向每个活动的相应指南的链接, 此操作手册介绍了端到端指南以帮助确保成功的团队为特定网站进行语音部署, 重点关注重要因素给用户。

通过完成本操作手册中的活动, 你的组织可以:

-   有效地规划和安排团队推出。

-   加速和优化用户采纳。

-   减少支持需求并提高用户满意度。

> [!NOTE]
> 本文和关联的操作手册不用于描述服务启用所需的每个技术配置步骤或向特定网站提供拨号音。 而是将重点放在最适合于板载用户的活动和任务, 并让他们通过快速平稳过渡来开始使用团队语音工作负载, 同时将支持需求降至最低。 有关如何最佳配置团队语音环境的技术指导, 请参阅用于[配置团队语音工作负载](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)的加入清单、[配置团队中的直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)、[团队核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)、[网络对于团队](onboarding-checklist-configure-networking.md)和[启用 Office 365](onboarding-checklist-enable-office-365.md)。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>行动手册重点领域

行动手册的重点是解决影响用户对团队语音部署的认知的因素。 活动和任务分组到以下重点区域:

-   服务准备情况验证
    - 音频会议
    - 通话套餐
    - 直接路由

-   用户启用

-   终结点

-   使用情况和质量

-   采用

[适用于语音 (行动手册) 的网站支持行动手册](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 工作簿。 这五个焦点区域中的每一个都是工作簿中的单独工作表, 每个部署任务和活动都分组到其中一个工作表中。

![网站支持行动手册的屏幕截图](media/deploy-my-service-image1.png "行动手册的屏幕截图")

> [!NOTE]
> 你将为团队推出的范围内的每个网站创建一个单独的 "行动手册" 实例。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>如何使用行动手册

无论位置的大小和复杂程度如何, 启用每个网站都需要尽早对任务和活动进行计划, 并在实际服务推出之前和之后以最佳顺序执行它们。 我们建议你在计划和执行你自己的 Microsoft 团队语音操作时, 按照以下步骤操作。

1. 下载适用于 Microsoft 团队语音的[网站支持行动手册 (行动手册)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 。

2. 为每个网站创建一个单独的行动手册副本。

3. 在名为 "**行动手册: {Sitename 代码}**" 的工作表的选项卡上, 将 **{sitename 代码}** 替换为相关的站点名称和/或站点代码。

4. 输入**网站名称、网站代码**和**计划启动日期**, 如下所示。 这是一个关键步骤, 因为它可调整行动手册中每个活动的建议截止时间。

   ![包含网站名称、网站代码和计划启动日期的示例](media/deploy-my-service-image2.png "示例, 包含纽约的网站名、网站代码 NY01 和计划开始日期 20-3 月 18")日

5. 检查每个活动, 执行必要的操作, 并在遍历日程表时更新状态。 状态以图形形式表示, 如下所述:
  
   - ![绿色复选标记](media/deploy-my-service-image3.png)为 **"是" 或 "不适用" (绿色)** 的插图: 活动已完成, 或者不适用于此网站, 不需要执行其他操作。</li>
   - ![](media/deploy-my-service-image4.png) <strong>活动尚未完成的黄色感叹号的插图 (黄色):</strong>该活动尚未完成, 并且必须在其计划中更新为 "是" 或 "否"。</li>
   - ![红色 X 表示 "不](media/deploy-my-service-image5.png) <strong>否" (红色)</strong>的插图: 由于存在问题, 无法完成活动, 并且必须携带给项目状态会议。</li></ul>

6. 状态将在每个分区内进行汇总, 分区标题将设置为这些状态标记之一。 **每周状态**也会自动更新。

![行动手册中的 "每周状态" 滚动屏幕截图](media/deploy-my-service-image6.png "行动手册中的 \"每周状态\" 滚动屏幕截图")

> [!TIP]
> 对您拥有的所有位置重复上述步骤。

> [!IMPORTANT]
> 某些步骤可能不适用于所有位置和网站。 如果特定活动不与网站相关, 则必须选择 "**不适**用于此活动"。 **不要删除操作**手册中的任何行;如果执行此操作, 则状态汇总公式将不起作用。<br/><br/>
注意可能花费比计划更多时间的活动, 例如号码移植和采购活动。 这些活动可能会对网站部署时间线产生负面影响。 请务必查看和更新活动列表和关联的日程表每周, 并在[筹划指导委员会会议](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)中展示它们, 以确保利益干系人了解每个网站的状态以及部署计划的任何可能的偏差。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定你的部署是否需要网站支持行动手册。</li><li>确定负责为您要部署的每个网站自定义 Microsoft 团队的网站支持行动手册的人员。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下载网站支持行动手册</a>。</li><li>为您的第一个网站自定义 "网站支持行动手册"。</li><li>根据需要重复其他网站的操作。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->