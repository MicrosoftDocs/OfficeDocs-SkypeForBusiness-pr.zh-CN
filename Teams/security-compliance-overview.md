---
title: Microsoft Teams 中的安全性和合规性概述
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: 包括审核和报告、 合规性内容搜索、 电子数据展示，和更多的 Microsoft 团队的安全性和遵从性功能的概述。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc686b520c9bd765539ff5fd9f636bc876583a41
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937895"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和合规性概述
======================================================

Microsoft Teams 建立在 Office 365 超大规模企业级云之上，提供我们的客户期望的高级安全性和合规性功能。

Teams 在上市时符合 Tier C 标准。 这包括以下标准：ISO 27001、ISO 27018、SSAE16 SOC 1 和 SOC 2、HIPAA 以及欧盟模型条款 (EUMC)。 在 Microsoft 合规性框架中，Microsoft 将 Office 365 应用和服务分类为四种类别。 每种类别均按特定的合规性承诺定义，Office 365 服务或相关的 Microsoft 服务必须履行这些承诺才能列在相应类别中。

默认情况下启用合规性类别 C 和 D 中的服务，它们有行业领先的合规性承诺。 类别 A 和 B 中的服务提供了针对整个组织开启或关闭这些服务的控制功能。 有关详细信息，请参阅[行业标准和规章的合规性框架](https://go.microsoft.com/fwlink/?linkid=855777)。 Teams 还支持云安全联盟合规性。

Teams 还强制执行团队范围和组织范围的双重身份验证、通过 Active Directory 进行单一登录以及对正在传输的数据和静态数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。 工作组 SharePoint 网站中存储的 OneNote 数据。 Wiki 选项卡可以还用于笔记记录和团队 SharePoint 网站中还存储它的内容。

我们还增加了以下支持：审核日志搜索、针对频道、聊天和文件的电子数据展示和法定保留，以及通过 Microsoft Intune 进行移动应用管理。 转到 Office 365 安全性和合规性中心管理这些设置。 

## <a name="auditing-and-reporting"></a>审核和报告

审核日志搜索置于 Office 365 安全性和合规性中心中，进而可以通过提供审核日志数据对审核事件设置警报和/或进行报告，能够导出工作负荷特定或一般事件集以用于管理和调查，审核时间线无限制。 所有审核日志数据可用于在 Office 365 安全性和合规性中心中设置警报，以及用于筛选和报告以供进一步分析。 请参阅此[链接](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)可了解有关如何进行审核日志搜索的 Office 365 安全性和合规性中心中的 Microsoft 团队事件详细信息。 

## <a name="compliance-content-search"></a>合规性内容搜索

内容搜索可以用于通过筛选功能的富所有团队数据都搜索和导出到特定合规性和诉讼支持的容器。 在有无电子数据展示案例的情况下，均可执行此操作。 这样，合规性管理员可以跨所有用户收集团队数据、 查看和导出进行进一步处理。 请参阅此[链接](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4)可了解有关如何执行合规性内容搜索中的 Office 365 安全性和合规性中心的 Microsoft 团队内容的详细信息。 

提示： 可以使用 kind MicrosoftTeams 进行筛选，通过仅内容的 Microsoft 团队即聊天和通道消息、 会议和呼叫。 

## <a name="ediscovery"></a>电子数据展示

电子数据展示是为了回应法律诉讼或调查中提供文件的要求而找出、收集和生成电子方式存储的信息 (ESI) 的电子操作过程。 功能包括案例管理、 保留、 搜索、 分析和团队数据导出。 这包括聊天、 消息和文件、 会议和呼叫摘要。 有关创建和电子数据展示中可用团队会议和呼叫、 会议和呼叫中发生事件的摘要。 

有关如何执行操作安全和合规性中心和运行合规性内容搜索团队内容中的电子数据展示的详细信息，请转到以下链接： 

[电子数据展示](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[内容搜索](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

客户可以利用就地电子数据展示或 [高级电子数据展示] 每他们的需求 (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)。 下表概括列出了这两者之间的差异：


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


## <a name="legal-hold"></a>法定保留

在诉讼，它通常所需的所有数据相关都联的用户 （管理员） 或团队永久保留，因此可用作证据的大小写。 这被通过发出合法保留的用户 （用户邮箱） 或团队。 时团队中的任何团队置于就地保留 （至目标的查询或筛选的内容邮箱或网站集的子集） 或诉讼保留 （整个邮箱或网站集），组邮箱置于保留项。 这样可以确保即使最终用户删除或编辑组邮箱到 ingested 的通道消息，该内容的变副本是维护和 eDisscovery 搜索中可用。 通常在电子数据展示案例的上下文中应用法定保留。 请参阅[此](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a)帮助文章以了解有关保留和 Office 365 安全性和合规性中心中的保留项的详细信息。 

## <a name="information-protection-architecture-for-microsoft-teams"></a>信息的 Microsoft 团队保护体系结构。 

如下图所示的引入数据流团队对 Exchange 和 SharePoint 的工作组文件和消息。 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

如下图所示的引入流程团队会议和呼叫数据到 Exchange。

![团队会议和呼叫数据到 Exchange 的工作流关系图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 可以有最多 24 小时制延迟工作组的内容。

## <a name="retention-policies"></a>保留策略

团队对话是永久性的且保留默认情况下不限次数。 保留策略的引入，管理员可以在团队聊天和频道邮件的安全和合规性中心中配置保留策略 （保留和删除）。 这有助于组织保留特定时间段法规遵从性 （即保留策略） 的数据，或者如果认为是责任特定的一段时间后删除的数据 （即，删除策略）。 团队保留策略确保删除数据时，它从删除所有团队服务上的永久数据存储位置。 

若要管理团队保留策略的工作原理使用的设置和 cmdlet 在下**数据管理**的 Office 365 安全性和合规性中心 > **保留**。

支持团队保留策略： 
    
- 保留： 指定的持续时间保持团队数据并不执行任何操作
- 保留和然后删除： 团队数据保留在指定时间段，然后删除
- 删除： 指定的时间后删除团队数据

尚不支持团队保留策略：

- 高级的保留策略不适用于团队聊天和团队通道消息位置
- 少于 30 天的持续时间

管理员可以设置团队专用聊天 （1:1 或一对多聊天） 和团队通道消息的独立的保留策略。 在许多情况下，组织考虑为多个比通道消息，通常是与项目相关的更多对话责任的私人聊天数据。 这些策略设置中的安全性和合规性中心，**数据调控** > **保留**。 打开**团队通道消息**和**团队聊天**，然后定义 （还如下图中所示） 这些位置的保留策略。 

当您打开**团队通道消息**时，您可以指定此策略将应用于哪个团队。 例如，团队 X、 Y、 和 Z，管理员可以 1 年后删除策略设置 （通过单独选择这些团队），并将 3 年删除策略应用于工作组的其余部分。 

您可以通过选择特定用户并应用唯一的保留策略的**团队聊天**执行相同的操作。 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> 团队通道消息位置和团队聊天位置仅地址存储在 Exchange Online 邮箱 （用户和组邮箱） 的团队对话。 从所有相关的存储位置，即邮箱、 基底和聊天服务中删除邮件。 
> 
> 若要管理保留策略的工作组文件，存储在 OneDrive for Business 和 SharePoint，使用它们的保留策略。




按照设计，为团队文件删除策略配置通过 SharePoint Online 和 OneDrive 业务位置。 因此，很可能策略无法删除之前删除这些消息获取团队聊天或通道邮件中引用的文件。 在这种情况下，该文件将仍显示在工作组邮件中，但如果您单击该文件，将出现"找不到文件"错误 （此种可能还出现不存在的策略，如果有人手动删除文件从 SharePoint Online 或 OneDrive for Business）。


有关为 Office 365 配置保留策略的详细信息，请阅读[的保留策略的概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。
 

## <a name="retention-policies-faq"></a>保留策略常见问题

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>哪些类型的策略我可以安装在保留策略和它们是如何工作？

在安全和合规性中心中，工作组或任何其他工作负荷，设置的保留策略时您可以设置策略的两种主要类型： 
- 保留： 这些策略确保您的数据保留给定时间段的时间，无论在最终用户工具会发生什么情况。 他们确保数据保留出于合规性和电子数据展示，直到这次中可用的过期。 时间过后，您的策略可以指明是否不执行任何操作或删除的数据。 在工作组，如果您为 7 年创建保留策略，即使最终用户删除其团队邮件，这些消息仍保留电子数据展示的 7 年。
- 删除： 这些策略确保数据不为您的组织的责任。 指定的持续时间后从团队中的所有相关存储删除数据。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>我们可以在组织范围的策略中包括团队？ 

否，当前不。 您必须创建团队聊天和频道的邮件使用团队位置行或这些团队 cmdlet 的特定策略：[新建 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [新建 TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)。 这些 cmdlet 将获取和设置以及版本。

### <a name="are-these-retention-policies-retroactive"></a>有以下保留策略影响以前的版本？ 

是的它们是。 如果您创建保留策略，以删除早于 60 天的数据，它将删除工作组创建超过 60 天的数据。 

### <a name="what-is-the-default-retention-policy"></a>什么是默认保留策略？ 

默认情况下，团队聊天、 通道和文件数据所永远保留。 用户可以删除内容，但保留策略不存在，团队数据到 Exchange online 邮箱 （用户和组），则始终存档和那里表示电子数据展示。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>可以指定目标用户或工作组在策略中的的设置？ 

是，则执行操作。 在策略创建向导在位置步骤中，可以包括或排除 （**团队通道消息**） 的团队或用户 （**团队聊天**） 并为组织创建目标的策略。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>使用保留策略中的组邮箱位置行和团队通道消息位置行之间的主要区别是什么？ 

如果您使用的 Exchange Online 的组邮箱和用户邮箱位置行，则将从指定的邮箱删除团队数据。 但是，这仅数据从邮箱中删除。 它不会删除其他团队数据，例如聊天服务。 我们建议使用团队保留策略正确管理团队的所有数据。 团队保留策略将团队数据删除所有的存储位置 – 邮箱，聊天服务，团队客户端。 

注意： 启动保留策略功能的团队可确保仅团队策略删除存储在 Exchange 邮箱位置 （用户或组） 内的团队项目。 其他邮箱上的策略安装程序不会影响团队项目。 这是 true 过去，但已解决的保留策略功能与。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>会发生什么情况 Skype 的互操作性聊天业务联机和团队 – 它们受保留策略？

是，业务联机和团队互操作性聊天 Skype 的工作方式相同。 后的业务在线聊天 Skype 进入团队，它将成为团队聊天线程中的邮件，并获取 ingested 到适当的邮箱。 使相同流动 works – 团队删除策略将从团队线程中删除这些消息。 但是，如果对话历史记录处于的 Skype 业务 online 并从业务联机客户端的 Skype 那些被保存到邮箱，团队保留策略不处理此聊天数据。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>怎么办？ 这些通过安全性和合规性中心 cmdlet 我应使用什么？ 

绝对。 您可以创建使用[安全性和合规性中心 Powershell cmdlet]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)的团队保留策略。 请记住这些不是 Exchange Online cmdlet。 以下是我们创建团队的 cmdlet。 它们从保留中安全性和合规性中心目前 cmdlet 按照现有术语和样式。

|策略|规则|
|---|---|
|[新 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[设置 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [设置 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[删除 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [删除 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>如果有多个团队具有不同的工期，哪一个 wins 的保留策略？

我们将按照[的保留策略的原则](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)，，我们建议您执行太。 短答案是： 
-   通过删除 wins 始终保留
-   最长保留期始终 wins
-   显式包含 wins 高于隐式包含位置方面
-   最短删除期间 wins



## <a name="retention-policies-known-issues"></a>已知问题的保留策略

1. 下选择工作组添加工作组通道消息位置行中，您可能会看到的 Office 365 组不还团队。 这将在将来解决。

1. 下团队聊天位置行中选择用户，您可能会看到来宾和非邮箱用户。 保留策略不打算为来宾，设置，而且我们正在这些从列表中删除。 

1. Exchange 生命周期助理 (ELC)，每日，运行，但它具有 7 天的 SLA。 因此，很可能，如果您有删除早于 60 天的项目工作组保留策略，这些项目无法达 67 天保留。 这不是新情况-遵循 Exchange 模型。 当然，在大多数情况下，没有延迟。


| | | |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织需要哪些安全性和合规性功能？ 贵组织是否有所需的许可证来满足安全性和合规性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |后续步骤         |文档所需的安全性和遵从性功能。         |

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
> [!NOTE]
> \*条件访问需要额外的许可证


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织是否有所需的许可证来满足合规性和安全性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |后续步骤         |查看贵组织的当前许可，并确认它满足合规性和安全性的所有业务要求。         |

在启用其中任何功能之前，请确保你有权访问 Office 365 管理中心中的安全性和合规性中心。 默认情况下，租户管理员有访问权限。

内容搜索和电子数据展示不需要启用中安全性和合规性中心。

<a name="location-of-data-in-teams"></a>Teams 中的数据的位置
-------------------------

Teams 中的数据位于与你的 Office 365 租户关联的地理区域。 目前，团队支持澳大利亚、 加拿大、 印度、 日本、 英国、 美国、 APAC 和 EMEA 区域。 

> [!IMPORTANT]
> 团队目前提供数据住所中澳大利亚、 加拿大、 印度、 日本和英国的仅新租户。 新租户的定义是，该租户中没有任何一个用户登录过 Teams。 澳大利亚、 印度和日本从现有租户将继续将其团队数据存储在 APAC 区域。 在加拿大和英国的现有租户会在美国存储其数据和 EMEA 区域，分别。

要详细了解为 Teams 启动英国和印度数据驻留的信息，请阅读 Ansuman Acharya 的博客文章 [Microsoft Teams 启动印度数据驻留，其他地理位置不久将启动](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)。 

有关团队加拿大数据住所详细信息，请阅读 Varun Sagar 博客文章， [Microsoft 团队启动加拿大数据住所、 澳大利亚和日本即将提供](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)。 

若要了解有关团队澳大利亚和日本数据住所的启动的详细信息，请阅读 Varun Sagar 博客文章， [Microsoft 团队启动澳大利亚和日本数据居住权](https://go.microsoft.com/fwlink/?linkid=867773)。 

要查看哪些区域托管你的租户数据，请转到 [Office 365 管理中心](https://portal.office.com/adminportal/home) > “**设置**” > “**组织配置文件**”。 向下滚动到“**数据位置**”。 

![Office 365 管理中心中“数据位置”表（包括 Teams）的屏幕截图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>条件访问策略团队如何工作？
-------------------------

Microsoft 团队严重依赖 Exchange Online、 SharePoint Online 和 Skype 业务 online 核心工作效率方案，如会议、 日历、 互操作的聊天和文件共享。 时用户直接登录到 Microsoft 团队的任何客户端上，为这些云应用程序设置的条件的访问策略应用于的 Microsoft 团队。 

单独的 Microsoft 团队支持作为云应用程序在 Azure Active Directory 条件访问策略。 当用户登录时，为 Microsoft 团队云应用程序设置的条件的访问策略将适用于 Microsoft 团队。 但是，不正确的策略，如 Exchange Online 和 SharePoint Online 的其他应用程序，用户可能仍将能够直接访问这些资源。 对于有关 azure 门户中的某个条件的访问策略设置的详细信息，请转至: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Windows 和 Mac 的 Microsoft 团队桌面客户端支持现代身份验证。 现代身份验证将跨平台基于在 Azure Active Directory 身份验证库 (ADAL) Microsoft Office 客户端应用程序登录。

Microsoft 团队桌面应用程序支持 AppLocker。  有关 AppLocker 先决条件的详细信息，请参阅： 要求使用 AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

<a name="privacy-in-teams"></a>Teams 中的隐私
--------------------------

作为 Office 365 的客户，你拥有并控制你的数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无权访问上载的内容。 对于 OneDrive for Business 和 SharePoint Online，客户数据位于租户中。

请在 [Office 365 信任中心](https://go.microsoft.com/fwlink/?linkid=855779)详细查看我们的信任和安全相关的信息。 Teams 与 Office 365 信任中心遵循相同的指导和原则。
