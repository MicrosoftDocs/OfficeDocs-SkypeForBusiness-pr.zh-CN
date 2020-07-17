---
title: Microsoft 团队先决条件 |依赖关系采用升级
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指南了解在组织中部署团队的先决条件和环境相关性
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1199bacde9ed41152cde6054975963cfd5a19ae9
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158730"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>团队的先决条件和环境依赖关系

![升级旅行图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级旅程的阶段，重点介绍技术准备阶段")

本文是您的升级过程的技术准备阶段的一部分，与用户准备阶段并行完成的活动。 在继续之前，请确认您已完成以前阶段中的这些活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

团队将多个 Microsoft 365 和 Office 365 服务结合在一起，因此依赖于这些服务的正确实现和操作。 这些服务包括（但不限于） SharePoint Online、Exchange Online 和 OneDrive for business。

尽管并非所有服务都是必需的，但我们强烈建议你实现所有服务。 如果您选择不实施某些服务，它将影响团队可为您的组织提供的功能。 例如，虽然您不必实现 SharePoint Online，但团队确实依赖于 SharePoint Online 执行某些功能（如组对话中的文件共享），因此不实现此服务将减少通过客户端提供的功能。

请参阅以下文章，了解有关先决条件以及团队如何与其他技术交互的方法：

- 如果你的组织尚未部署任何 Microsoft 365 或 Office 365 工作负荷，请参阅[入门](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果你的组织尚未为 Microsoft 365 或 Office 365 添加或配置验证的域，请参阅[域常见问题解答](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 如果你的组织尚未将身份与 Azure Active Directory 同步，请参阅[Microsoft 团队中的身份模型和身份验证](identify-models-authentication.md)。

- 如果你的组织没有 Exchange Online，请参阅[了解 exchange 和 Microsoft 团队如何交互](Exchange-Teams-interact.md)。

- 如果你的组织没有 SharePoint Online，请参阅[了解 Sharepoint online 和 OneDrive For business 如何与 Microsoft 团队进行交互](SharePoint-OneDrive-interact.md)。

- 了解[microsoft 365 组和 Microsoft 团队如何交互](Office-365-groups.md)。

- 如果您的组织是教育机构，并且您使用的是学生信息系统，请参阅部署 Microsoft 团队之前的 "[欢迎使用 Microsoft School 数据同步](https://docs.microsoft.com/schooldatasync)"。

- 如果你的组织正在考虑公共交换电话网络（PSTN）呼叫选项，请参阅[语音电话系统和 PSTN 连接](cloud-voice-landing-page.md)（[通话计划适合你](calling-plan-landing-page.md)）和[手机系统直接路由](direct-routing-landing-page.md)。

- 为确保在推出团队之前满足所有网络要求，请参阅为[Microsoft 团队准备组织的网络](prepare-network.md)。

验证你的环境满足所有适用的先决条件后，请[评估团队的当前环境](upgrade-plan-journey-evaluate-environment.md)。
