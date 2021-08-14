---
title: 管理适用于美国政府的 Office 365 G1 免费试用版
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 对于美国政府，如果你没有 Microsoft Teams 且不急需该软件，可向为应对 COVID-19（冠状病毒）疫情爆发而需要远程工作或在家办公的用户推广 Office 365 G1 试用版。
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad58e4388c6a20dc64f67dff5097158ac5c26bbf
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234517"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>管理适用于美国政府的 Office 365 G1 试用版 

自 2020 年 7 月 1 日起，Office 365 E1 试用版许可证不再可用。 如果需要向用户授予 Microsoft Teams 许可，请阅读 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)，了解包含 Teams 的付费订阅列表。 

使用本文中的指南管理现有 Office 365 G1 试用版许可证，包括[升级到付费订阅](#upgrade-users-from-the-office-365-g1-trial-license)。 若要了解详细信息，请参阅 [Microsoft 365 政府版计划](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans)以及 [GCC 云提供的 Microsoft Teams 功能](plan-for-government-gcc.md)。

不要错过我们[通过 Teams 支持远程工作人员](support-remote-work-with-teams.md)的所有指南。

## <a name="manage-the-g1-trial"></a>管理 G1 试用版

激活 Office 365 G1 试用版后，请打开许可证供需要它的任何用户使用。 要了解操作方式，请参阅[管理用户对 Teams 的访问](user-access.md)。

为需要 G1 试用版的用户启用该版本后，你可像管理拥有付费许可证的用户一样管理这些用户。有关详细信息，请参阅[为你的组织管理 Teams 设置](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>从 Office 365 G1 试用版许可证升级用户

将 G1 试用版用户升级到付费订阅：

1.  购买包含 Teams 的订阅。

2.  删除用户的 Office 365 G1 试用版订阅。

3.  分配新购买的许可证。

有关详细信息，请参阅 [Teams 政府版](expand-teams-across-your-org/teams-for-government-landing-page.md)。

> [!NOTE]
> 如果 G1 试用版许可证已终止，而用户没有立即升级到包含 Teams 的订阅，则会删除用户的数据。用户仍然存在于 Azure Active Directory 中，Teams 中的所有数据仍保留。如果向用户分配新的许可证以再次启用 Teams 功能，则所有内容将仍然存在。
> 
### <a name="remove-an-office-365-g1-trial-license"></a>删除 Office 365 G1 试用版许可证

  - 如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

  - 如果要通过管理门户删除此许可证，请参阅[从组织删除用户](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>相关主题

[管理用户对 Teams 的访问管理](user-access.md)

[为你的组织管理 Teams 设置](enable-features-office-365.md)
