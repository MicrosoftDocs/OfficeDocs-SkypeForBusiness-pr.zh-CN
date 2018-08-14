---
title: 规划 Microsoft 365 政府-GCC 部署的 Microsoft 团队
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 07/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: 面向 IT 专业人员为中处理数据受美国政府法规的实体的驱动器 Office 365 部署指南
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c54e553edb464dc094c45b4e9dd545827b625d3
ms.sourcegitcommit: 046cc4a880f3b6b5f912278483cf28fa25619b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "21600514"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 政府版-GCC 部署规划

本指南为 IT 专业人员带来了美国联邦、 状态、 本地、 经验，或地域政府实体或其他处理受及政府法规要求约束的数据的实体中的 Office 365 部署其中使用 Microsoft365 政府-GCC 适合满足这些要求。

> [!NOTE]
> 如果您的组织已满足 Microsoft 365 政府-GCC 资格要求和应用于并被接受到程序，您可以跳过步骤 1 到 4，直接转到步骤 5 以开始部署。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>步骤 1。 确定您的组织是否需要 Microsoft 365 政府-GCC，并且符合资格要求。 

Microsoft 365 政府-GCC 环境提供符合美国的云服务，包括 FedRAMP 适度和刑事审判和联邦税费信息系统 （CJI 和 FTI 数据类型） 要求的政府要求。

除了享受的特性和功能的 Office 365，组织受益于对 Microsoft 365 政府-GCC 是唯一的以下功能：

-   贵组织的客户内容逻辑分离从 microsoft 商业的 Office 365 服务中的客户内容中。
-   美国境内存储贵组织的客户内容。
-   贵组织的客户内容的访问仅限于屏蔽 Microsoft 人员。
-   Microsoft 365 政府-GCC 遵守认证和资格鉴定所需的美国公共部门客户。

您可以找到有关 Microsoft 365 政府-GCC 提供在[Office 365 政府计划](https://products.office.com/en-us/government/compare-office-365-government-plans)，包括[资格要求](https://products.office.com/en-us/government/compare-office-365-government-plans#EligibilityRequirements)美国政府客户的详细信息。

[Office 365 美国政府服务说明](https://technet.microsoft.com/en-us/library/mt774581.aspx)介绍平台的优点，围绕会议美国境内的合规性要求。

> [!Tip]
> 您可能希望将服务说明中的信息的转移到 Excel 工作簿和添加两个列：**相关的我的组织是/否**和**满足 Y/N 我的组织的需求**。 然后您可以查看此列表与同事以确认此服务满足您组织的需求。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Microsoft 365 政府-GCC 是否适合您的组织。</li><li>确认您的组织满足资格要求。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>下一步|<ul><li>了解由 Microsoft 365 政府-GCC 提供的功能。</li></ul>|

> [!Note]
> Microsoft 365 政府-GCC 仅在美国可用。 非 – 美国政府客户可以选择从[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)数。

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>步骤 2。 了解哪些功能目前不可用或默认为禁用。 

若要容纳政府云客户的要求，有一些区别 Microsoft 365 政府-GCC，企业计划。 下表中列出的功能不可用。

| 功能                     | 原因            |
|-----------------------------|-------------------|
| 呼叫和会议录音  | 记录是依赖于在 Microsoft 流，将在将来美国政府计划中可用。 |
| 应用       | 应用程序 （如自动程序、 选项卡，和连接器） 将不可用最初，但我们正在使其可为所有及其组件满足 FedRAMP 适度合规性栏。 |
| 电子邮件通道             | 政府计划中不支持当前功能体系结构。 |
| 统一的状态            | 我们为我们首先对此重要的功能的企业客户的完成工作。 它将可供政府客户将来。 |
| 电子邮件通知         | 美国政府计划中不支持当前功能体系结构。 若要使此功能可供美国政府计划客户将来正在进行工作。 |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Microsoft 365 政府-GCC 功能集是否能满足您组织的需求。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>下一步|<ul><li>了解默认安全设置。</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>步骤 3。 了解 Microsoft 365 政府-GCC 默认安全设置。

我们建议您执行时间仔细检查您的[管理和安全设置](enable-features-office-365.md)，然后再对其进行修改和对默认安全设置进行任何更改之前，请考虑影响合规性。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是否将修改任何默认 Microsoft 365 政府-GCC 安全设置，首先了解的任何更改影响的解决您可能会使。</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>步骤 4。 适用于 Microsoft 365 政府-GCC

无决定此服务适合您的组织，启动[此服务此处应用](https://products.office.com/en-us/government/eligibility-validation)的过程。

## <a name="step-5-deploy-teams-for-collaboration"></a>步骤 5。 部署团队协作

您已向 Microsoft 365 政府-GCC，onboarded 后，您可以按照使用[FastTrack](https://fasttrack.microsoft.com/fasttrack-faq)和您选择的合作伙伴，为板载到服务的标准的部署方法。

当您准备好时，到[启用通过团队和通道组织内的协作](teams-overview.md)部署团队。 请务必与您应用和变更管理团队或团队拥护者。

## <a name="step-6-deploy-teams-for-meetings-and-voice"></a>步骤 6。 会议和语音部署团队

这也是使用与您更多的利益干系人组团队启动规划推出会议和[云语音功能](cloud-voice-deployment.md)的绝佳时间。

