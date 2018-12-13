---
title: 规划 Microsoft 365 政府-GCC 部署的 Microsoft 团队
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 12/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 面向 IT 专业人员为中处理数据受美国政府法规的实体的驱动器 Office 365 部署指南
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf9571a52d99e9993161b6de99a190bc9b675f78
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240907"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Microsoft 365 政府版-GCC 部署规划

本指南为 IT 专业人员带来了美国联邦、 状态、 本地、 经验，或地域政府实体或其他处理受及政府法规要求约束的数据的实体中的 Office 365 部署其中使用 Microsoft365 政府-GCC 适合满足这些要求。

> [!NOTE]
> 如果您的组织已满足 Microsoft 365 政府-GCC 资格要求和应用于并被接受到程序，您可以跳过步骤 1 到 4，直接转到步骤 5 以开始部署。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>第 1 步 确定您的组织是否需要 Microsoft 365 政府-GCC，并且符合资格要求。 

Microsoft 365 政府-GCC 环境提供符合美国的云服务，包括 FedRAMP 适度和刑事审判和联邦税费信息系统 （CJI 和 FTI 数据类型） 要求的政府要求。

除了享受的特性和功能的 Office 365，组织受益于对 Microsoft 365 政府-GCC 是唯一的以下功能：

-   贵组织的客户内容逻辑分离从 microsoft 商业的 Office 365 服务中的客户内容中。
-   美国境内存储贵组织的客户内容。
-   贵组织的客户内容的访问仅限于屏蔽 Microsoft 人员。
-   Microsoft 365 政府-GCC 遵守认证和资格鉴定所需的美国公共部门客户。

您可以找到有关 Microsoft 365 政府-GCC 提供在[Office 365 政府计划](https://products.office.com/government/compare-office-365-government-plans)，包括[资格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)美国政府客户的详细信息。

[Office 365 美国政府服务说明](https://technet.microsoft.com/library/mt774581.aspx)介绍平台的优点，围绕会议美国境内的合规性要求。

> [!Tip]
> 您可能希望将服务说明中的信息的转移到 Excel 工作簿和添加两个列：**相关的我的组织是/否**和**满足 Y/N 我的组织的需求**。 然后您可以查看此列表与同事以确认此服务满足您组织的需求。


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Microsoft 365 政府-GCC 是否适合您的组织。</li><li>确认您的组织满足资格要求。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>了解由 Microsoft 365 政府-GCC 提供的功能。</li></ul>|

> [!Note]
> Microsoft 365 政府-GCC 仅在美国可用。 非 – 美国政府客户可以选择从[Office 365 政府计划](https://products.office.com/en/government/compare-office-365-government-plans)数。

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>第 2 步 了解哪些功能目前不可用或默认为禁用。 

若要容纳政府云客户的要求，有一些区别 Microsoft 365 政府-GCC，企业计划。 请参阅下表可查看可用的功能。

|                             | 功能                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| 基本 | 登录 | 有空 |
| | 状态 | 有空 |
| | 统一的状态 (Skype 业务和团队统一) | 政府待办事项上 |
| 活动 | 源 | 有空 |
|  | 我的活动 | 有空 |
| Chat | 对话 | 有空 |
| | 文件 | 有空 |
| | 组织结构图 | 有空 |
| | 活动 | 有空 |
| | 互操作 (1:1 团队-Skype 对业务聊天) | 政府待办事项上 |
| Teams | 频道消息 | 有空 |
| | 通道文件 | 有空 |
| | OneNote 选项卡 | 政府待办事项上 |
| | 电子邮件通道 | 不可用 |
| | 添加成员 | 有空 |
| | 来宾访问 | 有空 |
| 会议 | 安排会议 | 有空 |
| | 加入会议 | 有空 |
| | VoIP 会议 | 有空 |
| | 桌面共享 | 有空 |
| | 在共享授予 and 获得控制权 | 有空 |
| | 从会议室连接 | 有空 |
| | 匿名加入 | 有空 |
| | 云录制 | 政府待办事项上 |
| | 会议笔记 | 有空 |
| | 广播的会议 | 政府待办事项上 |
| | 联盟的会议 | 有空 |
| | 曲面集线器支持 （预览） | 有空 |
| 呼叫 | 联系人 | 有空 |
| | 历史记录 | 可用 |
| | 语音邮件 | 可用 |
| | VoIP 呼叫 | 有空 |
| | Skype for Business 的团队呼叫 | 可用 |
| | 通话套餐 | 有空 |
| | 音频会议 （通过允许会议参与者通过 PSTN 加入） | 有空 |
| | Microsoft 直接路由的电话系统 | 有空 |
| | PSTN 呼叫者会议厅 | 有空 |
| | 呼叫队列 | 有空 |
| | 经理和代理人支持 | 有空 |
| | 咨询和安全传输 | 有空 |
| | 请勿打扰突破性 | 有空 |
| | 特殊铃声 | 有空 |
| | 1： 与团队业务的 Skype 组呼叫升级到 1 和 PSTN 参与者 | 有空 |
| | 转发到组 | 有空 |
| | 转接到 PSTN 呼叫 | 有空 |
| | 紧急呼叫-调用计划 | 有空 |
| | 对现有认证的 SIP 电话支持 | 有空 |
| | 隐藏的 USB | 有空 |
| | 对呼叫和会议的电子数据展示 | 有空 |
| | 组织自动助理 | 有空 |
| | Skype 消费者-团队呼叫支持 | 有空 |
| 文件 | 最新 | 有空 |
| | Microsoft Teams | 有空 |
| 存储 | 应用程序商店 | 政府待办事项上 |
| 搜索 | 邮件 | 有空 |
| | 人员 | 有空 |
| | 文件 | 有空 |
| | 斜杠命令 | 有空 |
| 合规性 | 合规性内容搜索 | 有空 |
| | 保留 | 有空 |
| | 审核日志搜索 | 有空 |
| | 合法保留 | 有空 |
| | 电子数据展示 | 有空 |



|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定 Microsoft 365 政府-GCC 功能集是否能满足您组织的需求。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>了解默认安全设置。</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>第 3 步 了解 Microsoft 365 政府-GCC 默认安全设置。

我们建议您执行时间仔细检查您的[管理和安全设置](enable-features-office-365.md)，然后再对其进行修改和对默认安全设置进行任何更改之前，请考虑影响合规性。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是否将修改任何默认 Microsoft 365 政府-GCC 安全设置，首先了解的任何更改影响的解决您可能会使。</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>第 4 步 适用于 Microsoft 365 政府-GCC

无决定此服务适合您的组织，启动[此服务此处应用](https://products.office.com/government/eligibility-validation)的过程。

## <a name="step-5-plan-for-governance"></a>第 5 步 规划调控

确定调控和如何满足这些要求。 有关详细信息，请转到[团队中的治理规划](plan-teams-governance.md)。

## <a name="step-6-deploy-teams-for-collaboration"></a>第 6 步 部署团队协作

您已向 Microsoft 365 政府-GCC，onboarded 后，您可以按照使用[FastTrack](https://fasttrack.microsoft.com/fasttrack-faq)和您选择的合作伙伴，为板载到服务的标准的部署方法。

当您准备好时，到[启用通过团队和通道组织内的协作](teams-overview.md)部署团队。 请务必与您应用和变更管理团队或团队拥护者。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>第 7 步 会议和语音部署团队

这也是使用与您更多的利益干系人组团队启动规划推出会议和[云语音功能](cloud-voice-deployment.md)的绝佳时间。

