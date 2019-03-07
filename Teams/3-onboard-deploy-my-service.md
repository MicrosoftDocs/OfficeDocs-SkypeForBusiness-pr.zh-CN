---
title: 部署 Microsoft 团队云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 05/16/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 下载站点启用设置方案规划您的团队推出和加速和优化用户应用，认知质量和满意度。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ce9b3f5a1d81728f0bff6951211453fb4aa2ef4
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458993"
---
# <a name="deploy-my-service"></a>部署我服务

本文概述了正确部署云语音服务的要求。 按照部署云语音服务，您可以确保的说明性指导您成功帐户为满足所有要求并提供可重复的结果。

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>网站启用设置方案的 Microsoft 团队语音工作负荷

使用此设置方案来帮助贵组织成功地规划和执行网站的网站基于推出 Microsoft 团队语音功能。

此设置方案包括所有所需的活动，建议时间线和链接到有关每个活动的相应指南涵盖的端到端指导，帮助确保成功团队语音部署给定网站，侧重于重要的因素向用户。

通过完成此设置方案中的活动，您的组织可以：

-   有效地规划和安排团队推出。

-   加快和优化用户应用。

-   降低支持需求并提高用户满意度。

> [!NOTE]
> 本文和相关设置方案不目的介绍每个技术的配置步骤所需的服务启用或提供拨号音到特定站点。 相反，它们重点关注活动和轻松地向板载用户推荐的任务，并使其开始使用通过快速地平滑过渡与高应用率，同时最小化的支持要求的团队语音工作负荷。 有关如何配置团队语音环境，最佳的技术指导信息，请参阅[配置团队语音工作负荷](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)，[配置团队中直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)，入职培训清单[团队的核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)，[网络团队](onboarding-checklist-configure-networking.md)，和[启用 Office 365](onboarding-checklist-enable-office-365.md)。

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>设置方案重点领域

设置方案的重点是解决影响用户的角度看团队语音部署的因素。 活动和任务分为以下领域：

-   服务准备的验证
    - 音频会议
    - 通话套餐
    - 直接路由

-   用户启用

-   终结点

-   使用率和质量

-   采用

[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)是 Microsoft Excel 工作簿。 每个五个焦点区域是单独的工作表的工作簿中，每个部署任务和活动拖动到一个这些工作表被分组。

![设置方案的屏幕截图](media/deploy-my-service-image1.png "设置方案的屏幕截图")

> [!NOTE]
> 您将在您的团队推出的范围内创建的每个站点设置方案的单独实例。

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>如何使用设置方案

无论的大小和位置的复杂性，启用每个站点需要规划任务和活动足够早期 — 和最佳顺序执行这些 — 之前、 升级期间和实际服务推出之后。 我们建议您执行以下步骤，如您规划和执行自己迁移到 Microsoft 团队语音。

1. 下载 Microsoft 团队语音[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)。

2. 创建一份的每个站点设置方案。

3. 在名为 **{SiteName 代码} 设置方案**工作表的选项卡上，与相关网站名称和/或站点代码替换 **{SiteName 代码}** 。

4. 输入**网站名称、 站点代码**，和**计划启动日期**，如下所示。 这是关键步骤中，因为它调整设置方案中的每个活动的建议的峰值。

   ![网站名称为纽约站点代码 NY01 和 20-Mar 18 计划的启动日期示例](media/deploy-my-service-image2.png "网站名称为纽约站点代码 NY01 和 20-Mar 18 计划的启动日期示例")

5. 查看每个活动和所需的操作，当您演练日程表更新状态。 状态表示图形，如下所示：
   <ul>
   <li>![绿色复选标记](media/deploy-my-service-image3.png) <strong>是、 或不适用 （绿色）：</strong>活动完成后，或不适用于此网站，并需要没有进一步的操作。</li>
   <li>![黄色感叹号](media/deploy-my-service-image4.png) <strong>活动未完成尚未 （黄色）：</strong>该活动不起作用，已完成，必须更新为是或否按其计划。</li>
   <li>![红色 X](media/deploy-my-service-image5.png) <strong>没有 （红色）：</strong>活动无法完成由于问题，必须执行到项目状态会议。</li></ul>

6. 状态成型内每个部分，并节标题格式之一的这些状态指示符。 **每周状态**也会自动更新。

![每周状态汇总中设置方案的屏幕截图](media/deploy-my-service-image6.png "每周状态汇总中设置方案的屏幕截图")

> [!TIP]
> 您具有的所有位置重复上述步骤。

> [!IMPORTANT]
> 某些步骤可能不是适用于所有位置和网站。 如果不与网站相关的特定活动，则必须选择**不适用于**此活动。 **不要删除**任何行中设置方案;如果这样做，状态汇总公式将不起作用。<br/><br/>
请注意，可能会更多时间比您计划，如号码移植活动和采购活动。 这些活动可以对网站部署时间线产生负面影响。 请务必查看和每周，更新活动列表和关联的日程表和他们出席[调控委员会会议](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide)以确保利益干系人了解每个站点和任何可能偏离的部署计划的状态。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>决定是否需要为您的部署网站启用设置方案。</li><li>决定谁将负责将部署每个网站自定义 Microsoft 团队网站启用设置方案。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">下载站点启用设置方案</a>。</li><li>自定义网站启用设置方案为您的第一个网站。</li><li>根据需要为其他网站重复。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->