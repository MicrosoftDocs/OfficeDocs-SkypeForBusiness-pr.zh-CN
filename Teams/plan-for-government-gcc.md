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
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1b97e82edd97079c1e4615e5bb7fcf4a1eb2fea
ms.sourcegitcommit: b6eb22e96be5fb18984f1dd05e4eb8f2cfc032f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2020
ms.locfileid: "42968657"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>规划 Microsoft 365 政府版-GCC 部署

本指南适用于面向美国联邦、州、本地、tribal 或 territorial 政府实体或其他实体中的 Office 365 部署的 IT 专业人员，这些实体或其他实体处理受政府管理法规和要求制约的数据，其中使用 Microsoft365政府-GCC 适用于满足这些要求。

> [!IMPORTANT]
> 由于 coronavirus （COVID-19） pandemic，Microsoft 团队在在线通话和音频/视频会议方面遇到了极大的高峰。<br/>
> 
>为响应更空前的通话增加，并确保连续性和可用性，Microsoft 允许 Microsoft 团队拥有的音频/视频服务器利用我们的商业数据中心中的处理能力和我们的政府数据中心。<br/>
> 
>这些音频/视频服务器驻留在 Microsoft Azure FedRAMP 中的 Microsoft Azure 高资格鉴定边界服务器，并且不存储任何客户内容。 但是，这些服务器正在处理通话和会议的音频和视频，并在此期间内由我们的商业员工进行操作。<br/>
> 
>经确认，被筛选的人员正在监视这些服务器，以便通过查看这些服务器的交互式登录项来对客户数据进行潜在访问。 合格的人员在访问客户内容方面满足了 GCC 的要求。 有关筛选要求的详细信息，请参阅[GCC 服务说明](Office365-ServiceDescriptions\office-365-platform-service-description\office-365-us-government\gcc.md)。<br/>
> 
>感谢您的支持，因为我们采取措施来确保我们的服务在这些特别时间内保持可用且可靠。<br/>


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
| Base64 | 登录 | 在线 |
| | 状态 | 在线 |
| | 统一状态（Skype for Business 和团队统一） | 在线 |
| 活动 | 源 | 在线 |
|  | 我的活动 | 在线 |
| 聊天 | 交谈 | 在线 |
| | 文件 | 在线 |
| | 组织结构图 | 在线 |
| | 活动 | 在线 |
| | 互操作（1:1 团队-Skype for Business 聊天） | 在线 |
| Teams | 频道消息 | 在线 |
| | 信道文件 | 在线 |
| | OneNote 选项卡 | 在政府待办事项中 |
| | 通过电子邮件发送频道 | 不可用 |
| | 添加成员 | 在线 |
| | 来宾访问权限 | 在线 |
| 会议 | 安排会议 | 在线 |
| | 加入会议 | 在线 |
| | VoIP 会议 | 在线 |
| | 桌面共享 | 在线 |
| | 在共享中提供和获取控制权 | 在线 |
| | 从会议室连接 | 在线 |
| | 匿名联接 | 在线 |
| | 云录制 | 在线 |
| | 会议笔记 | 在线 |
| | 实时事件 | 在线 |
| | 联盟会议 | 在线 |
| | Surface Hub 支持 | 在线 |
| 呼叫 | 联系人 | 在线 |
| | 信息 | 在线 |
| | 语音邮件 | 可用 |
| | VoIP 呼叫 | 在线 |
| | Skype for Business-团队通话 | 可用 |
| | 通话套餐 | 在线 |
| | 音频会议（通过允许会议参与者通过 PSTN 加入） | 在线 |
| | Microsoft Phone 系统直接路由 | 在线 |
| | PSTN 呼叫者的大厅 | 在线 |
| | 通话队列 | 在线 |
| | 老板和代理人支持 | 在线 |
| | 咨询和安全转移 | 在线 |
| | 请勿打扰突破 | 在线 |
| | 独特震铃 | 在线 |
| | 1:1 与团队、Skype for Business 和 PSTN 参与者进行群组通话升级 | 在线 |
| | 转发到组 | 在线 |
| | 转接至 PSTN 呼叫 | 在线 |
| | 紧急呼叫呼叫计划 | 在线 |
| | 对现有认证的 SIP 电话的支持 | 在线 |
| | USB HID | 在线 |
| | 用于通话和会议的电子数据展示 | 在线 |
| | 组织自动助理 | 在线 |
| | Skype 消费者-团队通话支持 | 在线 |
| 文件 | 近来 | 在线 |
| | Microsoft Teams | 在线 |
| 应用商店 | 应用商店 | 在线 |
| 搜索 | 彩信 | 在线 |
| | 人员 | 在线 |
| | 文件 | 在线 |
| | 斜杠命令 | 在线 |
| 符合 | 合规性内容搜索 | 在线 |
| | 保存 | 在线 |
| | 审核日志搜索 | 在线 |
| | 法律封存 | 在线 |
| | 电子数据展示 | 在线 |

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

