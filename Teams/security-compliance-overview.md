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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20b1ff0536117516484a1d9f54fc49fedbab2e12
ms.sourcegitcommit: 4e6b39e7421ea6eb03c524bb6b8e597c1966bad1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "30056520"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和合规性概述
======================================================

Microsoft Teams 建立在 Office 365 超大规模企业级云之上，提供我们的客户期望的高级安全性和合规性功能。

符合层 D 的团队。 这包括以下标准：ISO 27001、ISO 27018、SSAE16 SOC 1 和 SOC 2、HIPAA 以及欧盟模型条款 (EUMC)。 在 Microsoft 合规性框架中，Microsoft 将 Office 365 应用和服务分类为四种类别。 每种类别均按特定的合规性承诺定义，Office 365 服务或相关的 Microsoft 服务必须履行这些承诺才能列在相应类别中。

默认情况下启用合规性类别 C 和 D 中的服务，它们有行业领先的合规性承诺。 类别 A 和 B 中的服务提供了针对整个组织开启或关闭这些服务的控制功能。 有关详细信息，请参阅[行业标准和规章的合规性框架](https://go.microsoft.com/fwlink/?linkid=855777)。 Teams 还支持云安全联盟合规性。

Teams 还强制执行团队范围和组织范围的双重身份验证、通过 Active Directory 进行单一登录以及对正在传输的数据和静态数据加密。 文件存储在 SharePoint 中，并会进行 SharePoint 加密。 笔记存储在 OneNote 中，并会进行 OneNote 加密。 工作组 SharePoint 网站中存储的 OneNote 数据。 Wiki 选项卡可以还用于笔记记录和团队 SharePoint 网站中还存储它的内容。

我们还增加了以下支持：审核日志搜索、针对频道、聊天和文件的电子数据展示和法定保留，以及通过 Microsoft Intune 进行移动应用管理。 转到 Office 365 安全性 & 合规性中心管理这些设置。 

## <a name="auditing-and-reporting"></a>审核和报告

审核日志搜索插入到 Office 365 安全性 & 合规中心的权限，并公开能力设置通知和/或导出的工作负荷特定或泛型事件设置用于管理使用和调查，跨报告使可用，审核事件不受限制的审核时间线。 审核日志的所有数据提供有关 Office 365 安全性 & 合规中心内的通知的设置以及筛选和导出供进一步分析。 请参阅此[链接](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)可了解有关如何执行审核日志搜索的 Office 365 安全性 & 合规性中心中的 Microsoft 团队事件详细信息。 

## <a name="compliance-content-search"></a>合规性内容搜索

内容搜索可以用于通过筛选功能的富所有团队数据都搜索和导出到特定合规性和诉讼支持的容器。 在有无电子数据展示案例的情况下，均可执行此操作。 这样，合规性管理员可以跨所有用户收集团队数据、 查看和导出进行进一步处理。 请参阅此[链接](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4)可了解有关如何管理 Office 365 安全性 & 合规性中心中的 Microsoft 团队内容法规遵从性内容搜索。 

提示： 可以使用类型的 Microsoft 团队进行筛选，通过仅内容的 Microsoft 团队即聊天和通道消息、 会议和呼叫。 

## <a name="ediscovery"></a>电子数据展示

电子数据展示是为了回应法律诉讼或调查中提供文件的要求而找出、收集和生成电子方式存储的信息 (ESI) 的电子操作过程。 功能包括案例管理、 保留、 搜索、 分析和团队数据导出。 这包括聊天、 消息和文件、 会议和呼叫摘要。 有关创建和电子数据展示中可用团队会议和呼叫、 会议和呼叫中发生事件的摘要。 

有关如何执行安全 & 合规性中心中的电子数据展示和运行团队内容法规遵从性内容搜索的详细信息，请转到以下链接： 

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

在诉讼，它通常所需的所有数据相关都联的用户 （管理员） 或团队永久保留，因此可用作证据的大小写。 这被通过发出合法保留的用户 （用户邮箱） 或团队。 时团队中的任何团队置于就地保留 （至目标的查询或筛选的内容邮箱或网站集的子集） 或诉讼保留 （整个邮箱或网站集），组邮箱置于保留项。 这样可以确保即使最终用户删除或编辑组邮箱到 ingested 的通道消息，该内容的变副本是维护和电子数据展示搜索中可用。 通常在电子数据展示案例的上下文中应用法定保留。 请参阅[此](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a)帮助文章以了解有关保留和 Office 365 安全性 & 合规性中心中的保留项的详细信息。 

## <a name="information-protection-architecture-for-microsoft-teams"></a>信息的 Microsoft 团队保护体系结构。 

如下图所示的引入数据流团队对 Exchange 和 SharePoint 的工作组文件和消息。 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

如下图所示的引入流程团队会议和呼叫数据到 Exchange。

![团队会议和呼叫数据到 Exchange 的工作流关系图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 可以有最多 24 小时制延迟工作组的内容。

<a name="licensing"></a>许可
---------------

涉及到信息保护功能时，Office 365 订阅和关联的单独许可证将确定功能集。


| 信息保护功能 | Office 365 商业协作版 | Office 365 商业高级版 | Office 365 企业版 E1 | Office 365 企业版 E3/E4 | Office 365 企业版 E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              存档              |               -                |              -              |            -             |             是              |           是             |
|        就地电子数据展示        |               -                |              -              |            -             |             是              |           是            |
|        高级电子数据展示        |               -                |              -              |            -             |              -              |           是            |
|            法定保留             |               -                |              -              |            -             |             是              |           是             |
|     合规性内容搜索     |               -                |             是              |           是             |             是              |           是            |
|      审核和报告       |              是               |             是              |           是             |             是              |           是            |
|       条件的访问\*        |              是                |             是              |           是             |             是              |           是            |

> [!NOTE]
> \*条件访问需要额外的许可证


| |  |  |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织是否有所需的许可证来满足合规性和安全性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |后续步骤         |查看贵组织的当前许可，并确认它满足合规性和安全性的所有业务要求。         |

然后再启用这些功能，确保您在 Office 365 管理中心中有权安全 & 合规性中心。 默认情况下，租户管理员有访问权限。

内容搜索和电子数据展示不需要安全 & 合规性中心中的启用。

<a name="location-of-data-in-teams"></a>Teams 中的数据的位置
-------------------------

Teams 中的数据位于与你的 Office 365 租户关联的地理区域。 目前，团队支持澳大利亚、 加拿大、 印度、 日本、 英国、 美国、 APAC 和 EMEA 区域。 

> [!IMPORTANT]
> 团队目前提供数据住所中澳大利亚、 加拿大、 印度、 日本和英国的仅新租户。 新租户的定义是，该租户中没有任何一个用户登录过 Teams。 澳大利亚、 印度和日本从现有租户将继续将其团队数据存储在 APAC 区域。 在加拿大和英国的现有租户会在美国存储其数据和 EMEA 区域，分别。

要详细了解为 Teams 启动英国和印度数据驻留的信息，请阅读 Ansuman Acharya 的博客文章 [Microsoft Teams 启动印度数据驻留，其他地理位置不久将启动](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)。 

有关团队加拿大数据住所详细信息，请阅读 Varun Sagar 博客文章， [Microsoft 团队启动加拿大数据住所、 澳大利亚和日本即将提供](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)。 

若要了解有关团队澳大利亚和日本数据住所的启动的详细信息，请阅读 Varun Sagar 博客文章， [Microsoft 团队启动澳大利亚和日本数据居住权](https://go.microsoft.com/fwlink/?linkid=867773)。 

若要查看的区域存储租户数据，转到[Office 365 管理中心](https://portal.office.com/adminportal/home) > **设置** > **组织配置文件**。 向下滚动到“**数据位置**”。 

![团队，包括 Office 365 管理中心中的数据位置表的屏幕截图。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>条件访问策略团队如何工作？
-------------------------

Microsoft 团队严重依赖 Exchange Online、 SharePoint Online 和 Skype 业务 online 核心工作效率方案，如会议、 日历、 互操作的聊天和文件共享。 时用户直接登录到 Microsoft 团队的任何客户端上，为这些云应用程序设置的条件的访问策略应用于的 Microsoft 团队。 

单独的 Microsoft 团队支持作为云应用程序在 Azure Active Directory 条件访问策略。 当用户登录时，为 Microsoft 团队云应用程序设置的条件的访问策略将适用于 Microsoft 团队。 但是，不正确的策略，如 Exchange Online 和 SharePoint Online 的其他应用程序，用户可能仍将能够直接访问这些资源。 有关设置 azure 门户中的某个条件的访问策略的详细信息，请转到: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Windows 和 Mac 的 Microsoft 团队桌面客户端支持现代身份验证。 现代身份验证将跨平台基于在 Azure Active Directory 身份验证库 (ADAL) Microsoft Office 客户端应用程序登录。

Microsoft 团队桌面应用程序支持 AppLocker。  有关 AppLocker 先决条件的详细信息，请参阅： 要求使用 AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

<a name="privacy-in-teams"></a>Teams 中的隐私
--------------------------

作为 Office 365 的客户，你拥有并控制你的数据。 除了为你提供你已订阅的服务外，Microsoft 不会将你的数据用于任何其他用途。 作为服务提供商，我们不会扫描你的电子邮件、文档或团队来做广告或用于与服务无关的用途。 Microsoft 无权访问上载的内容。 对于 OneDrive for Business 和 SharePoint Online，客户数据位于租户中。

请在 [Office 365 信任中心](https://go.microsoft.com/fwlink/?linkid=855779)详细查看我们的信任和安全相关的信息。 Teams 与 Office 365 信任中心遵循相同的指导和原则。
