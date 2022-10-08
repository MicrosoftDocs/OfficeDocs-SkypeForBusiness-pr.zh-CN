---
title: 安全性和符合性概述
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Microsoft Teams 安全性和合规性功能概述，包括隐私和加密、审核和报告等。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
- purview-compliance
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d673be29b62097dd2737d24910707bac8ad58d3b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046882"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和符合性

> [!IMPORTANT]
> 若要了解如何在 **COVID-19 疫情期间每个人在家工作时** 最好地确保安全，请阅读以下文章：
>  - [安全团队为支持在家办公需完成的 12 大任务](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分离隧道为远程用户优化 Microsoft 365 或 Office 365 连接性](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新时间：2020 年 4 月 2 日： [Teams 安全指南](teams-security-guide.md)


Microsoft Teams 基于 Microsoft 365 构建，Office 365超大规模企业级云，提供客户期望的高级安全性和合规性功能。 有关在 Microsoft 365 或Office 365中规划安全性的详细信息，[安全路线图](/microsoft-365/security/office-365-security/security-roadmap)是一个很好的起点。 有关在 Microsoft 365 或 Office 365 中规划合规性的详细信息，可以从[安全&合规性计划](/microsoft-365/compliance/plan-for-security-and-compliance)开始。


本文将提供有关 Teams 特定安全性和合规性的更多信息。 不要错过有关安全性和合规性的 Microsoft 力学视频：

- [IT Microsoft Teams 协作版：安全性和合规性](https://youtu.be/91lHNKVVvQ4) (12：42 分钟) 
- [Microsoft Teams 安全性和合规性控制](https://www.youtube.com/watch?v=Km4T4hMM__k) (10：54 分钟) 

> [!IMPORTANT]
> 作为 Microsoft 365 或Office 365的客户，你拥有并控制数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无权访问上传的内容。 与 Microsoft 365 中的 OneDrive 和 SharePoint 一样，客户数据保留在租户中。 可以在 [Microsoft 信任中心](https://microsoft.com/trustcenter)查看有关我们的信任和安全相关信息的详细信息。 Teams 遵循与 Microsoft 信任中心相同的指导和原则。

## <a name="security"></a>安全性

Teams 强制实施全团队和组织范围的双因素身份验证、通过 Active Directory 进行单一登录，以及对传输和静态数据进行加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。 OneNote 数据存储在团队 SharePoint 网站中。 Wiki 选项卡也可用于记笔记，其内容也存储在团队 SharePoint 网站中。

读取 [标识模型和身份验证](identify-models-authentication.md) ，以便更深入地了解身份验证和 Teams，以及 [新式身份验证的工作原理](sign-in-teams.md) 将特别有助于新式身份验证。

由于 Teams 与 SharePoint、OneNote、Exchange 等合作，因此你应该能够轻松地管理 Microsoft 365 或Office 365全部安全性。 若要了解详细信息，请阅读[有关如何配置 Microsoft 365 或Office 365组织以提高安全性的信息](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前， [专用通道](private-channels.md) 支持有限的安全性和符合性功能。 即将推出对专用频道中一整套安全性和合规性功能的支持。

### <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

Microsoft Defender for Office 365适用于 Microsoft Teams 以及与 Teams 集成以进行内容管理的 SharePoint 和 OneDrive 应用程序。 Defender for Office 365允许你确定这些应用程序中的内容是否具有恶意性质，并阻止用户访问此内容。

检测后如何管理受影响的内容，必须满足你在 Microsoft 365 或Office 365中选择的设置。 我们强烈建议在配置Defender for Office 365时考虑所有应用程序，若要进一步阅读[安全链接的工作原理概述，以及设置安全链接的步骤](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)，请参阅此处了解有关入门的详细信息。

### <a name="safe-links-in-microsoft-teams"></a>Microsoft Teams 中的安全链接

Defender for Office 365 Microsoft Teams 中提供了安全链接。 若要获取有关什么是安全链接以及如何处理此功能的详细信息，请阅读 [Teams 的安全链接设置](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)。 Defender for Office 365[计划 1 和计划 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide) 中都提供了安全链接。

### <a name="safe-attachments"></a>安全附件

安全附件是一项功能，旨在通过检查和检测恶意附件来增强用户安全性。 全局或安全管理员 [启用该功能](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) 并 [创建](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) 策略来处理这些可疑的恶意附件，以防止向用户发送、单击和执行操作。

SharePoint、OneDrive 和 Microsoft Teams 以及 Microsoft Defender for Office 365 [计划 1 和计划 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide) 中的 Microsoft 365 或 Office 365 都可使用安全附件保护。 在 [本文](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide)中详细了解安全附件及其如何帮助保护组织。

### <a name="secure-score"></a>安全分数

Microsoft 安全分数是衡量组织安全状况的度量值，较高数字表示采取了更多改进措施。 可以在[Microsoft 365 安全中心](https://security.microsoft.com/securescore)中找到它。 遵循安全分数建议可以保护组织免受威胁。 在Microsoft 365 安全中心的集中式仪表板中，组织可以监视和处理其 Microsoft 365 标识、应用和设备的安全性。 Microsoft Teams 现在提供了有关安全分数的建议，建议管理员在平台上监视其安全立场。

安全分数可帮助组织：
- 报告组织安全状况的当前状态。
- 通过提供可发现性、可见性、指导和控制来改善其安全状况。
- 与基准进行比较，并建立关键性能指标 (KPI) 。

### <a name="how-conditional-access-policies-work-for-teams"></a>条件访问策略如何为 Teams 工作

Microsoft Teams 严重依赖 Exchange Online、SharePoint 和 Skype for Business Online 来实现核心生产力方案，例如会议、日历、互操作聊天和文件共享。 当用户直接登录到任何客户端上的 Microsoft Teams 时，为这些云应用设置的条件访问策略将应用于 Microsoft Teams。

在 Azure Active Directory 条件访问策略中，Microsoft Teams 作为云应用单独受支持。 用户登录时，为 Microsoft Teams 云应用设置的条件访问策略适用于 Microsoft Teams。 但是，如果没有其他应用（如 Exchange Online 和 SharePoint）上的正确策略，用户仍可直接访问这些资源。 有关在Azure 门户中设置条件访问策略的详细信息，请参阅 [Azure Active Directory 快速入门](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

适用于 Windows 和 Mac 的 Microsoft Teams 桌面客户端支持新式身份验证。 新式身份验证基于 Azure Active Directory 身份验证库 (ADAL) 跨平台将登录引入 Microsoft Office 客户端应用程序。

Microsoft Teams 桌面应用程序支持 AppLocker。  有关 AppLocker 先决条件的详细信息，请参阅：使用 [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker) 的要求。

## <a name="compliance"></a>合规性

Teams 提供各种信息来帮助你了解合规性领域，包括频道、聊天和附件的通信合规性、保留策略、数据丢失防护 (DLP) 、电子数据展示和频道、聊天和文件的法律保留、审核日志搜索以及使用Microsoft Intune的移动应用程序管理。 我们提供了有关下面所有这些主题的一些信息，你可以转到[Microsoft Purview 合规门户](https://compliance.microsoft.com)来管理这些设置。

### <a name="information-barriers"></a>信息屏障

Microsoft Purview 信息屏障是 Teams 管理员制定的策略，用于在不需要人员或组进行通信 (，或者出于法规原因阻止他们这样做) ，它还允许你设置与查阅和电子数据展示 (下) 所述的相关策略。 这些策略可能会影响 1：1 聊天、群聊或团队级别的用户。 信息屏障功能在公有云中可用，从 2021 年 1 月起已推出到 GCC 云。

若要进一步阅读本主题，请转到 [Microsoft Teams 中的信息屏障](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>通信合规性

Microsoft Purview 通信合规性允许将用户添加到可配置为检查 Microsoft Teams 通信的范围内策略，以了解攻击性语言、敏感信息以及与内部和法规标准相关的信息。 可以扫描公共和专用 Teams 频道、单个聊天和附件中的聊天通信和关联附件，以帮助最大程度地降低组织中的通信风险。 有关如何配置策略以帮助检测、捕获和采取不适当 Teams 通信操作的详细信息，请参阅 [了解通信合规性](/microsoft-365/compliance/communication-compliance)。

### <a name="sensitivity-labels"></a>敏感度标签

应用 [敏感度标签](/microsoft-365/compliance/sensitivity-labels) 来保护和规范对团队内协作期间创建的敏感组织内容的访问。 例如，应用用于配置团队公共或专用)  (隐私、控制来宾访问和外部共享以及管理来自非托管设备的访问的标签。 有关详细信息，请查看 [Microsoft Teams 中的敏感度标签](sensitivity-labels.md)。

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Microsoft Purview 数据丢失防护 (DLP) 

数据丢失防护 (Microsoft Teams 中的 DLP) ，以及 Microsoft Purview 的较大 DLP 案例，围绕在保护敏感文档和数据方面的业务准备情况展开。 无论你对消息或文档中的敏感信息有顾虑，DLP 策略都可以帮助确保用户不会与错误的人共享此敏感数据。

有关 Teams 中的数据丢失防护的信息，请查看 [适用于 Microsoft Teams 的 DLP](/microsoft-365/compliance/dlp-microsoft-teams)。 DLP 关注的一篇好文章是 [了解数据丢失防护](/microsoft-365/compliance/dlp-learn-about-dlp)。

### <a name="customer-key"></a>客户密钥

Microsoft 365 提供针对内容的服务加密的附加加密层。 使用你提供的密钥，客户密钥在 Microsoft Teams 中加密多种不同类型的数据。 在应用程序级别使用客户密钥，客户密钥会加密存储在 SharePoint Online 中的 Teams 文件。 有关信息，请参阅 [Microsoft Purview 客户密钥的服务加密](/microsoft-365/compliance/customer-key-overview)。

在租户级别使用客户密钥，客户密钥加密：
- Teams 聊天消息 (1：1 聊天、群集聊天、会议聊天和频道对话) 
- Teams 媒体消息 (图像、代码片段、视频和 wiki 图像) 
- Teams 呼叫和存储在 Teams 存储中的会议录制
- Teams 聊天通知
- Cortana 提供的 Teams 聊天建议
- Teams 状态消息

有关详细信息，请参阅 [租户级别的客户密钥概述](/microsoft-365/compliance/customer-key-tenant-level) ，并阅读 Microsoft Teams 博客，其中介绍了 [现在公共预览版中 Microsoft Teams 的客户密钥支持](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)。 有关租户级别包含客户密钥的Microsoft Purview 信息保护版本的信息，请阅读[“宣布新Microsoft Purview 信息保护功能以了解和保护敏感数据](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

### <a name="retention-policies"></a>保留策略

使用 Microsoft Teams 中的保留策略，既可以保留组织出于法规、法律、业务或其他原因而保留的重要数据，还可以删除与保留无关的内容和通信。 还可以使用保留策略将数据保留一段时间，然后将其删除。 有关详细信息，请查看 [Microsoft Teams 中的保留策略](retention-policies.md)。

### <a name="ediscovery"></a>电子数据展示

电子发现（即电子数据展示）是识别、收集和生成电子存储信息的电子方面， (ESI) 响应法律诉讼或调查中生产的要求。 功能包括事例管理、保存、搜索、分析和导出 Teams 数据。 这包括聊天、消息和文件、会议和通话摘要。 对于 Teams 会议和通话，会在电子数据展示中创建并提供会议和呼叫中发生的事件摘要。

有关如何在Microsoft Purview 合规门户中使用电子数据展示工具搜索 Teams 内容的更多详细信息，请转到以下链接：

- [电子数据展示](/microsoft-365/compliance/manage-legal-investigations)

- [内容搜索](/microsoft-365/compliance/search-for-content)

我们提供了一篇特定于 Teams 的文章，详细了解如何对 [Microsoft Teams 中的内容进行电子数据展示调查](eDiscovery-investigation.md)。

客户可以根据自己的要求利用电子数据展示或 [电子数据展示 (高级) ](/microsoft-365/compliance/office-365-advanced-ediscovery) 。 下表概括列出了这两者之间的差异：

|&nbsp; |电子数据展示  |电子数据展示 (高级)   |
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

在诉讼期间，可能需要将与用户 (保管人) 或团队关联的所有数据保留为不可变数据，以便可以将其用作案件的证据。 为此，可以将用户 (用户邮箱) 或团队置于法定保留状态。 对于团队法定保留，可以保留团队的邮箱：

- In-Place保留 (通过目标查询或筛选的内容将邮箱或网站集的子集保留) 或
- 诉讼保留 (整个邮箱或网站集被搁置) 。

在任一情况下，设置保留后，它确保即使最终用户删除或编辑组邮箱中的频道邮件，该内容的不可变副本也可通过电子数据展示搜索进行维护和提供。 法律保留通常在电子数据展示案例的上下文中适用。

请参阅[保留策略概述](/microsoft-365/compliance/retention-policies)，详细了解Microsoft Purview 合规门户中的保留和保留。 有关法定保留的更多特定于 Teams 的信息，我们还让 [Microsoft Teams 用户或团队处于法定保留状态](legal-hold.md) ，供你了解详细信息。

### <a name="content-search"></a>内容搜索

内容搜索可用于通过丰富的筛选功能搜索所有 Teams 数据。 生成的数据可以导出到特定容器，以获得合规性和诉讼支持。 在有无电子数据展示案例的情况下，均可执行此操作。 这使合规性管理员能够跨所有用户收集 Teams 数据，查看并导出这些数据以供进一步处理。 请参阅[内容搜索](/microsoft-365/compliance/content-search)，详细了解如何在Microsoft Purview 合规门户中对 Microsoft Teams 和其他 Microsoft 365 或Office 365内容进行合规性内容搜索。

> [!TIP]
> 使用内容搜索，可以根据需要筛选到仅限 Microsoft Teams 的内容，例如聊天和频道消息、会议和通话。

如果要进一步了解有关配置内容搜索的 Teams 特定信息，请查看 [Microsoft Teams 中的内容搜索](content-search.md)。

### <a name="auditing"></a>审核

审核日志搜索直接插入到Microsoft Purview 合规门户中，并允许导出特定工作负载或泛型事件集以供管理员在无限审核时间线内使用和调查，从而能够设置警报以及报告审核事件。 可以为Microsoft Purview 合规门户中的所有审核日志数据设置警报，并筛选和导出此数据以供进一步分析。 若要详细了解如何在Microsoft Purview 合规门户中搜索 Microsoft Teams 事件，请[参阅 Microsoft Teams 中事件的审核日志](audit-log-events.md)。

## <a name="privacy"></a>隐私

在 Microsoft，保护数据是我们的首要任务。 若要了解我们的隐私做法，请阅读：  

- [Microsoft 隐私](https://www.microsoft.com/trust-center/privacy)
- [我们在 Microsoft Teams 中对隐私和安全的承诺](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [对于 IT 专业人员：Microsoft Teams 中的隐私和安全](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>信息保护体系结构

下图指示 Teams 数据引入 Exchange 和 SharePoint for Teams 文件和消息的流。

> [!div class="mx-imgBorder"]
> ![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下图指示 Teams 会议的引入流以及将数据调用到 Exchange。

> [!div class="mx-imgBorder"]
> ![Teams 会议的工作流和向 Exchange 调用数据的示意图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 最多可以有 24 小时的延迟来发现 Teams 内容。

## <a name="licensing"></a>许可

在信息保护功能方面，Microsoft 365 订阅、Office 365订阅和关联的独立许可证将确定可用功能集。

有关确定许可需要实现安全性和合规性功能的信息，请查看安全性和合规性功能的 [许可要求](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 。

> [!NOTE]
> 无需在Microsoft Purview 合规门户中启用内容搜索、电子数据展示 (标准) 和电子数据展示 (高级) 即可正常工作。 有关详细信息，请参阅 [Microsoft 365 电子数据展示解决方案](/microsoft-365/compliance/ediscovery)。

## <a name="location-of-data-in-teams"></a>Teams 中的数据的位置

Teams 中的数据位于与 Microsoft 365 或 Office 365 组织关联的地理区域中。 若要查看当前支持哪些区域，请查看 [Microsoft Teams 中的数据位置](location-of-data-in-teams.md)。

如果需要查看租户的哪个区域包含数据，请转到 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home) > **Settings** > **组织配置文件**。 向下滚动到 **数据位置**。

> [!div class="mx-imgBorder"]
> ![数据位置表的屏幕截图，包括管理中心中的 Teams。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>合规性标准

Teams 使用以下标准： [ISO 27001](/microsoft-365/compliance/offering-iso-27001)、 [ISO 27018](/microsoft-365/compliance/offering-iso-27018)、 [SSAE18 SOC 1 和 SOC 2](/microsoft-365/compliance/offering-soc)、 [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech) 和 [EU Model 子句 (EUMC) ](/microsoft-365/compliance/offering-eu-model-clauses)。 在 Microsoft 合规性框架中，Microsoft 将 Microsoft 365 和Office 365应用程序和服务分类为四个类别。 每个类别由特定合规性承诺定义，必须满足 Microsoft 365 或Office 365服务或相关 Microsoft 服务才能在该类别中列出。

可以在 [数据保护资源](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)中找到详细信息。 Teams 还支持云安全联盟合规性。

## <a name="related-topics"></a>相关主题

[Microsoft 365 安全性](/microsoft-365/security/)

[Microsoft 365 符合性](/microsoft-365/compliance/)

[Microsoft 合规性产品/服务](/microsoft-365/compliance/offering-home)
