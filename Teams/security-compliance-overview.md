---
title: 安全性和符合性概述
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Microsoft Teams 安全性和符合性功能的概述，包括隐私和加密、审核和报告等。
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
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 36cb67dc73177678206e5d5865ba145414ae37a9
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836919"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和符合性

> [!IMPORTANT]
> 若要了解如何在 **COVID-19** 爆发期间，在每个人在家工作时最好地确保安全，请阅读以下文章：
>  - [安全团队为支持在家办公需完成的 12 大任务](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分离隧道为远程用户优化 Microsoft 365 或 Office 365 连接性](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新时间：2020 年 4 月 2 日 [：Teams 安全指南](teams-security-guide.md)


Microsoft Teams 构建在 Microsoft 365 和 Office 365 超大规模企业级云上，提供客户期望的高级安全性和合规性功能。 有关在 Microsoft 365 或 Office 365 中规划安全性详细信息，安全 [路线图是一](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) 个很好的起点。 有关在 Microsoft 365 或 Office 365 中规划合规性详细信息，可以从安全与合规& [开始](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)。


本文将提供有关特定于 Teams 的安全性和符合性的进一步信息。 不要错过以下有关安全性和符合性的 Microsoft Mechanics 视频：

- [适用于 IT 的 Microsoft Teams 协作版： (](https://youtu.be/91lHNKVVvQ4) 12：42 分钟) 
- [在](https://www.youtube.com/watch?v=Km4T4hMM__k) 10：54 分钟 (Microsoft Teams 安全性和合规性控制) 

> [!IMPORTANT]
> 作为 Microsoft 365 或 Office 365 的客户，你拥有和控制你的数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无法访问已上传的内容。 与 Microsoft 365 中的 OneDrive 和 SharePoint 一样，客户数据保留在租户内。 可以在 Microsoft 信任中心查看有关我们的信任和安全[相关信息。](https://microsoft.com/trustcenter) Teams 遵循与 Microsoft 信任中心相同的指南和原则。

## <a name="security"></a>安全性

Teams 强制实施团队范围和组织范围的双因素身份验证、通过 Active Directory 单一登录，以及传输中和静态数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。 OneNote 数据存储在团队 SharePoint 网站中。 "Wiki"选项卡还可用于做笔记，其内容也存储在团队 SharePoint 网站中。

阅读[标识模型和身份验证](identify-models-authentication.md)，深入了解身份验证和 Teams，以及新式[](sign-in-teams.md)验证的工作原理将尤其有助于新式验证。

由于 Teams 与 SharePoint、OneNote、Exchange 等部门合作，因此应熟悉 Microsoft 365 或 Office 365 中的安全性。 若要了解有关详细信息，请阅读如何配置 [Microsoft 365 或 Office 365 组织，提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前 [，专用通道](private-channels.md) 支持有限的安全性和符合性功能。 即将推出对专用通道中整套安全性和符合性功能的支持。

### <a name="advanced-threat-protection-atp"></a>ATP (高级威胁防护) 

高级威胁防护 (ATP) 适用于 Microsoft Teams，以及 SharePoint 和 OneDrive（与 Teams 集成进行内容管理的应用程序）。 ATP 允许确定这些应用程序中的内容在本质上是否恶意，并阻止用户访问此内容。

检测后如何管理受影响的内容，由你在 Microsoft 365 或 Office 365 中所选的设置决定。 我们强烈建议你在配置 ATP 时考虑所有应用程序，为进一步阅读， [适用于 SharePoint、OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 和 Microsoft Teams 的 ATP 将详细介绍如何入门。

### <a name="safe-links"></a>安全链接

虽然目前 Microsoft Teams 中未提供高级威胁防护 (ATP) 安全链接，但现在通过技术采用计划 ([](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) TAP) 提供公共预览版，虽然尚未设置公开发布的发布日期，但我们将在该时间到来时更新本文。 同时，有关 Microsoft 365 或 Office 365 安全链接的信息，请查看 [ATP 安全链接](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 ATP 计划 1 和 [ATP 计划 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)中均提供 ATP 安全链接。

### <a name="safe-attachments"></a>安全附件

安全附件是一项功能，旨在通过检查和检测恶意附件来增强用户安全性。 全局管理员或安全管理员会创建[](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide)策略来处理这些可疑的恶意附件，以防止它们发送给用户、单击这些附件并采取行动。 安全附件保护适用于 SharePoint、OneDrive 和 Microsoft Teams，Microsoft 365 或 Office 365 高级威胁防护计划 1 和 [2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) 具有此功能。 在 [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)中的安全附件中阅读有关安全附件及其如何帮助保护组织的信息。

### <a name="secure-score"></a>安全评分

Microsoft 安全评分是组织安全态势的度量，数字越高，表示采取的改进措施更多。 可以在 [Microsoft 365 安全中心找到它](https://security.microsoft.com/securescore)。 遵循安全评分建议可以保护组织免受威胁。 在 Microsoft 365 安全中心的集中式仪表板中，组织可以监视并处理其 Microsoft 365 标识、应用和设备的安全性。 Microsoft Teams 现在提供安全评分建议，建议管理员监视他们在平台上的安全状态。

安全评分可帮助组织：
- 报告组织安全态势的当前状态。
- 通过提供可发现性、可见性、指导和控制性来改善其安全状况。
- 与基准进行比较，并建立关键绩效指标 (KPI) 。


### <a name="how-conditional-access-policies-work-for-teams"></a>条件访问策略在 Teams 中如何工作

Microsoft Teams 在很大程度上依赖于 Exchange Online、SharePoint 和 Skype for Business Online 实现核心工作效率方案，例如会议、日历、互操作聊天和文件共享。 当用户在任何客户端上直接登录 Microsoft Teams 时，为这些云应用设置的条件访问策略将应用于 Microsoft Teams。

Azure Active Directory 条件访问策略中单独支持 Microsoft Teams 作为云应用。 为 Microsoft Teams 云应用设置的条件访问策略适用于用户登录时 Microsoft Teams。 但是，如果没有 Exchange Online 和 SharePoint 等其他应用程序的正确策略，用户仍可能能够直接访问这些资源。 有关在 Azure 门户中设置条件访问策略的信息，请参阅 [Azure Active Directory 快速入门](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

适用于 Windows 和 Mac 的 Microsoft Teams 桌面客户端支持新式身份验证。 新式身份验证基于 ADAL 的 Azure Active Directory 身份验证库 (ADAL) 跨Microsoft Office客户端应用程序。

Microsoft Teams 桌面应用程序支持 AppLocker。  有关 AppLocker 先决条件详细信息，请参阅： [使用 AppLocker 的要求](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

## <a name="compliance"></a>合规性

Teams 提供广泛的信息来帮助你处理合规性领域，包括频道通信符合性、聊天和附件通信合规性、保留策略、数据丢失防护 (DLP) 、通道、聊天和文件电子数据展示和法定保留、审核日志 搜索，以及 Microsoft Intune 的移动应用程序管理。 我们在下面提供了所有这些主题的一些信息，你可以转到 [Microsoft 365](https://compliance.microsoft.com) 合规中心来管理这些设置。

### <a name="information-barriers"></a>信息屏障

信息屏障是 Teams 管理员实施的策略，用于执行一些操作，例如，在不需要人员或组进行相互通信时 (或者出于法规原因阻止他们这样做) ，它还允许你设置与查找和电子数据展示 () 下面介绍的内容相关的策略。 这些策略可能会影响 1 对 1 聊天、群组聊天或团队级别的用户。 信息屏障功能在公有云中可用，从 2021 年 1 月开始，此功能已推出到 GCC 云。

有关本主题的进一步阅读，请转到 [Microsoft Teams 中的信息屏障](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>通信合规性

Microsoft 365 中的通信符合性允许将用户添加到范围内策略，这些策略可以配置为检查 Microsoft Teams 通信中是否包含冒犯性语言、敏感信息以及与内部和法规标准相关的信息。 可以扫描公共和专用 Teams 通道中的聊天通信和相关附件、个人聊天和附件，以帮助最大程度地降低组织的通信风险。 若要详细了解如何配置策略来帮助检测、捕获不适宜的 Teams 通信并采取行动，请参阅 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)中的通信符合性。

### <a name="retention-policies"></a>保留策略

Microsoft Teams 中的保留策略允许保留组织出于法规、法律、业务或其他原因保留的重要数据，以及删除与保留不相关的内容和通信。 还可使用保留策略将数据保留一段时间，然后将其删除。 有关详细信息，请查看 [Microsoft Teams 中的保留策略](retention-policies.md)。

## <a name="sensitivity-labels"></a>敏感度标签

应用 [敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ，以保护并管理对在团队内协作期间创建的敏感组织内容的访问。 例如，应用用于配置团队 (或) 隐私、控制来宾访问和外部共享以及管理来自非托管设备的访问的标签。 有关详细信息，请查看 [Microsoft Teams 中的敏感度标签](sensitivity-labels.md)。

### <a name="data-loss-prevention-dlp"></a>DLP (数据丢失防护) 

Microsoft Teams 中的数据丢失防护 (DLP) ，以及适用于 Microsoft 365 或 Office 365 的更大 DLP 案例，围绕保护敏感文档和数据的业务准备情况。 无论您对邮件或文档中的敏感信息有顾虑，DLP 策略都有助于确保用户不会与错误人员共享此敏感数据。

有关 Teams 中的数据丢失防护的信息，请查看[适用于 Microsoft Teams 的 DLP。](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) 有关 O365 DLP 问题的良好文章是 [数据丢失防护概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>电子数据展示

电子发现或电子数据展示是电子方面，用于识别、收集和生成电子存储的信息 (ESI) 以响应法律诉讼或调查的生产请求。 功能包括 Teams 数据案例管理、保留、搜索、分析和导出。 这包括聊天、消息和文件、会议摘要和呼叫摘要。 对于 Teams 会议和通话，将创建会议和通话中发生的事件的摘要，并可在电子数据展示中查看。

若要详细了解如何在安全中心和合规中心执行 Microsoft 365 或 Office 365 电子数据展示，以及如何针对 Teams 内容运行合规性内容搜索，请转到以下链接：

 - [电子数据展示](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [内容搜索](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

我们有一篇特定于 Teams 的文章，详细了解来宾到来宾聊天的电子 [数据展示](eDiscovery-investigation.md)。

客户可以按要求利用电子数据展示 [或高级](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) 电子数据展示。 下表概括列出了这两者之间的差异：

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

在诉讼期间，您可能需要将与用户管理员 () 或团队关联的所有数据保留为不可变数据，以便它可以用作案例的证据。 为此，可以将用户邮箱 (邮箱) 保留团队。 对于团队法定保留，团队邮箱可以置于以下保留中：

- In-Place通过 () 查询或筛选的内容保留邮箱或网站集的子集，或者
- 整个 (或网站集的"诉讼保留") 。

在任一情况下，设置保留后，它可确保即使最终用户删除或编辑组邮箱中的频道邮件，该内容的不可变副本也通过电子数据展示搜索进行维护和提供。 法定保留通常应用于电子数据展示案例的上下文中。

请参阅 [保留策略概述](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) ，详细了解 Microsoft 365 合规中心的保留和保留。 有关法定保留的更多特定于 Teams 的信息，我们还将 [Microsoft Teams](legal-hold.md) 用户或团队放在法定保留状态，供你了解详细信息。

### <a name="compliance-content-search"></a>合规性内容搜索

内容搜索可用于通过丰富的筛选功能搜索所有 Teams 数据。 生成的数据可以导出到特定容器，以用于合规性和诉讼支持。 在有无电子数据展示案例的情况下，均可执行此操作。 这使合规性管理员能够跨所有用户收集 Teams 数据，查看并导出这些数据进行进一步处理。 请参阅内容 [搜索](https://docs.microsoft.com/microsoft-365/compliance/content-search) ，详细了解如何针对 Microsoft Teams 和 Microsoft 365 合规中心的其他 Microsoft 365 或 Office 365 内容执行合规性内容搜索。

> [!TIP]
> 使用内容搜索，可以筛选到仅 Microsoft Teams 内容，例如聊天和频道消息、会议和通话（如有必要）。

如果希望有关配置内容搜索的更多特定于 Teams 的信息，请查看 Microsoft [Teams 中的内容搜索](content-search.md)。

### <a name="auditing-and-reporting"></a>审核和报告

审核日志搜索直接插入 Microsoft 365 合规中心，通过允许导出工作负荷特定或通用事件集，以便管理员使用和调查无限审核时间线，让你能够设置警报以及报告审核事件。 可以针对 Microsoft 365 合规中心内的所有审核日志数据设置警报，并筛选和导出此数据以进一步进行分析。 请参阅搜索 ["审核日志，](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 详细了解如何针对 Microsoft 365 或 Office 365 执行审核日志搜索。 若要了解有关在 Microsoft 365 合规中心中搜索 Microsoft Teams 事件，我们还在 [Teams](audit-log-events.md) 中打开审核功能，供你查看。

## <a name="customer-key"></a>客户密钥

Microsoft 365 为内容提供附加的加密层，并基于服务加密。 客户密钥使用你提供的密钥在 Microsoft Teams 中加密多种不同类型的数据。 客户密钥在应用程序级别使用客户密钥加密存储在 SharePoint Online 中的 Teams 文件。 有关信息，请参阅 [使用客户密钥 进行服务加密](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)。 

在租户级别使用客户密钥时，客户密钥会加密：
- Teams 聊天消息 (一对一聊天、群组聊天、会议聊天和频道) 
- Teams 媒体 (图像、代码片段、视频和 Wiki 图像) 
- Teams 通话和会议录制存储在 Teams 存储中
- Teams 聊天通知
- Cortana 提供的团队聊天建议
- Teams 状态消息 有关详细信息，请参阅租户级别的 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level) 客户密钥概述，并阅读 Microsoft Teams 博客，其中介绍了 Microsoft Teams 的客户密钥支持现已在公共预览 [版中](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)提供。 有关在租户级别包含客户密钥的 Microsoft 信息保护版本的信息，请阅读宣布推出新的 Microsoft 信息保护功能，了解 [和保护敏感数据](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

## <a name="privacy"></a>隐私

在 Microsoft，保护你的数据是我们的首要任务。 若要了解隐私惯例，请阅读：  

- [Microsoft 隐私](https://www.microsoft.com/trust-center/privacy)
- [我们对 Microsoft Teams 中隐私和安全的承诺](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [对于 IT 专业人员：Microsoft Teams 中的隐私和安全性](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>信息保护体系结构

下图指示 Teams 数据同时流入 Exchange 和 SharePoint 的 Teams 文件和消息流。

> [!div class="mx-imgBorder"]
> ![Teams 数据到 Exchange 和 SharePoint 的工作流图](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下图表示 Teams 会议的流入流，以及将数据调用到 Exchange。

> [!div class="mx-imgBorder"]
> ![Teams 会议和向 Exchange 调用数据的工作流图](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 发现 Teams 内容最多需要 24 小时。

## <a name="licensing"></a>许可

就信息保护功能来说，Microsoft 365 订阅、Office 365 订阅和关联的独立许可证将确定可用的功能集。

有关确定许可需要实现安全性和符合性功能的信息，请查看 [安全性和符合性功能](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 的许可要求。

> [!NOTE]
> 无需在安全与合规中心启用内容搜索&电子数据展示。

## <a name="location-of-data-in-teams"></a>Teams 中的数据的位置

Teams 中的数据位于与 Microsoft 365 或 Office 365 组织关联的地理区域中。 若要了解当前支持的区域，请查看 Microsoft [Teams 中数据的位置](location-of-data-in-teams.md)。

如果需要查看哪个区域存储租户的数据，请转到 [Microsoft 365](https://portal.office.com/adminportal/home)管理中心"设置  >  **组织**  >  **配置文件"。** 向下滚动到 **数据位置**。

> [!div class="mx-imgBorder"]
> !["数据位置"表的屏幕截图，包括管理中心中的 Teams](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>符合性标准

Teams 采用以下标准[：ISO 27001、ISO](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [27018、SSAE18](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SOC 1 和 SOC 2、HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)和 EU MODEL [clauses (EUMC) 。 ](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) [](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech) 在 Microsoft 合规性框架中，Microsoft 将 Microsoft 365 和 Office 365 应用程序和服务分为四个类别。 每个类别由 Microsoft 365、Office 365 服务或相关 Microsoft 服务必须满足的特定合规性承诺定义，并列在该类别中。

可以在数据保护资源 [中找到详细信息](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)。 Teams 还支持云安全联盟合规性。

## <a name="related-topics"></a>相关主题

[Microsoft 365 安全性](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 符合性](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft 合规性产品/服务](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
