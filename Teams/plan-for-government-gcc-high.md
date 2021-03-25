---
title: Microsoft 365 政府版 - GCC 高部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 指导 IT 专业人员在处理受美国政府法规限制的数据的实体中驱动 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5533b6d5c2e08cb79ec8dd2052d761d86546b05
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117840"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>规划 Office 365 政府版 - GCC 高部署

本指南适用于推动 Office 365 在美国联邦政府实体或处理受政府法规和要求（使用 Office 365 政府版 - GCC High）满足这些要求的其他实体中的 Office 365 部署 IT 专业人员。

> [!NOTE]
> 如果您的组织已满足 Office 365 政府版 - GCC 高资格要求，并且已申请并接受该计划，您可以跳过步骤 1 和 2 并直接转到步骤 3。

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>第 1 步 确定组织是否需要 Office 365 政府版 - GCC High 并满足资格要求。 

Office 365 政府版 - GCC High 环境符合美国政府对云服务的要求。 除了享受 Office 365 的功能外，组织还受益于 Office 365 政府版独有的以下功能 – GCC High：

- 组织的客户内容在逻辑上与 Microsoft 商业版 Office 365 服务中的客户内容分开。
- 组织的客户内容存储在美国。
- 对组织的客户内容的访问仅限于已筛选的 Microsoft 人员。
- Office 365 政府版 – GCC High 符合美国公共服务部门客户所需的认证和认证。

有关 Office 365 政府版 - GCC High 产品/服务（适用于美国政府客户）在 [Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)版计划（包括 [资格要求）中查找详细信息](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。

[Office 365 美国政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)版服务说明介绍了平台的好处，其中心内容是满足美国内部的合规性要求。


> [!Tip]
> 您可能希望将服务说明中的信息表转移到 Excel 工作簿并添加两列：与我的组织 **Y/N** 相关和满足我的组织 **Y/N 的需求**。 然后，可以与同事一起查看此列表，确认此服务满足组织的需求。


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Office 365 政府版 - GCC High 是否适合组织。</li><li>确认组织满足资格要求。</li></ul> |

> [!Note]
> Office 365 政府版 - GCC High 仅在美国可用。 非美国政府版客户可以从多个 [Office 365 政府版计划中选择](https://products.office.com/en/government/compare-office-365-government-plans)。

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>第 2 步 申请 Office 365 政府版 - GCC High

确定此服务适合你的组织后，请开始 [申请此服务的过程](https://products.office.com/government/eligibility-validation)。


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>第 3 步 了解 Office 365 政府版 - GCC 高默认安全设置。

建议在修改管理员和安全设置之前仔细查看这些设置[](enable-features-office-365.md)，并考虑对合规性的影响，然后再对默认安全设置进行更改。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定是否需要修改任何默认的 Office 365 政府版 - GCC 高安全设置，并首先了解可能进行的任何更改的影响。</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>第 4 步 了解 Office 365 政府版 - GCC High 中当前提供哪些 Teams 功能

为了适应政府云客户的要求，Office 365 政府版中的 Teams - GCC High 和企业版计划中的 Teams 之间存在一些差异。 请参阅下表，了解哪些功能可用。

[Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>第 5 步 规划治理

确定监管要求以及如何满足这些要求。 有关详细信息 [，请转到规划 Teams](plan-teams-governance.md) 中的治理。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|决策点 |<ul><li>按照在 Teams 中规划治理中的准则，确定 [并记录治理要求](plan-teams-governance.md)。 </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>第 6 步 部署 Teams 进行协作

加入 Office 365 政府版 - GCC High 后，请按照如何推出 Microsoft Teams 中概述的建议 [部署路径操作](./deploy-overview.md)。 请务必与采用和更改管理团队以及 Teams 冠军互动。

还可以与 [FastTrack 或](https://www.microsoft.com/fasttrack) 所选合作伙伴合作来载入服务。

> [!NOTE]
> 尚不支持用于 GCCH 环境的 Mac Teams 客户端。