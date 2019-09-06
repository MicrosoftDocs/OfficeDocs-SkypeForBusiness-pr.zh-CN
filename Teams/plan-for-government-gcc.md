---
title: Microsoft 365 政府版规划 - GCC 部署 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT 专业人士在处理由美国政府法规制约的数据的实体中驱动 Office 365 部署的指南
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a167c8a6df85b5d3d861f42ce40f67e845709a77
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767119"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>规划 Microsoft 365 政府版-GCC 部署

本指南适用于面向美国联邦、州、本地、tribal 或 territorial 政府实体或其他实体中的 Office 365 部署的 IT 专业人员，这些实体或其他实体处理受政府管理法规和要求制约的数据，其中使用 Microsoft365政府-GCC 适用于满足这些要求。

> [!NOTE]
> 如果您的组织已满足 Microsoft 365 政府-GCC 资格要求，并已接受并接受该计划，则可以跳过步骤1和步骤2，直接转到步骤3。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>第 1 步 确定你的组织是否需要 Microsoft 365 政府-GCC 并满足资格要求。 

Microsoft 365 政府版-GCC 环境为云服务（包括 FedRAMP 中等）和针对犯罪分子和联邦税务信息系统（CJI 和 FTI 数据类型）的要求遵守美国政府规定。

除了享受 Office 365 的功能和功能之外，组织还受益于 Microsoft 365 政府-GCC 所特有的以下功能：

-   你的组织的客户内容在 Microsoft 的商业版 Office 365 服务中与客户内容逻辑隔离。
-   您的组织的客户内容存储在美国。
-   对您的组织的客户内容的访问权限受到限制，无法对 Microsoft 人员进行筛选。
-   Microsoft 365 政府版-GCC 遵循美国公共事业部门客户所需的认证和 accreditations。

您可以在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)（包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有关 Microsoft 365 政府版（美国）政府客户的详细信息。

[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍了平台的优势，这些优势在美国的会议合规性要求的中心。

> [!Tip]
> 你可能想要将服务说明中的信息表传输到 Excel 工作簿中，并添加两列：**与我的组织进行相关**并**满足组织 y/n 的需要**。 然后，您可以与同事一起查看此列表，以确认此服务是否满足组织的需求。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Microsoft 365 政府版-GCC 是否适合您的组织。</li><li>确认您的组织满足资格要求。</li></ul> |

> [!Note]
> Microsoft 365 政府版-GCC 仅适用于美国。 非美国政府客户可以从多个[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)中进行选择。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>第 2 步 适用于 Microsoft 365 政府版-GCC

如果确定此服务适合你的组织，请在[此处开始应用此服务](https://products.office.com/government/eligibility-validation)的过程。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>第 3 步 了解 Microsoft 365 政府版-GCC 默认安全设置。

我们建议你在修改你的管理员和安全设置之前认真检查你的[管理员和安全设置](enable-features-office-365.md)，并考虑对默认安全设置进行任何更改之前对合规性产生的影响。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定你是否要修改任何默认的 Microsoft 365 政府-GCC 安全设置，首先要了解你可能做出的任何更改的影响。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>第 4 步 了解默认情况下当前不可用或已禁用的功能。 

为了满足政府云客户的要求，Microsoft 365 政府版和企业版计划之间存在一些差异。 请参考下表，查看哪些功能可用。

|                             | 功能                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| Base64 | 登录 | 有空 |
| | 状态 | 有空 |
| | 统一状态（Skype for Business 和团队统一） | 有空 |
| 活动 | 源 | 有空 |
|  | 我的活动 | 有空 |
| 聊天 | 交谈 | 有空 |
| | 文件 | 有空 |
| | 组织结构图 | 有空 |
| | 活动 | 有空 |
| | 互操作（1:1 团队-Skype for Business 聊天） | 有空 |
| 团队 | 频道消息 | 有空 |
| | 信道文件 | 有空 |
| | OneNote 选项卡 | 在政府待办事项中 |
| | 通过电子邮件发送频道 | 不可用 |
| | 添加成员 | 有空 |
| | 来宾访问权限 | 有空 |
| 会议 | 安排会议 | 有空 |
| | 加入会议 | 有空 |
| | VoIP 会议 | 有空 |
| | 桌面共享 | 有空 |
| | 在共享中提供和获取控制权 | 有空 |
| | 从会议室连接 | 有空 |
| | 匿名联接 | 有空 |
| | 云录制 | 有空 |
| | 会议笔记 | 有空 |
| | 实时事件 | 有空 |
| | 联盟会议 | 有空 |
| | Surface Hub 支持 | 不可用 |
| 呼叫 | 联系人 | 有空 |
| | 信息 | 有空 |
| | 语音邮件 | 可用 |
| | VoIP 呼叫 | 有空 |
| | Skype for Business-团队通话 | 可用 |
| | 通话套餐 | 有空 |
| | 音频会议（通过允许会议参与者通过 PSTN 加入） | 有空 |
| | Microsoft Phone 系统直接路由 | 有空 |
| | PSTN 呼叫者的大厅 | 有空 |
| | 通话队列 | 有空 |
| | 老板和代理人支持 | 有空 |
| | 咨询和安全转移 | 有空 |
| | 请勿打扰突破 | 有空 |
| | 独特震铃 | 有空 |
| | 1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级 | 有空 |
| | 转发到组 | 有空 |
| | 转接至 PSTN 呼叫 | 有空 |
| | 紧急呼叫呼叫计划 | 有空 |
| | 对现有认证的 SIP 电话的支持 | 有空 |
| | USB HID | 有空 |
| | 用于通话和会议的电子数据展示 | 有空 |
| | 组织自动助理 | 有空 |
| | Skype 消费者-团队通话支持 | 有空 |
| 文件 | 近来 | 有空 |
| | Microsoft Teams | 有空 |
| 储存 | 应用商店 | 在政府待办事项中 |
| 搜索 | 彩信 | 有空 |
| | 人员 | 有空 |
| | 文件 | 有空 |
| | 斜杠命令 | 有空 |
| 符合 | 合规性内容搜索 | 有空 |
| | 保存 | 有空 |
| | 审核日志搜索 | 有空 |
| | 法律封存 | 有空 |
| | 电子数据展示 | 有空 |

> [!Note]

> 当其他工作负荷在 GCC 云中完全可用时，它们将在所有其他集成工作完成后的团队中变为可用。


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定团队功能集是否满足组织的需求。</li></ul> |

## <a name="step-5-plan-for-governance"></a>第 5 步 规划管理

确定您的监管要求以及如何满足这些要求。 有关详细信息，请转到[团队中的管理计划](plan-teams-governance.md)。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>按照[规划团队中的管理](plan-teams-governance.md)指南，确定和记录您的管理要求。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>第 6 步 部署协作团队

在 onboarded 到 Microsoft 365 政府-GCC 后，请按照[如何部署 Microsoft 团队](How-to-roll-out-teams.md)中介绍的推荐部署途径进行操作。 请确保与你的采纳和更改管理团队和团队拥护人员联系。

您还可以与[FastTrack](https://www.microsoft.com/fasttrack)或您的选定合作伙伴进行服务。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>第 7 步 为会议和语音部署团队

这也是将团队与更大的风险承担者组配合使用来开始计划推出会议和[云语音功能](cloud-voice-deployment.md)的一个好时机。

