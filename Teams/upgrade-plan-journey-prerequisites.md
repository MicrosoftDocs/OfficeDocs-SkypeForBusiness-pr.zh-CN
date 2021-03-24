---
title: 升级到 Teams 的先决条件和环境依赖项
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指南了解在组织中部署 Teams 的先决条件和环境依赖项
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
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092190"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teams 的先决条件和环境依赖项

![升级过程图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级过程阶段，着重强调技术准备阶段")

本文是升级过程的技术准备阶段（与用户准备阶段并行完成的活动）的一部分。 在继续之前，请确认已完成之前阶段中的这些活动：

- [登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [请确定项目范围](./upgrade-define-project-scope.md)
- [了解 Skype for Business 和 Teams 的共存和互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [选择了升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams 结合了多个 Microsoft 365 和 Office 365 服务，因此依赖于这些服务的正确实现和操作。 这些服务包括但不限于 SharePoint Online、Exchange Online 和 OneDrive for Business。

虽然并非所有服务都是必需的，但我们强烈建议实现所有这些服务。 如果选择不实施某些服务，则会影响 Teams 为组织提供的功能。 例如，虽然无需实现 SharePoint Online，但 Teams 确实依赖 SharePoint Online 实现某些功能，例如组对话中的文件共享，因此不实现此服务会减少通过客户端提供的功能。

请参阅以下文章，了解先决条件以及 Teams 如何与其他技术交互：

- 如果你的组织尚未部署任何 Microsoft 365 或 Office 365 工作负荷，请参阅 [入门](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 如果你的组织尚未添加或配置 Microsoft 365 或 Office 365 的已验证域，请参阅 [域常见问题](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)解答 。

- 如果组织尚未将标识同步到 Azure Active Directory，请参阅 Microsoft Teams 中的标识 [模型和身份验证](identify-models-authentication.md)。

- 如果你的组织没有 Exchange Online，请参阅了解 Exchange 和 [Microsoft Teams 如何交互](Exchange-Teams-interact.md)。

- 如果你的组织没有 SharePoint Online，请参阅了解 [SharePoint Online](SharePoint-OneDrive-interact.md)和 OneDrive for Business 如何与 Microsoft Teams 交互。

- 了解 [Microsoft 365 组和 Microsoft Teams 如何交互](Office-365-groups.md)。

- 如果你的组织是教育机构，并且你使用学生信息系统，请参阅在部署 Microsoft Teams 之前欢迎使用 [Microsoft 学校](/schooldatasync) 数据同步。

- 如果你的组织考虑使用公用电话交换网 (PSTN) 呼叫选项，请参阅语音 - 电话系统和 [PSTN](cloud-voice-landing-page.md)连接、哪个呼叫计划 [适合](calling-plan-landing-page.md)你和电话 [系统直接路由](direct-routing-landing-page.md)。

- 若要确保在推出 Teams 之前满足所有网络要求，请参阅 [为 Microsoft Teams](prepare-network.md)准备组织的网络。

- 如果你当前正在使用 Skype for Business Online 连接器管理服务，则需要移动到 Teams PowerShell 模块并更新现有的 PowerShell 脚本。 有关详细信息 [，请参阅从 Skype for Business Online 连接器移动到 Teams PowerShell](teams-powershell-move-from-sfbo.md) 模块。

验证环境满足所有适用的先决条件后，请评估 Teams [的当前环境](upgrade-plan-journey-evaluate-environment.md)。