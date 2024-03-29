---
title: 升级到新环境的先决条件和环境Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指南了解在组织中部署Teams先决条件和环境依赖项
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f10df8849e6efe4e6ceac38cb46d118dff5a8ff8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725451"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>安全环境的先决条件和环境Teams

![升级过程图，强调技术准备阶段。](media/upgrade-banner-tech-readiness.png "升级过程阶段，着重强调技术准备阶段")

本文是升级过程的技术准备阶段（与用户准备阶段并行完成的活动）的一部分。 在继续之前，请确认已完成之前阶段中的这些活动：

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解两者共存Skype for Business互操作性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams服务Microsoft 365 Office 365服务，因此依赖于这些服务的正确实现和操作。 这些服务包括但不限于联机、SharePoint和Exchange Online OneDrive for Business。

尽管并非所有服务都是必需的，但我们强烈建议实现所有这些服务。 如果选择不实施某些服务，则会影响组织Teams的功能。 例如，虽然无需实现 SharePoint Online，但 Teams 确实依赖于 SharePoint Online 实现某些功能，例如组对话中的文件共享，因此不实现此服务会减少通过客户端提供的功能。

请参阅以下文章，了解先决条件以及如何Teams技术交互：

- 如果组织尚未在工作负荷中部署Microsoft 365 Office 365，请参阅[入门](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果你的组织尚未为域或域添加或配置Microsoft 365 Office 365，请参阅[域常见问题](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)解答。

- 如果组织尚未将标识同步到Azure Active Directory，请参阅中的标识模型和[Microsoft Teams。](identify-models-authentication.md)

- 如果您的组织没有 Exchange Online，请参阅[了解 Exchange 与 Microsoft Teams 如何交互](Exchange-Teams-interact.md)。

- 如果您的组织没有 SharePoint Online，请参阅[了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](SharePoint-OneDrive-interact.md)。

- 若要了解如何[Microsoft 365组Microsoft Teams交互](Office-365-groups.md)。

- 如果你的组织是教育机构，并且你使用学生信息系统，请参阅在部署学校数据同步[Microsoft](/schooldatasync) Microsoft Teams。

- 如果你的组织正在考虑公用电话交换网 (PSTN) 呼叫选项，请参阅语音 - 电话系统 和[PSTN](cloud-voice-landing-page.md)连接、哪个呼叫计划适合[](calling-plan-landing-page.md)你和 电话系统[直接路由](direct-routing-landing-page.md)。

- 若要确保在推出前满足所有网络要求Teams，请参阅准备组织的网络以[Microsoft Teams。](prepare-network.md)

- 如果当前正在使用 Skype for Business Online 连接器来管理服务，则需要移动到 powerShell Teams并更新现有的 PowerShell 脚本。 有关详细信息[，请参阅](teams-powershell-move-from-sfbo.md)从 Skype for Business Online 连接器Teams PowerShell 模块。

验证环境是否满足所有适用的先决条件后，请评估当前[环境](upgrade-plan-journey-evaluate-environment.md)Teams。