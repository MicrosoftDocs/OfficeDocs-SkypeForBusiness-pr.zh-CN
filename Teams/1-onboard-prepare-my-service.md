---
title: 准备部署 Microsoft 小组云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 使用板载清单为小组准备 Office 365 和配置团队核心功能，网络，和云语音工作负载。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e4b6e690450b8ec81209a0244769444ee2d30d
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="prepare-my-service"></a>准备我的服务

这篇文章概括介绍了准备云语音服务为您的组织的要求。 正确地做好准备，您可以确保您已经准备好提供语音功能为您的组织的云。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>针对 Microsoft 小组语音工作负载的服务清单

下列清单将逐步实现与 Microsoft 小组中调用计划功能的音频会议和电话系统的步骤。

*  [Office 365 准备团队](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [配置团队核心能力](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [配置网络](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [在团队中配置云语音工作负载](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

任务和这些检查表中的活动是应用于每个部署的云语音功能与团队的核心"待办事项"项目。 您可以自定义要包含的活动和特定于自己团队之旅的任务的清单。

>[!NOTE]
>本指南重点介绍仅调用计划和音频会议电话系统。 如果您是初次接触小组，检查[Microsoft 小组概述](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。 规划团队部署的一般准则，请参见[Microsoft 小组规划指南](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams)。

使用提供的检查表来跟踪状态的每个单独的活动和任务，并确保没有跳过任何重要的步骤。 每个活动都包括所需的操作，并参考其他信息可用来完成该活动的详细的说明。

但我们建议您按照顺序清单，准确的顺序将取决于您的部署和配置的范围和复杂环境中。 他们正在组织以支持"全新"团队部署 （一个没有以前 Skype 业务联机状态） 或从 Skype 的在线业务迁移到团队。 如果您正在从 Skype 的在线业务迁移内容，您可能已经完成一些这样的活动，并可以忽略它们现在。

后服务用户在每个站点的基础上，我们强烈建议您为这些检查表的补充指南使用[站点支持行动手册 （手册） 的声音](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)。

>[!NOTE]
>大多数配置设置共有之间团队和 Skype 的在线业务。 Office 365 Skype 业务管理中心的用于配置这些设置。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责监督服务清单的完成？</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>下载的服务清单。</li><li>通过板载的核对清单项逐步根据您的组织部署计划而工作。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>继续服务

在完成此清单后，将成功添加语音功能为您的团队部署。

作为下一步，使用[语音 （手册） 的网站支持行动手册](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)帮助您板载在每个站点上，您的用户，并帮助确保您规划和执行特定于站点的重要活动。

-   可以通过在站点首展计划

-   建立服务管理流程

-   执行测试和修正

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>在团队中测试云语音工作负载

已经定义和记录您的团队云语音业务成功和技术实施计划构想阶段的一部分，并采取在管理中心所需的配置后下, 一步是验证您的组织通过特征、 功能性和易用性满足的期望和要求。 试验或最终部署在生产环境中部署之前，您应该执行此验证步骤。

您可以利用业务成功计划构想阶段，作为确定活动、 期望、 特性/功能的测试用例和总体范围的测试阶段进行评估的基础定义。

## <a name="define-your-testing-approach"></a>定义测试方法

在最简单的形式，测试方法基于作用域中的用户在满足音频会议或电话系统的功能功能调用计划服务和开发测试计划，验证功能要求您审阅。 以下是一个示例测试计划板载音频会议实施的阶段。

| 音频会议功能测试 | 结果摘要 | 附加注释 |
|------------|-----------------|------------------|
| 计划特别小组会议，包含音频会议拨入信息 | 通过/失败   | 待定 |
| 用于电话拨入从 PSTN 会议音频会议提供的拨号信息 | 通过/失败 | 待定 |
| 通过 PSTN 拨出其他人加入现有会议 | 通过/失败 | 待定 |


| 通过调用计划功能的电话系统可供测试 | 结果摘要 | 附加注释 |
|----------------------------------------------------|-----------------|------------------|
| 进行到 PSTN 呼叫 PSTN 拨号       | 通过/失败       | 待定 |
| 拨入您从外部行 （移动，固定） 的 PSTN 号码接收 PSTN 呼叫 | 通过/失败 | 待定|
|将从一组用户 PSTN 呼叫转接到另一个 | 通过/失败 | 待定 |


>[!TIP]
>为了帮助作为起始点的测试用例创建，请参阅音频会议用户指南可在[团队会议和调用](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings)的列表。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>为团队设置了云语音工作负载

现在，您已经定义了测试方法下, 一步配置您的服务环境和用户小组云语音功能的范围内。 有关其他信息，请参阅[音频会议技术规划](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing)和[设置音频会议的 Skype 业务和 Microsoft 小组](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)以及[技术系统规划的电话与调用计划](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans)和[集Skype 的通话方案，为业务和 Microsoft 小组](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a>执行测试计划

在配置用户和音频会议服务环境后，测试的最后一步包括重点放在功能验证执行的测试计划。 

**音频会议系统必备组件和用户和站点的假设测试范围内：**

-   业务案例定义用于音频会议服务已完成。

-   授权所需的音频会议可用且已分配。

-   已标识组织站点和用户组的列表。

-   已标识和配置的专用和共享音频会议拨入号码与语言首选项的列表。

-   [通信片尾](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已经为您的组织设置。

-   音频会议会议网桥的设置已被标识和配置 （PIN 长度、 入口/出口通知，启用通知首选项）。

-   租户会议策略，拨号计划设置支持音频会议拨出方案已确定，配置，和应用。

-   已标识和配置音频会议法规遵从性要求。

**电话系统调用计划测试在作用域中的系统必备组件和用户和站点的假设：**

-   与调用计划服务的电话系统的业务使用案例定义已完成。

-   授权与调用计划的电话系统所需要的是可用且已分配。

-   已标识组织站点和用户组的列表。

-   要分配给用户的电话号码已获得或移植到 Microsoft 和租户门户中可用。

-   [通信片尾](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)（如果需要） 已经为您的组织设置。

-   租户用户策略和拨号计划与调用计划方案支持电话系统的设置有标识，配置，和应用。

-   已标识和配置电话系统调用计划法规遵从性要求。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>确定要部署的音频会议功能功能 （服务决策）。</li><li>确定用户的音频会议的功能要求。</li><li>确定音频会议服务配置要求。</li><li>决定哪些调用计划功能功能的电话系统将部署 （服务决策）。</li><li>确定用户调用计划与电话系统的功能要求。</li><li>标识服务调用计划与电话系统的配置要求。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>开发并记录您的测试计划方法。</li><li>准备您的服务环境和音频会议功能的作用域中的用户。</li><li>准备您的服务环境和调用计划功能的电话系统范围内的用户。</li><li>执行您想要启用音频会议功能的测试验证。</li><li>执行测试验证您想要启用的调用计划功能的电话系统。</li><li>任何测试失败，确认您的配置是否正确，检查社区的文章，以及 — — 如果需要 — — 引发支持案例。</li></ul></td></tr>
</table>


有关如何执行测试的团队中的音频会议的更多详细的指南，请参阅 [详细测试指南对于音频会议] (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing)。

有关如何执行测试的电话系统调用计划在团队中的其他详细指导，请参阅[详细测试电话系统指南](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System)。

<!--ENDOFSECTION-->