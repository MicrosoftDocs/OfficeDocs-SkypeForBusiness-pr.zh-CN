---
title: Microsoft 团队系统必备组件 |依赖项应用升级
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: 使用本指南可了解有关先决条件和环境依赖项以在组织中部署团队
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39483e7b3c8e511f2081f907b187d97dbbaf526f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203336"
---
![升级旅程，重点强调的技术的准备阶段的阶段](media/upgrade-banner-tech-readiness.png "升级旅程，重点强调的技术的准备阶段的阶段")

本文是您升级旅程，与用户准备阶段并行完成的活动的技术的准备阶段的一部分。 在继续之前，确认您已完成从以前的阶段的这些活动：

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)
- [商业和团队理解共存和 Skype 的互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>先决条件和团队环境依赖项

团队结合使用多个 Office 365 服务，因此依赖的正确实现和操作这些服务。 这些服务包括 — 但不限于 — SharePoint Online 和 Exchange Online 的 OneDrive for Business。

尽管并非所有服务都都需要，但强烈建议您实现所有这些。 如果您选择不实现某些服务，它会影响团队可以提供您的组织的功能。 例如，您无需实现 SharePoint Online，但团队依赖 SharePoint Online 的某些功能如文件共享中组对话，因此不实现此服务将降低通过提供的功能客户端。

请参阅以下文章以了解有关先决条件和团队与其他技术的交互方式：

- 如果您的组织未部署任何 Office 365 工作负载，请参阅[Getting Started with Office 365 的业务](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果贵组织尚未添加或 Office 365 配置已验证的域，请参阅[Verify Office 365 域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 如果贵组织尚未同步到 Azure Active Directory 标识，请参阅[标识模型和 Microsoft 团队中的身份验证](identify-models-authentication.md)。

- 如果您的组织 doesn¹t Exchange Online，请参阅[的了解 Exchange 和 Microsoft 团队的交互方式](Exchange-Teams-interact.md)。

- 如果您的组织没有 SharePoint Online，请参阅[的了解 SharePoint Online 和 OneDrive for Business 如何与 Microsoft 团队交互](SharePoint-OneDrive-interact.md)。

- 了解如何[Office 365 组和 Microsoft 团队进行交互](Office-365-groups.md)。

- 如果您的组织是教育机构并使用学生信息系统，然后再部署 Microsoft 团队[部署学校数据同步](https://docs.microsoft.com/schooldatasync)。

后验证了您的环境符合[评估当前环境团队](upgrade-plan-journey-evaluate-environment.md)的所有适用的先决条件。