---
title: 部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下载网站启用操作手册，规划Teams推广，并加速和优化用户采用、质量感知和满意度。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5c027da20c6c305fd5924cd6483c5cbd63b8ddd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733537"
---
# <a name="deploy-my-service"></a>部署服务

本文概述了正确部署云语音服务的要求。 遵循部署云语音服务的规范性指南，确保成功满足所有要求并提供可重复的结果。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>适用于语音工作负荷的站点Microsoft Teams playbook

使用此操作手册可帮助组织成功地规划并执行Microsoft Teams站点语音功能的推出。

包括所有必需的活动、建议的时间线以及每个活动的相应指南的链接，此操作手册涵盖端到端指南，可帮助确保为给定网站成功部署 Teams 语音，并重点关注对用户重要的因素。

通过完成此操作手册中的活动，组织可以：

-   有效地计划和计划Teams部署。

-   加速和优化用户采用。

-   减少支持需求并增加用户满意度。

> [!NOTE]
> 本文和关联的 Playbook 并非旨在描述启用服务或向特定站点提供拨号音所需的每个技术配置步骤。 相反，他们专注于为用户轻松加入而建议的活动和任务，让他们通过快速流畅的采用率快速Teams使用语音工作负荷，同时尽量减少支持要求。 有关如何以最佳方式配置 Teams 语音环境的技术指南，请参阅用于配置[Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)语音工作负荷、在[Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)中配置直接路由、Teams[核心](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)功能、Teams 网络以及启用 Microsoft 365 或[Office 365](onboarding-checklist-enable-office-365.md)的载入[](prepare-network.md)清单。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Playbook 重点区域

Playbook 的重点是解决影响用户对语音部署Teams的因素。 活动和任务分组到以下重点区域：

-   服务就绪性验证
    - 音频会议
    - 通话套餐
    - 直接路由

-   用户启用

-   终结点

-   使用情况和质量

-   采用

Playbook 网站启用[Playbook (Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)) 是Microsoft Excel工作簿。 这五个重点区域都是工作簿中的一个单独的工作表，每个部署任务和活动都分组到其中一个工作表中。

![网站启用 playbook 的屏幕截图。](media/deploy-my-service-image1.png "Playbook 的屏幕截图")

> [!NOTE]
> 你将为实施计划范围内的每个站点创建一个单独的 playbook Teams实例。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>如何使用 playbook

无论位置的大小和复杂程度如何，启用每个网站都需要你尽早规划任务和活动，并按最佳顺序执行这些任务和活动-在推出实际服务之前、期间和之后。 建议在计划和执行自己的语音操作时执行Microsoft Teams步骤。

1. 下载适用于语音的语音 (Playbook) 网站Microsoft Teams [Playbook。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)

2. 为每个网站创建一个单独的 playbook 副本。

3. 在名为 **Playbook for {SiteName-Code}** 的工作表的选项卡上，将 **{SiteName-Code}** 替换为相关的网站名称和/或站点代码。

4. 输入" **网站名称、站点代码**"和 **"计划启动日期**"，如下所示。 这是一个关键步骤，因为它会调整操作手册中每个活动的建议期限。

   ![包含网站名称、站点代码和计划启动日期的示例。](media/deploy-my-service-image2.png "网站名称为纽约、站点代码 NY01 和计划发布日期为 3 月 20 日的示例")

5. 查看每个活动，采取必要操作，并更新浏览时间线时的状态。 状态以图形方式表示，如下所述：
  
   - ![绿色对号的插图。](media/deploy-my-service-image3.png) **是，或不适用于绿色 () ：** 活动已完成，或者不适用于此站点，无需进一步操作。</li>
   - ![黄色感叹号的插图。](media/deploy-my-service-image4.png) <strong>活动尚未完成，出现黄色 () ：</strong> 活动尚未完成，必须按计划更新为"是"或"否"。</li>
   - ![红色 X 的图示，指示否。](media/deploy-my-service-image5.png) <strong>没有 (红色) ：</strong> 活动因问题无法完成，必须携带到项目状态会议。</li></ul>

6. 状态在每个部分中汇总，分区标题的格式设置为这些状态指示器之一。 **每周状态** 也会自动更新。

![Playbook 中每周状态汇总的屏幕截图。](media/deploy-my-service-image6.png "Playbook 中每周状态汇总的屏幕截图")

> [!TIP]
> 针对你拥有的所有位置重复上述步骤。

> [!IMPORTANT]
> 某些步骤可能不适用于所有位置和网站。 如果特定活动与网站不相关，则必须选择" **不适用于此** 活动"。 **不要删除** playbook 中的任何行;如果这样做，状态汇总公式将不起作用。<br/><br/>
请注意可能需要比计划的时间更多的活动，例如数字移植和采购活动。 这些活动可能会对站点部署时间线产生负面影响。 请务必每周查看和更新活动列表和相关日程表，并出席指导委员会会议，确保利益干系人[](./envision-steering-committee-complete-guide.md)了解每个网站的状态以及任何可能与部署计划偏差的情况。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定是否需要站点启用 Playbook 进行部署。</li><li>确定谁将负责为要部署的每一个Microsoft Teams自定义网站启用 Playbook。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下载网站启用 Playbook。</a></li><li>为第一个网站自定义网站启用 Playbook。</li><li>根据需要对其他网站重复上述步骤。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->