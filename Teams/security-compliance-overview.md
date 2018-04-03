---
title: Microsoft Teams 中的安全性和合规性概述
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Microsoft Teams 中的安全性和合规性概述，包括审核和报告、合规性内容搜索以及电子数据展示等。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857e4b691256ff13b6f9308bcd9fb12dfb10297d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和合规性概述
======================================================

Microsoft Teams 建立在 Office 365 超大规模企业级云之上，提供我们的客户期望的高级安全性和合规性功能。

Teams 在上市时符合 Tier C 标准。 这包括以下标准：ISO 27001、ISO 27018、SSAE16 SOC 1 和 SOC 2、HIPAA 以及欧盟模型条款 (EUMC)。 在 Microsoft 合规性框架中，Microsoft 将 Office 365 应用和服务分类为四种类别。 每种类别均按特定的合规性承诺定义，Office 365 服务或相关的 Microsoft 服务必须履行这些承诺才能列在相应类别中。

默认情况下启用合规性类别 C 和 D 中的服务，它们有行业领先的合规性承诺。 类别 A 和 B 中的服务提供了针对整个组织开启或关闭这些服务的控制功能。 有关详细信息，请参阅[行业标准和规章的合规性框架](https://go.microsoft.com/fwlink/?linkid=855777)。 Teams 还支持云安全联盟合规性。

Teams 还强制执行团队范围和组织范围的双重身份验证、通过 Active Directory 进行单一登录以及对正在传输的数据和静态数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。

我们还增加了以下支持：审核日志搜索、针对频道、聊天和文件的电子数据展示和法定保留，以及通过 Microsoft Intune 进行移动应用管理。 请转到 Office 365 安全和法规遵从性中心管理这些设置。 

## <a name="auditing-and-reporting"></a>审核和报告

审核日志搜索置于 Office 365 安全性和合规性中心中，进而可以通过提供审核日志数据对审核事件设置警报和/或进行报告，能够导出工作负荷特定或一般事件集以用于管理和调查，审核时间线无限制。 所有审核日志数据可用于在 Office 365 安全性和合规性中心中设置警报，以及用于筛选和报告以供进一步分析。

## <a name="compliance-content-search"></a>合规性内容搜索

可以使用内容搜索通过丰富的筛选功能搜索 Teams，并可以将搜索结果导出到特定容器以用于合规性和诉讼活动。 在有无电子数据展示案例的情况下，均可执行此操作。

## <a name="ediscovery"></a>电子数据展示

电子数据展示是为了回应法律诉讼或调查中提供文件的要求而找出、收集和生成电子方式存储的信息 (ESI) 的电子操作过程。

功能包括案例管理、 保存、 搜索、 分析和团队数据的导出。 这些数据包括聊天、消息传递和文件数据。

客户可以利用就地电子数据展示或[高级电子数据展示](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)。

下表概括列出了这两者之间的差异：


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

当 Teams 中的任何团队置于就地保留或诉讼保留时，将组邮箱置于保留状态。

通常在电子数据展示案例的上下文中应用法定保留。

下图显示了 Teams 数据到 Exchange 和 SharePoint 的工作流。

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> 发现 Teams 内容的过程最长可能延迟 24 小时。


## <a name="retention-policies"></a>保留策略

小组对话将是持续和永久默认保留。 随着保留策略，管理员可以配置团队聊天和通道消息的安全性和法规遵从性中心 （保留和删除） 的保留策略。 这可帮助组织保留数据的法规遵从性 （即保留策略） 的特定期间或去除的数据 （即删除策略） 如果认为是一项负担一段时间。 保留策略小组确保，当删除数据时，它会从团队服务上的所有永久数据存储位置。 

管理团队保留策略工作原理的设置和 cmdlet Office 365 安全和法规遵从性在中心中使用**数据治理**下 > **保留**。

支持团队保留策略： 
    
- 保留： 保持指定的持续时间的团队数据并不执行任何操作
- 保存，然后删除： 保持指定的持续时间的团队数据，然后删除
- 删除： 删除指定的时间后团队数据

尚不支持团队保留策略：

- 高级的保留策略不能应用于团队聊天和团队通道消息位置
- 不超过 30 天的持续时间

管理员可以设置不同的保留策略团队专用聊天 （1:1 或一对多聊天） 和团队通道消息。 在许多情况下，组织会考虑私人聊天数据为更多的负债比信道消息，通常是更多的与项目相关的对话。 安全性和符合性中心，**数据治理**中设置这些策略 > **保留**。 打开**团队通道消息**和**小组研讨**，然后定义这些位置 （如下图中还显示） 的保留策略。 

当您打开**团队通道消息**时，您可以指定该策略将应用于哪个团队。 例如，对于 X、 Y 和 Z 的团队，管理可以为期 1 年的删除策略设置 （通过分别选择这些团队），并对团队的其余部分应用 3 年删除策略。 

通过选择特定的用户并应用唯一的保留策略，可以为**小组研讨**做同样的事情。 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> 团队通道消息位置和小组研讨位置仅地址存储在联机 Exchange 邮箱 （用户和组邮箱） 小组对话。 消息从即邮箱、 基底，以及聊天服务的所有相关存储位置中删除。 
> 
> 管理保留策略小组文件，它们将用于商业和 SharePoint 存储在 OneDrive，使用它们的保留策略。




按照设计，团队文件的删除策略配置通过 SharePoint Online 和 OneDrive 的业务位置。 因此，很可能一个策略可以删除之前删除这些邮件团队聊天或通道消息中引用的文件。 在这种情况下，该文件将仍显示在团队消息中，但如果您单击该文件，您将获得"未找到文件"错误 （这可能还发生的一种策略，没有人从 SharePoint Online 或业务的 OneDrive 手动删除文件）。


有关将配置为 Office 365 的保留策略的详细信息，请阅读[概述的保留策略](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。
 

## <a name="retention-policies-faq"></a>保留策略的常见问题解答

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>哪种类型的策略可以在保留策略中设置以及它们如何工作？

在安全性和法规遵从性中心，当团队或者任何其他的工作负荷，设置保留策略，您可以设置策略的两种主要类型： 
- 保留： 这些策略可确保您的数据被保留为给定时间段内，无论发生什么情况中的最终用户工具。 他们确保数据保留的法规遵从性目的和 eDiscovery，直到这次在过期。 在时间到期之后，您的策略可以指示是否不执行任何操作或删除数据。 团队，在如果您 7 年来，创建保留策略，即使最终用户删除他们团队的邮件，这些邮件仍保留为 eDiscovery 7 年。
- 删除： 这些策略可确保数据不是您的组织的责任。 在指定的持续时间之后, 从团队中的所有相关存储删除数据。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>我们可以在组织范围的策略中包含团队？ 

不，没有。 您必须创建使用团队位置行或这些团队 cmdlet 的团队聊天和通道消息的特定策略： 新建 TeamsRetentionCompliancePolicy & New TeamsComplianceRetentionRule。 这些 cmdlet 具有 get 和 set 版本也。

### <a name="are-these-retention-policies-retroactive"></a>是否这些保留策略追溯？ 

是的它们是。 如果您创建一个保留策略以删除数据超过 60 天，它将删除团队数据创建超过 60 天。 

### <a name="what-is-the-default-retention-policy"></a>默认保留策略是什么？ 

默认情况下，团队聊天、 通道和文件数据被永远保留。 用户可以删除某件事情，但在没有保留策略的情况下，团队数据到联机 Exchange 邮箱 （用户和组），则始终存档和将 eDiscovery 那里停留。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>可以指定目标的用户或组策略中的设置？ 

是的确实。 在策略创建向导中的位置步骤中，可以包括或排除团队 （**团队通道消息**） 或用户 （**团队聊天**） 并为您的组织创建目标的策略。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>使用保留策略中的组邮箱位置行和团队通道消息位置行之间的主要区别是什么？ 

如果您使用的联机 Exchange 组邮箱和用户邮箱的位置的行，则将从指定的邮箱删除团队数据。 但是，这只会删除数据从邮箱。 它不会删除团队的其他数据，如聊天服务。 我们建议使用小组保留策略无法正确管理团队中的所有数据。 团队的保留策略删除所有存储的位置--邮箱聊天服务，团队客户端从团队数据。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>怎样到 Skype 的在线业务和团队互操作聊天--它们受到了保留策略？

是的在线业务和团队互操作聊天 Skype 的工作方式相同。 对业务在线聊天 Skype 进入团队，一旦它成为团队聊天线程中的邮件并获取到适当的邮箱 ingested。 变流工作原理，因此团队删除策略将从团队线程删除这些邮件。 但是，如果对话历史记录已经为 Skype 的在线业务，Skype 的在线业务客户端从那些将被保存到邮箱聊天数据不是由处理小组保留策略。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>我如何通过安全性和法规遵从性中心 cmdlet 吗？ 我应该使用什么？ 

绝对。 您可以创建团队使用[安全性和法规遵从性居中 Powershell cmdlet]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)的保留策略。 请记住，这些都不是 Exchange Online cmdlet。 以下是我们为团队创建的 cmdlet。 他们从安全性和法规遵从性中心目前的保留 cmdlet 遵循现有的命名法和样式。

|策略|规则|
|---|---|
|新 TeamsRetentionCompliancePolicy| 新 TeamsRetentionComplianceRule|
|获得 TeamsRetentionCompliancePolicy| 获得 TeamsRetentionComplianceRule|
|获取-TeamsRetentionCompliancePolicy| 组-TeamsRetentionComplianceRule|
|删除-TeamsRetentionCompliancePolicy| 删除-TeamsRetentionComplianceRule|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>如果有多个保留策略团队，不同持续时间的一次为准？

我们遵循[原则的保留策略](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)，并建议执行过。 简短的答案是： 
-   始终保留胜过删除
-   最长保留期总是获胜
-   显式包含胜过隐式包含的位置
-   最短的删除操作期间 wins



## <a name="retention-policies-known-issues"></a>已知问题的保留策略

1. 在团队通道消息位置行中选择的团队，您可能会看到不还，Office 365 组的团队。 这将在以后解决。

1. 下的团队交谈位置行中选择用户，您可能看到的来宾和非邮箱用户。 保留策略并不适合将客人，而且我们正在这些从列表中删除。 

1. 交换生命周期 (ELC) 助手每日运行，但它的 SLA 为 7 天。 因此，有可能，如果您有一个小组保留策略，以删除早于 60 天内的项目，这些项目无法达 67 天保持。 这不是新的情况-它跟交换模型。 当然，在大多数情况下，没有任何延迟。


| | | |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织需要哪些安全性和合规性功能？ 贵组织是否有所需的许可证来满足安全性和合规性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |后续步骤         |记录您所需的安全性和法规遵从性功能。         |

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
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |后续步骤         |查看您的组织当前授权并确认它满足法规遵从性和安全性的所有业务需求。         |

在启用其中任何功能之前，请确保你有权访问 Office 365 管理中心中的安全性和合规性中心。 默认情况下，租户管理员有访问权限。

内容搜索和 eDiscovery 不需要支持在安全和法规遵从性中心。

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

检查出更多有关我们的信任和安全相关的[Office 365 信任中心](https://go.microsoft.com/fwlink/?linkid=855779)的信息。 Teams 与 Office 365 信任中心遵循相同的指导和原则。
