---
title: "Microsoft Teams 中的安全性和合规性概述"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "Microsoft Teams 中的安全性和合规性概述，包括审核和报告、合规性内容搜索以及电子数据展示等。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 376196b4f3d8479437eb4b4824c74574ae3012ce
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和合规性概述
======================================================

Microsoft Teams 建立在 Office 365 超大规模企业级云之上，提供我们的客户期望的高级安全性和合规性功能。

Teams 在上市时符合 Tier C 标准。 这包括以下标准：ISO 27001、ISO 27018、SSAE16 SOC 1 和 SOC 2、HIPAA 以及欧盟模型条款 (EUMC)。 在 Microsoft 合规性框架中，Microsoft 将 Office 365 应用和服务分类为四种类别。 每种类别均按特定的合规性承诺定义，Office 365 服务或相关的 Microsoft 服务必须履行这些承诺才能列在相应类别中。

默认情况下启用合规性类别 C 和 D 中的服务，它们有行业领先的合规性承诺。 类别 A 和 B 中的服务提供了针对整个组织开启或关闭这些服务的控制功能。 有关详细信息，请参阅[行业标准和规章的合规性框架](https://go.microsoft.com/fwlink/?linkid=855777)。 Teams 还支持云安全联盟合规性。

Teams 还强制执行团队范围和组织范围的双重身份验证、通过 Active Directory 进行单一登录以及对正在传输的数据和静态数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。

我们还增加了以下支持：审核日志搜索、针对频道、聊天和文件的电子数据展示和法定保留，以及通过 Microsoft Intune 进行移动应用管理。

这些工具位于 Office 365 安全性和合规性门户中，提供以下功能：

-   审核和报告

    -   审核日志搜索置于 Office 365 安全性和合规性中心中，进而可以通过提供审核日志数据对审核事件设置警报和/或进行报告，能够导出工作负荷特定或一般事件集以用于管理和调查，审核时间线无限制。 所有审核日志数据可用于在 Office 365 安全性和合规性中心中设置警报，以及用于筛选和报告以供进一步分析。

-   合规性内容搜索

    -   可以使用内容搜索通过丰富的筛选功能搜索 Teams，并可以将搜索结果导出到特定容器以用于合规性和诉讼活动。 在有无电子数据展示案例的情况下，均可执行此操作。

-   电子数据展示

    -   电子数据展示是为了回应法律诉讼或调查中提供文件的要求而找出、收集和生成电子方式存储的信息 (ESI) 的电子操作过程。

    -   功能包括对 Teams 数据进行案例管理、保留、搜索、分析和导出。 这些数据包括聊天、消息传递和文件数据。

    -   客户可以利用就地电子数据展示或[高级电子数据展示](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)。

    -   下表概括列出了这两者之间的差异：


| |就地电子数据展示  |高级电子数据展示  |
|---------|---------|---------|
|案例管理     |X        |X         |
|访问控制  |X         |X         |
|内容搜索     |X         | X        |
|保留   |X         | X        |
|导出     |X         |X         |
|重复项检测     |-         |X         |
|使用机器学习的相关性搜索    |-         |X         |
|非结构化数据分析      |-         |X         |


-   法定保留

    -   当 Teams 中的任何团队置于就地保留或诉讼保留时，将组邮箱置于保留状态。

    -   通常在电子数据展示案例的上下文中应用法定保留。

下图显示了 Teams 数据到 Exchange 和 SharePoint 的工作流。

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> 发现 Teams 内容的过程最长可能延迟 24 小时。

此外，Microsoft 正在考虑为 Teams 提供以下安全功能。 一旦可用，将提供有关客户如何利用这些功能的指导：

-   租户特定的保留策略

-   数据丢失防护 (DLP)

-   客户密码箱

-   权限管理


| | | |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织需要哪些安全性和合规性功能？ 贵组织是否有所需的许可证来满足安全性和合规性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |后续步骤         |在下面的表格中记录所需的安全性和合规性功能。         |

<a name="licensing"></a>许可
---------------

涉及到信息保护功能时，Office 365 订阅和关联的单独许可证将确定功能集。

|信息保护功能   |Office 365 商业协作版   |Office 365 商业高级版   |Office 365 企业版 E1   |Office 365 企业版 E3/E4   |Office 365 企业版 E5   |
|---|---|---|---|---|---|
|存档|-  |-   |-   |是   |是   |
|就地电子数据展示|-   |-   |-   |是   |是   |
|高级电子数据展示|-   |-   |-   |-   |是   |
|法定保留|-   |-   |-   |是   |是   |
|合规性内容搜索|- |- |- |是 |是 |
|审核和报告|是 |是 |是 |是 |是 |
|条件访问 |是 |是 |是 |是 |是 |
\*条件访问需要额外的许可证


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织是否有所需的许可证来满足合规性和安全性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |后续步骤         |检查贵组织的当前许可，并确认其是否满足合规性和安全性的所有业务需求。         |

在启用其中任何功能之前，请确保你有权访问 Office 365 管理中心中的安全性和合规性中心。 默认情况下，租户管理员有访问权限。

不要求在安全性和合规性中心中启用内容搜索和电子数据展示。

<a name="location-of-data-in-teams"></a>Teams 中的数据的位置
-------------------------

Teams 中的数据位于与你的 Office 365 租户关联的地理区域。 当前，Teams 支持美洲、欧洲、中东和非洲以及亚太地区这些区域。 

> [!IMPORTANT]
> Teams 目前在英国和印度仅为新租户提供数据驻留。 新租户的定义是，该租户中没有任何一个用户登录过 Teams。 英国和印度的现有租户将继续分别保留在 EMEA 和 APAC 区域中，直至宣布迁移计划（预计在 2018 年）。

要详细了解为 Teams 启动英国和印度数据驻留的信息，请阅读 Ansuman Acharya 的博客文章 [Microsoft Teams 启动印度数据驻留，其他地理位置不久将启动](https://go.microsoft.com/fwlink/?linkid=867773)。

要查看哪些区域托管你的租户数据，请转到 [Office 365 管理中心](https://portal.office.com/adminportal/home) > “**设置**” > “**组织配置文件**”。 向下滚动到“**数据位置**”。 

![Office 365 管理中心中“数据位置”表（包括 Teams）的屏幕截图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="privacy-in-teams"></a>Teams 中的隐私
--------------------------

作为 Office 365 的客户，你拥有并控制你的数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无权访问上载的内容。 对于 OneDrive for Business 和 SharePoint Online，客户数据位于租户中。

请在 [*Office 365 信任中心*](https://go.microsoft.com/fwlink/?linkid=855779)详细查看我们的信任和安全相关的信息。 Teams 与 Office 365 信任中心遵循相同的指导和原则。
