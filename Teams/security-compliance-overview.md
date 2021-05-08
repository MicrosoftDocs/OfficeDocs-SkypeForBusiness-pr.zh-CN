---
title: 安全性和符合性概述
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: 概述安全Microsoft Teams功能，包括隐私和加密、审核和报告等。
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
ms.openlocfilehash: bfa593aaeabe8d7aab9446a1070134b267ea6ef4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107608"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>安全与合规Microsoft Teams

> [!IMPORTANT]
> 若要了解如何在 **COVID-19** 爆发期间，在每个人在家工作时最好地确保安全，请阅读以下文章：
>  - [安全团队为支持在家办公需完成的 12 大任务](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分离隧道为远程用户优化 Microsoft 365 或 Office 365 连接性](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新时间：2020 年 4 月 2 Teams[安全指南](teams-security-guide.md)


Microsoft Teams基于超大规模Microsoft 365 Office 365云，提供客户期望的高级安全性和符合性功能。 有关规划安全方案或Microsoft 365 Office 365，安全[路线图是一](/microsoft-365/security/office-365-security/security-roadmap)个很好的起点。 有关规划安全与Microsoft 365符合性Office 365，可以从安全与&[开始](/microsoft-365/compliance/plan-for-security-and-compliance)。


本文将提供有关特定于Teams安全性和符合性的进一步信息。 不要错过以下有关安全性和符合性的 Microsoft Mechanics 视频：

- [Microsoft Teams IT 的"](https://youtu.be/91lHNKVVvQ4)基本信息：安全性和合规性 (12：42 分钟) 
- [Microsoft Teams](https://www.youtube.com/watch?v=Km4T4hMM__k) 10：54 (安全与合规性控制) 

> [!IMPORTANT]
> 作为客户或Microsoft 365 Office 365，您拥有和控制数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无法访问已上传的内容。 与OneDrive和SharePoint一Microsoft 365一样，客户数据保留在租户内。 可以在 Microsoft 信任中心查看有关我们的信任和安全[相关信息。](https://microsoft.com/trustcenter) Teams遵循与 Microsoft 信任中心相同的指南和原则。

## <a name="security"></a>安全性

Teams实施团队范围和组织范围的双因素身份验证、通过 Active Directory 的单一登录，以及传输中和静态数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。 OneNote数据存储在团队或SharePoint中。 "Wiki"选项卡还可用于做笔记，其内容也存储在工作组SharePoint网站。

阅读[标识模型和身份验证](identify-models-authentication.md)，深入了解身份验证和Teams，以及新式验证的工作原理将尤其[](sign-in-teams.md)有助于新式验证。

由于Teams与 SharePoint、OneNote、Exchange 等部门合作，因此，应该能够Microsoft 365或Office 365安全性。 若要了解有关详细信息，请阅读如何配置 Microsoft 365[或 Office 365，提高安全性](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前 [，专用通道](private-channels.md) 支持有限的安全性和符合性功能。 即将推出对专用通道中整套安全性和符合性功能的支持。

### <a name="advanced-threat-protection-atp"></a>ATP (高级威胁防护) 

高级威胁防护 (ATP) 适用于 Microsoft Teams，以及 SharePoint 和 OneDrive，这些应用程序与 Teams 集成以用于内容管理。 ATP 允许确定这些应用程序中的内容在本质上是否恶意，并阻止用户访问此内容。

在检测后如何管理受影响的内容，由你在应用或Microsoft 365 Office 365。 强烈建议在配置 ATP 时考虑所有应用程序，对于进一步阅读，[适用于 SharePoint、OneDrive](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)和 Microsoft Teams 的 ATP 将包含如何开始的详细信息。

### <a name="safe-links"></a>保险箱链接

虽然目前，高级威胁防护 (ATP) 安全链接在 Microsoft Teams 中不可用，但现在通过技术采用计划 (TAP [](/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide)) 提供公共预览版，虽然尚未设置公开发布的发布日期，但我们将在该时间到来时更新本文。 同时，有关链接或Microsoft 365 Office 365 保险箱的信息，请查看[ATP 保险箱链接。](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) ATP 保险箱 1 和[ATP 计划 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)中均提供 ATP 链接。

### <a name="safe-attachments"></a>保险箱附件

保险箱附件是一项功能，旨在通过检查和检测恶意附件来增强用户安全性。 全局管理员或安全管理员会创建[](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide)策略来处理这些可疑的恶意附件，以防止它们发送给用户、单击这些附件并采取行动。 保险箱附件保护适用于 SharePoint、OneDrive 和 Microsoft Teams，Microsoft 365 或 Office 365 高级威胁防护计划 1 和[2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)具有此功能。 在 Microsoft Defender for 保险箱 的"附件"中阅读有关附件保险箱帮助保护组织[Office 365。](/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>安全评分

Microsoft 安全评分是组织安全态势的度量，数字越高，表示采取的改进措施更多。 可以在安全中心的 Microsoft 365[找到](https://security.microsoft.com/securescore)它。 遵循安全评分建议可以保护组织免受威胁。 在安全中心内Microsoft 365仪表板中，组织可以监视和Microsoft 365标识、应用和设备的安全性。 Microsoft Teams安全评分建议，建议管理员在平台上监视其安全状态。

安全评分可帮助组织：
- 报告组织安全态势的当前状态。
- 通过提供可发现性、可见性、指导和控制性来改善其安全状况。
- 与基准进行比较，并建立关键绩效指标 (KPI) 。


### <a name="how-conditional-access-policies-work-for-teams"></a>条件访问策略如何适用于Teams

Microsoft Teams主要依赖于 Exchange Online、SharePoint 和 Skype for Business Online 实现核心工作效率方案，例如会议、日历、互操作聊天和文件共享。 为这些云应用设置的条件访问策略适用于Microsoft Teams客户端上直接登录 Microsoft Teams应用。

Microsoft Teams条件访问策略中单独支持将 Azure Active Directory 作为云应用。 为云应用设置的条件访问Microsoft Teams用户登录Microsoft Teams应用。 但是，如果没有对其他应用（如 Exchange Online 和 SharePoint）的正确策略，用户仍可能能够直接访问这些资源。 有关在 Azure 门户中设置条件访问策略的信息，请参阅快速[Azure Active Directory。](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams和 Mac 的Windows客户端支持新式身份验证。 新式身份验证基于 ADAL 的 Azure Active Directory 身份验证库 (ADAL) 跨Microsoft Office客户端应用程序。

Microsoft Teams桌面应用程序支持 AppLocker。  有关 AppLocker 先决条件详细信息，请参阅： [使用 AppLocker 的要求](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

## <a name="compliance"></a>合规性

Teams 提供广泛的信息来帮助你处理合规性领域，包括通道、聊天和附件的通信符合性、保留策略、数据丢失防护 (DLP) 、针对通道、聊天和文件的电子数据展示和法定保留、审核日志 搜索以及使用 Microsoft Intune 的移动应用程序管理。 我们在下面提供了所有这些主题的一些信息，你可以转到Microsoft 365[中心](https://compliance.microsoft.com)来管理这些设置。

### <a name="information-barriers"></a>信息屏障

信息屏障是 Teams 管理员实施的策略，用于执行一些操作，例如 (当不需要人员或组相互通信时，或者出于法规原因阻止他们这样做) ，它还允许你设置与查找和电子数据展示 () 下面介绍的内容相关的策略。 这些策略可能会影响 1 对 1 聊天、群组聊天或团队级别的用户。 信息屏障功能在公有云中可用，从 2021 年 1 月开始，它已在云中GCC推出。

有关本主题的进一步阅读，请转到中[的信息Microsoft Teams。](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>通信合规性

在 Microsoft 365 中的通信符合性允许你将用户添加到范围内策略，这些策略可以配置为检查 Microsoft Teams 通信中是否包含冒犯性语言、敏感信息以及与内部和法规标准相关的信息。 可以扫描公共和专用聊天Teams聊天通信和相关附件、个人聊天和附件，以帮助最大程度地降低组织的通信风险。 若要详细了解如何配置策略来帮助检测、捕获不适当的通信Teams采取操作，请参阅 Microsoft 365 中的[通信符合性](/microsoft-365/compliance/communication-compliance)。

### <a name="retention-policies"></a>保留策略

使用 Microsoft Teams 中的保留策略可以保留组织出于法规、法律、业务或其他原因保留的重要数据，以及删除与保留不相关的内容和通信。 还可使用保留策略将数据保留一段时间，然后将其删除。 有关详细信息，请参阅中的[保留Microsoft Teams。](retention-policies.md)

## <a name="sensitivity-labels"></a>敏感度标签

应用 [敏感度标签](/microsoft-365/compliance/sensitivity-labels) ，以保护并管理对在团队内协作期间创建的敏感组织内容的访问。 例如，应用用于配置团队 (或) 隐私、控制来宾访问和外部共享以及管理来自非托管设备的访问的标签。 有关详细信息，请查看中[敏感度标签Microsoft Teams。](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>DLP (数据丢失防护) 

Microsoft Teams 中的数据丢失防护 (DLP) ，以及适用于 Microsoft 365 或 Office 365 的更大 DLP 案例，围绕保护敏感文档和数据的业务准备情况。 无论您对邮件或文档中的敏感信息有顾虑，DLP 策略都有助于确保用户不会与错误人员共享此敏感数据。

有关在数据中防止数据丢失Teams，请查看 DLP for [Microsoft Teams。](/microsoft-365/compliance/dlp-microsoft-teams) 有关 O365 DLP 问题的良好文章是 [数据丢失防护概述](/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>电子数据展示

电子发现或电子数据展示是电子方面，用于识别、收集和生成电子存储的信息 (ESI) 以响应法律诉讼或调查的生产请求。 功能包括案例管理、保留、搜索、分析和导出数据Teams导出。 这包括聊天、消息和文件、会议摘要和呼叫摘要。 对于Teams呼叫，将创建会议和通话中发生的事件的摘要，并可在电子数据展示中查看。

若要详细了解如何在安全Microsoft 365 Office 365中执行电子数据展示或电子数据展示，以及如何针对 Teams 内容运行合规性内容搜索，请转到以下链接：

 - [电子数据展示](/microsoft-365/compliance/manage-legal-investigations)

 - [内容搜索](/microsoft-365/compliance/search-for-content)

我们有一Teams一篇文章，了解来宾到来宾聊天的电子[数据展示](eDiscovery-investigation.md)。

客户可以按要求利用电子数据展示[Advanced eDiscovery](/microsoft-365/compliance/office-365-advanced-ediscovery)功能。 下表概括列出了这两者之间的差异：

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

请参阅[保留策略概述](/microsoft-365/compliance/retention-policies)，详细了解保留和保留Microsoft 365中心。 有关Teams保留的更多特定信息，我们还有一个Microsoft Teams保留用户或[](legal-hold.md)团队，供你了解详细信息。

### <a name="compliance-content-search"></a>合规性内容搜索

内容搜索可用于通过丰富的筛选Teams搜索所有数据。 生成的数据可以导出到特定容器，以用于合规性和诉讼支持。 在有无电子数据展示案例的情况下，均可执行此操作。 这样，合规性管理员Teams所有用户收集数据，查看并导出这些数据进行进一步处理。 请参阅内容[搜索](/microsoft-365/compliance/content-search)，详细了解如何针对 Microsoft Teams 和其他 Microsoft 365 或 Office 365 内容执行合规性Microsoft 365搜索。

> [!TIP]
> 使用内容搜索，可向下筛选Microsoft Teams内容，例如聊天和频道消息、会议和呼叫（如有必要）。

如果想进一步Teams内容搜索的特定信息，请查看中的内容[Microsoft Teams。](content-search.md)

### <a name="auditing-and-reporting"></a>审核和报告

审核日志搜索直接插入到 Microsoft 365 合规中心，通过允许导出工作负荷特定或通用事件集，以便管理员在无限制的审核时间线上使用和调查，从而设置警报以及报告审核事件。 可以在合规中心内设置所有审核日志Microsoft 365警报，并筛选和导出此数据进行进一步分析。 请参阅搜索[审核日志，](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)详细了解如何针对用户或用户执行审核Microsoft 365 Office 365。 若要详细了解如何搜索 Microsoft Teams 合规性中心Microsoft 365事件，我们还将打开审核[Teams供你](audit-log-events.md)查看。

## <a name="customer-key"></a>客户密钥

Microsoft 365为内容提供基于服务加密的附加加密层。 使用提供的密钥，客户密钥可加密数据中多种不同类型的Microsoft Teams。 在应用程序级别使用客户密钥，客户密钥Teams存储在 SharePoint Online 中的文件。 有关信息，请参阅 [使用客户密钥 进行服务加密](/microsoft-365/compliance/customer-key-overview)。 

在租户级别使用客户密钥时，客户密钥会加密：
- Teams聊天消息 (一对一聊天、群组聊天、会议聊天和频道) 
- Teams媒体消息 (图像、代码片段、视频和 Wiki 图像) 
- Teams存储中存储的呼叫和Teams录制
- Teams聊天通知
- Teams Cortana 提供聊天建议
- Teams状态消息 有关详细信息，请参阅租户级别的[Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level)客户密钥概述，并阅读 Microsoft Teams 博客，其中介绍了客户密钥对[Microsoft Teams 的支持，](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)现在处于公共预览状态。 有关在租户级别包含客户密钥的 Microsoft 信息保护版本的信息，请阅读宣布推出新的 Microsoft 信息保护功能，了解 [和保护敏感数据](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

## <a name="privacy"></a>隐私

在 Microsoft，保护你的数据是我们的首要任务。 若要了解隐私惯例，请阅读：  

- [Microsoft 隐私](https://www.microsoft.com/trust-center/privacy)
- [我们对安全与隐私的承诺Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [对于 IT 专业人员：隐私和安全Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>信息保护体系结构

下图指示数据对Teams和消息的Exchange SharePoint Teams流。

> [!div class="mx-imgBorder"]
> ![将数据Teams到Exchange SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下图指示会议数据的Teams和调用数据以Exchange。

> [!div class="mx-imgBorder"]
> ![会议Teams调用数据的工作流图Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 发现内容可能会延迟多达 24 Teams。

## <a name="licensing"></a>许可

就信息保护功能来说，Microsoft 365订阅、Office 365和关联的独立许可证将确定可用的功能集。

有关确定许可需要实现安全性和符合性功能的信息，请查看 [安全性和符合性功能](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 的许可要求。

> [!NOTE]
> 无需在安全与合规中心启用内容搜索&电子数据展示。

## <a name="location-of-data-in-teams"></a>Teams 中的数据的位置

Teams 中的数据位于与 Microsoft 365 或 Office 365 组织关联的地理区域中。 若要了解当前支持的区域，请查看数据在 Microsoft Teams[中的位置](location-of-data-in-teams.md)。

如果需要查看哪个区域存储租户的数据，请转到管理中心Microsoft 365"设置 [](https://portal.office.com/adminportal/home)  >    >  **配置文件"。** 向下滚动到 **数据位置**。

> [!div class="mx-imgBorder"]
> !["数据位置"表的屏幕截图，Teams管理中心内的数据位置](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>符合性标准

Teams采用以下标准[：ISO 27001、ISO](/microsoft-365/compliance/offering-iso-27001) [27018、SSAE18](/microsoft-365/compliance/offering-iso-27018) [SOC 1 和 SOC 2、HIPAA](/microsoft-365/compliance/offering-soc)和 EUMC ([EUMC) 。 ](/microsoft-365/compliance/offering-eu-model-clauses) [](/microsoft-365/compliance/offering-hipaa-hitech) 在 Microsoft 符合性框架中，Microsoft 将Microsoft 365 Office 365和服务分为四个类别。 每个类别由特定合规性承诺定义，对于要列在该类别中的 Microsoft 365 服务Office 365或相关的 Microsoft 服务，必须满足这些承诺。

可以在数据保护资源 [中找到详细信息](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)。 Teams 还支持云安全联盟合规性。

## <a name="related-topics"></a>相关主题

[Microsoft 365安全性](/microsoft-365/security/)

[Microsoft 365符合性](/microsoft-365/compliance/)

[Microsoft 合规性产品/服务](/microsoft-365/compliance/offering-home)