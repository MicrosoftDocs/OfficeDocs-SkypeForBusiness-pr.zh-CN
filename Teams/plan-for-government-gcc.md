---
title: Microsoft 365政府 - GCC部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 指导 IT 专业人员推动Microsoft 365受美国政府法规限制的实体中的部署
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117830"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>规划Microsoft 365政府 - GCC部署

本指南适用于在美国联邦、州、地方、部落或政府实体或其他处理受政府法规和要求（使用 Microsoft 365 政府版 - GCC）适合满足这些要求的实体中部署 Microsoft 365 的 IT 专业人员。 2020 年 3 月 26 日新版：不要错过可下载的快速[入门](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)指南GCC。

> [!IMPORTANT]
> Microsoft Teams由于 COVID-19 的 corona (，在线呼叫和音频/视频会议) 高峰。<br/>
> 
>为了应对呼叫的前所未有的增加，为了确保连续性和可用性，Microsoft 允许 Microsoft Teams GCC 音频/视频服务器在我们的商业数据中心以及政府数据中心利用处理能力。<br/>
> 
>这些音频/视频服务器驻留在美国Microsoft Azure FedRAMP 高认证边界服务器内，不存储任何客户内容。 但是，这些服务器正在处理呼叫和会议的音频和视频，并在此过渡期间在我们的商业人员下操作。<br/>
> 
>合格、经筛选的人员通过查看这些服务器的任何交互式登录来监视这些服务器，以可能访问客户数据。 合格人员GCC访问客户内容的要求。 有关筛选要求的详细信息，请参阅GCC[说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。<br/>
> 
>感谢你的支持，因为我们采取一些措施来确保我们的服务在这些特殊时刻保持可用和可靠。<br/>


> [!NOTE]
> 如果你的组织已满足 Microsoft 365 政府 - GCC 资格要求，并且已申请并接受该计划，则你可以跳过步骤 1 和 2 并直接转到步骤 3。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>第 1 步 确定组织是否需要Microsoft 365政府 - GCC并满足资格要求。 

Microsoft 365 政府 - GCC 环境符合美国政府对云服务（包括 FedRAMP 中等）的要求，以及适用于犯罪和联邦税务信息系统的要求 (CJI 和 FTI 数据类型) 。

除了享受组织的特性和功能Microsoft 365，组织还受益于政府 - Microsoft 365独有的GCC：

-   组织的客户内容在逻辑上与 Microsoft 商业Microsoft 365内容分开。
-   组织的客户内容存储在美国。
-   对组织的客户内容的访问仅限于已筛选的 Microsoft 人员。
-   Microsoft 365政府 - GCC符合美国公共服务部门客户所需的认证和认证。

有关美国政府 - 美国政府Microsoft 365产品/服务GCC，请参阅政府Microsoft 365计划，[包括](https://products.office.com/government/compare-office-365-government-plans)[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。

本[Microsoft 365美国政府](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)服务说明介绍了平台的好处，其中心内容是满足美国内部的合规性要求。

> [!Tip]
> 你可能希望将服务说明中的信息表转移到 Excel 工作簿并添加两列：与我的组织 **Y/N** 相关和满足我的组织 **Y/N 的需求**。 然后，可以与同事一起查看此列表，确认此服务满足组织的需求。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定Microsoft 365政府 - GCC是否适合组织。</li><li>确认组织满足资格要求。</li></ul> |

> [!Note]
> Microsoft 365政府 - GCC仅适用于美国。 非美国政府客户可以从多个政府[Microsoft 365中选择](https://products.office.com/en/government/compare-office-365-government-plans)。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>第 2 步 申请Microsoft 365政府 - GCC

确定此服务适合你的组织后，请在此处 [开始申请此服务的过程](https://products.office.com/government/eligibility-validation)。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>第 3 步 了解Microsoft 365政府 - GCC默认设置。

建议在修改管理员和安全设置之前仔细查看这些设置[](enable-features-office-365.md)，并考虑对合规性的影响，然后再对默认安全设置进行更改。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是否要修改任何默认的政府Microsoft 365 - GCC安全设置，以首先了解可能做出的任何更改的影响。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>第 4 步 了解默认情况下哪些功能当前不可用或已禁用。

为了适应政府云客户的要求，Microsoft 365政府 - GCC计划Enterprise差异。 请参阅下表，了解哪些功能可用。

[Microsoft Teams服务说明](/office365/servicedescriptions/teams-service-description)

> [!Note]
> 在云中完全GCC工作负荷后，当所有其他集成工作Teams，这些工作负荷将在云中可用。


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定Teams功能集是否满足组织的需求。</li></ul> |

## <a name="step-5-plan-for-governance"></a>第 5 步 规划治理

确定监管要求以及如何满足这些要求。 有关详细信息[，请转到规划](plan-teams-governance.md)Teams治理。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>按照在管理中规划治理中的准则，确定[并](plan-teams-governance.md)记录Teams。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>第 6 步 部署Teams进行协作

在加入政府 - Microsoft 365后，GCC遵循如何推出 Microsoft Teams[中概述的建议部署Microsoft Teams。](./deploy-overview.md) 请务必与采用和更改管理团队和Teams合作。

还可以与 [FastTrack 或](https://www.microsoft.com/fasttrack) 所选合作伙伴合作来载入服务。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>第 7 步 为Teams和语音部署语音

这也是与更广泛的利益干系人Teams一起开始规划推出会议和云语音[功能的一个不错时间](./cloud-voice-landing-page.md)。