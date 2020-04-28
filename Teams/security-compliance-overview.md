---
title: 安全性和合规性概述
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Microsoft 团队的安全和合规性功能概述，包括审核和报告、合规性内容搜索、eDiscovery 等。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e3f26f286fa3f8418df93d6498b8c754c857785
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901717"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft 团队中的安全和合规性

> [!IMPORTANT]
> 若要了解如何在**COVID-19 病毒发作期间让所有人在家里工作**，请阅读以下文章：
>  - [安全团队为支持在家办公需完成的 12 大任务](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分离隧道为远程用户优化 Office 365 连接性](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 已更新2020年4月2日：[团队安全指南](teams-security-guide.md)


Microsoft Teams 建立在 Office 365 超大规模企业级云之上，提供我们的客户期望的高级安全性和合规性功能。 有关在 Office 365 中规划安全性的详细信息，请查看我们的 Office 365 内容。 [Office 365 安全路线图](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)是一个不错的开端。 有关在 Office 365 中规划合规性的详细信息，您可以从[适用于安全和合规性文章的计划](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)开始。


本文将提供有关特定于团队的安全和合规性的进一步信息。 不要错过有关安全和合规性的 Microsoft 相关视频：

- [适用于 IT 的 Microsoft 团队基础知识：安全和合规性](https://youtu.be/91lHNKVVvQ4)（12:42 分钟）
- [适用于安全和合规性的 Microsoft 团队控件](https://www.youtube.com/watch?v=Km4T4hMM__k)（10:54 分钟）

> [!IMPORTANT]
> 作为 Office 365 的客户，你拥有并控制你的数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无权访问已上载的内容。 对于 OneDrive for Business 和 SharePoint Online，客户数据位于租户中。 您可以在[Microsoft 信任中心](https://microsoft.com/trustcenter)查看有关我们的信任和安全相关信息的更多信息。 团队遵循与 Microsoft 信任中心相同的指南和原则。

## <a name="security"></a>安全性

团队强制执行团队范围和组织范围内的双重身份验证，通过 Active Directory 进行单一登录，并在传输和存放数据时进行数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。 OneNote 数据存储在团队 SharePoint 网站中。 Wiki 选项卡还可用于笔记记录，其内容也存储在团队 SharePoint 网站中。

阅读身份[模型和身份验证](identify-models-authentication.md)，以便更深入地了解身份验证和团队，以及[新式身份验证工作方式](sign-in-teams.md)对新式身份验证的帮助尤其如此。

由于团队可与 SharePoint、OneNote、Exchange 等进行合作，因此你应该轻松管理 Office 365 中的安全。 若要了解有关 Office 365 安全性的详细信息，请阅读[配置 Office 365 组织以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前，[专用通道](private-channels.md)支持有限的安全和合规性功能。 即将推出专用频道中整套安全和合规性功能的支持。

### <a name="advance-threat-protection-atp"></a>高级威胁防护（ATP）

高级威胁防护（ATP）可用于 Microsoft 团队，以及 SharePoint 和 OneDrive for Business 以及与内容管理团队集成的应用程序。 ATP 允许你确定这些应用程序中的内容是否具有恶意性质，并阻止用户访问此内容。

在检测到 Office 365 中所选设置后，受影响内容的管理方式。 我们强烈建议你在配置 ATP 时考虑所有应用程序，如果需要进一步阅读， [SharePoint、OneDrive 和 Microsoft 团队文章的 Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)将提供有关如何入门的详细信息。

### <a name="safe-links"></a>安全链接

虽然目前，高级威胁防护（ATP）安全链接在 Microsoft 团队中不可用，但现在，它们现在是通过我们的技术采纳计划（点击）进行[公共预览](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide)，同时还未设置常规可用性的发布日期，我们将在该时间到达时更新本文。 同时，有关 Office 365 安全链接的信息，请查看[office 365 ATP 安全链接](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 Atp "安全链接" 在 " [Atp 计划 1" 和 "ATP 计划 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)" 中可用。

### <a name="safe-attachments"></a>安全附件

安全附件是一种旨在通过检查和检测恶意附件来增强用户安全的功能。 全局或安全管理员创建用于处理这些可疑的恶意附件的[策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide)，以防止这些附件被发送到用户、单击和操作。 "安全附件保护" 适用于 SharePoint Online、OneDrive for business 和 Microsoft 团队，并且这两个 Office 365[高级威胁防护计划1和 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)都具有此功能。 请阅读有关安全附件的详细信息，以及这些附件如何帮助保护您[的组织。](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="how-conditional-access-policies-work-for-teams"></a>条件访问策略适用于团队的方式

Microsoft 团队很大程度上依赖于 Exchange Online、SharePoint Online 和 Skype for Business Online，以获得核心生产力方案，如会议、日历、互操作聊天和文件共享。 为这些云应用设置的条件访问策略在用户直接登录到 Microsoft 团队（在任何客户端上）时适用于 Microsoft 团队。

Microsoft 团队作为 Azure Active Directory 条件访问策略中的云应用单独受支持。 为 Microsoft 团队云应用设置的条件访问策略在用户登录时适用于 Microsoft 团队。 但是，如果在其他应用（如 Exchange Online 和 SharePoint Online）上没有正确的策略，用户可能仍然能够直接访问这些资源。 有关在 azure 门户中设置条件访问策略的详细信息，请转到： [Azure Active Directory 快速入门](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

适用于 Windows 和 Mac 的 Microsoft 团队桌面客户端支持新式身份验证。 新式身份验证通过平台将基于 Azure Active Directory 身份验证库（ADAL）的登录引入 Microsoft Office 客户端应用程序。

Microsoft 团队桌面应用程序支持 AppLocker。  有关 AppLocker 先决条件的详细信息，请参阅：使用[applocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)的要求。

## <a name="compliance"></a>符合

团队有大量信息可帮助您处理合规性领域，包括频道、聊天和附件、保留策略、数据丢失保护（DLP）、电子数据丢失保护（DLP）、电子数据展示和法律封存（适用于频道、聊天和文件、审核日志搜索以及与 Microsoft Intune 的移动应用程序管理）。 我们提供了有关以下所有主题的一些信息，您可以转到[Microsoft 365 合规中心](https://compliance.microsoft.com)来管理这些设置。

### <a name="information-barriers"></a>信息障碍

信息障碍是团队管理员在原地保留的策略，可使用户或组与其他人进行通信（当他们没有业务需求来执行此操作时），并且它还允许你设置与查找和电子数据展示（如下所述）相关的策略。 这些策略可以影响1:1 聊天、群组聊天或团队级的用户。

有关本主题的进一步阅读，请转到[Microsoft 团队中的信息障碍](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>通信合规性

通过 Microsoft 365 中的通信合规性，你可以将用户添加到范围内策略，这些策略可以配置为检查适用于攻击性语言的 Microsoft 团队通信、敏感信息以及与内部和法规标准相关的信息。 可以扫描公共和私人团队频道、个人聊天和附件中的聊天通信和相关附件，以帮助最大程度地减少组织中的沟通风险。 有关如何配置策略以帮助你检测、捕获和采取措施处理不当团队通信的详细信息，请参阅[Microsoft 365 中的通信合规性](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。

### <a name="retention-policies"></a>保留策略

Microsoft 团队中的保留策略使你能够保留你的组织出于法规、法律、业务或其他原因而保留的重要数据，还可删除与保留无关的内容和通信。 您还可以使用保留策略保留一段时间内的数据，然后将其删除。 有关详细信息，请参阅[Microsoft 团队文章中的保留策略](retention-policies.md)。

### <a name="data-loss-prevention-dlp"></a>数据丢失防护（DLP）

Microsoft 团队中的数据丢失防护（DLP）以及适用于 Office 365 的较大 DLP 情景，在保护 Office 365 中的敏感文档和数据时面临业务准备。 无论您是否关注邮件或文档中的敏感信息，DLP 策略都能够帮助确保您的用户不会与错误的用户共享此敏感数据。

有关团队中的数据丢失防护的详细信息，请查看[适用于 Microsoft 团队的 DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)。 O36 DLP 问题的一个好的文章是[数据丢失防护的概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>电子数据展示

电子查询（电子查询或电子数据展示）是标识、收集和出具电子存储信息（ESI）的电子方面，可响应法律花色或调查中的生产请求。 功能包括 "案例管理"、"保存"、"搜索"、"分析" 和 "工作组数据导出"。 这包括聊天、消息传递和文件、会议和通话摘要。 对于团队会议和通话，将创建会议和通话中发生的事件的摘要，并将其提供给电子数据展示。

有关365如何在安全 & 合规中心以及运行团队内容的合规性内容搜索的更多详细信息，请访问以下链接：

[电子数据展示](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[内容搜索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

对于详细信息，我们有一个特定团队的文章，[电子数据展示是来宾到来宾聊天的电子数据展示](eDiscovery-investigation.md)。

客户可以根据其要求利用电子数据展示或[高级电子数据展示](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery)。 下表概括列出了这两者之间的差异：

| |电子数据展示  |高级电子数据展示  |
|---------|---------|---------|
|案例管理     |X        |X         |
|访问控制  |X         |X         |
|内容搜索     |X         | X        |
|保留   |X         | X        |
|导出     |X         |X         |
|重复项检测     |-         |X         |
|使用机器学习的相关性搜索    |-         |X         |
|非结构化数据分析      |-         |X         |

### <a name="legal-hold"></a>法定保留

在诉讼期间，你可能需要将与用户（保管人）或团队相关联的所有数据保留为不可变，以便可以将其用作案例的证据。 你可以通过在法律封存上放置用户（用户邮箱）或团队来执行此操作。 对于团队法律封存，可以将团队的邮箱置于以下保留状态：

- 就地保留（通过目标查询或筛选内容的邮箱或网站集的子集处于暂候状态），或者
- 诉讼封存（整个邮箱或网站集被置于保持状态）。

在任何一种情况下，设置保留后，它可确保即使最终用户删除或编辑组邮箱中的频道消息，也可通过电子数据展示搜索维护和提供该内容的不可变副本。 法律封存通常在电子数据展示事例的上下文中应用。

请参阅[保留策略文章概述](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)，以了解有关 Microsoft 365 合规中心中的保留和保留的详细信息。 有关法律封存的更多团队特定信息，我们还让[Microsoft 团队用户或团队在法律封存](legal-hold.md)文章中了解详细信息。

### <a name="compliance-content-search"></a>合规性内容搜索

可使用内容搜索通过丰富的筛选功能搜索所有团队数据。 生成的数据可以导出到特定容器，以实现合规性和诉讼支持。 在有无电子数据展示案例的情况下，均可执行此操作。 这使合规性管理员能够跨所有用户收集团队数据、查看和导出它以进行进一步处理。 请参阅[Office 365 文章中的 "内容搜索"](https://docs.microsoft.com/microsoft-365/compliance/content-search) ，了解有关如何在 microsoft "365 合规中心" 中执行 microsoft 团队以及其他 microsoft 365 或 Office 365 内容的合规性内容搜索的详细信息。

> [!TIP]
> 使用内容搜索，您可以根据需要筛选仅限 Microsoft 团队的内容，如聊天和频道消息、会议和呼叫。

如果您想了解有关配置内容搜索的进一步的团队详细信息，请查看[Microsoft 团队文章中的内容搜索](content-search.md)。

### <a name="auditing-and-reporting"></a>审核和报告

审核日志搜索直接插入 Microsoft 365 合规性中心，并使你能够通过导出特定于工作负荷的事件集或常规事件集来针对无限制审核日程表进行管理和调查，从而设置警报以及报告审核事件。 你可以为 Microsoft 365 合规中心内的所有审核日志数据设置通知，并筛选和导出此数据以进行进一步分析。 请参阅[搜索审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)文章，了解有关如何为 Office 365 执行审核日志的详细信息。 若要了解有关在 Microsoft 365 合规中心中搜索 Microsoft 团队事件的详细信息，我们还提供团队文章中的 "[启用审核](audit-log-events.md)"，供你查看。

## <a name="privacy"></a>隐私

在 Microsoft，保护您的数据是我们的最高优先级。 若要了解我们的隐私做法，请阅读[Microsoft 的隐私](https://www.microsoft.com/trust-center/privacy)。

## <a name="information-protection-architecture"></a>信息保护体系结构

下图指示团队文件和邮件的团队数据到 Exchange 和 SharePoint 的接收流。

![团队数据到 Exchange 和 SharePoint 的工作流的图表](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下图指示团队会议和向 Exchange 调用数据的接收流程。

![团队会议工作流和向 Exchange 调用数据的工作流的图表](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 要发现团队内容，最多可以有24小时的延迟。

## <a name="licensing"></a>许可

在信息保护功能方面，Microsoft 365 订阅、Office 365 订阅和关联的独立许可证将确定可用功能集。

有关确定授权需要实现安全和合规性功能的信息，请查看[Office 365 或 Microsoft 365 的许可](https://download.microsoft.com/download/8/7/7/877B1713-671E-43AA-BB79-AF8478C64AFF/Licensing-Microsoft-365.pdf)。

> [!NOTE]
> 不需要在安全 & 合规中心中启用内容搜索和电子数据展示。

## <a name="location-of-data-in-teams"></a>Teams 中的数据的位置

团队中的数据位于与您的 Office 365 组织相关联的地理区域中。 若要查看当前受支持的区域，请查看[Microsoft 团队中数据的位置](location-of-data-in-teams.md)。

如果需要查看哪个区域驻留你的租户的数据，请转到[Microsoft 365 管理中心](https://portal.office.com/adminportal/home) > **设置** > **组织配置文件**。 向下滚动到“**数据位置**”。

![数据位置表的屏幕截图，其中包括管理中心中的团队](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>合规性标准

团队符合第 D 层。 这包括以下标准： [ISO 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001)、 [iso 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018)、 [SSAE16 SOC 1 和 SOC 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)、 [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)和[欧盟型号子句（EUMC）](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses)。 在 Microsoft 合规性框架中，Microsoft 将 Office 365 应用和服务分类为四种类别。 每种类别均按特定的合规性承诺定义，Office 365 服务或相关的 Microsoft 服务必须履行这些承诺才能列在相应类别中。

默认情况下启用合规性类别 C 和 D 中的服务，它们有行业领先的合规性承诺。 类别 A 和 B 中的服务提供了针对整个组织开启或关闭这些服务的控制功能。 可在[合规性标准](security-compliance-overview.md#compliance-standards)中找到详细信息。 Teams 还支持云安全联盟合规性。

## <a name="related-topics"></a>相关主题

[Microsoft 365 安全](https://docs.microsoft.com/microsoft-365/security/)
[microsoft 365 合规性](https://docs.microsoft.com/microsoft-365/compliance/)
[microsoft 合规性服务](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
