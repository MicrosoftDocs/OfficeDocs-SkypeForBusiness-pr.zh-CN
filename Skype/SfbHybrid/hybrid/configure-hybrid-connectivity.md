---
title: 配置混合连接|部署 Skype for Business Server 2019 连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关实现 Skype for Business Server 和 Teams 之间的混合连接的说明。
ms.openlocfilehash: fee7587c641f2fd55cd8b4ac4da72b3944b819a1
ms.sourcegitcommit: 64b9f7297d33a883506893fb68d1ad5202b4df1a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2021
ms.locfileid: "59682807"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>配置 Skype for Business Server 和 Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**摘要：** 阅读本主题，了解如何配置 Skype for Business Server 和 Teams。  混合连接使你能够将本地用户移动到 Teams，并允许用户利用云服务。
  
在执行本主题中的步骤之前，您应已阅读 Plan [hybrid connectivity between Skype for Business Server and Teams](plan-hybrid-connectivity.md)。
  
下表列出了配置混合连接Skype for Business所需的任务，并提供指向相关文章的链接，了解详细信息。
  
|步骤|说明|
|:-----|:-----|
|创建适用于 Microsoft 365 的租户帐户。   <br/> |若要了解[Microsoft 365，Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 若要确保您的环境已准备好进行Microsoft 365，请参阅系统[要求](https://products.office.com/office-system-requirements)。  <br/> 有关设置Microsoft 365的详细信息，请参阅入门[Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254982)  <br/> |
|将域添加到你的Microsoft 365并验证所有权。  <br/> | 您必须将域添加到您的 Microsoft 365 组织，然后按照步骤使用 Microsoft 365。 此验证是确认你是域的所有者。 <br/> 若要将域添加到组织Microsoft 365，请按照将域添加到组织中所述[Microsoft 365。](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US) 请务必查看以下有关成为混合的组织 [DNS 含义的指南](#dns-implications-for-on-premises-organizations-that-become-hybrid)。 <br/> |
|设置 Active Directory 同步。  <br/> |Active Directory 同步可确保本地 Active Directory 与 Microsoft 365，以便创建每个用户帐户和组的同步版本。  <br/> <br> **重要提示：** 您需要在本地部署和联机部署之间同步组织中所有 Skype for Business 用户的 Active Directory 帐户，即使用户未移动到 Teams。 如果未同步所有用户，则组织中本地用户和联机用户之间的通信可能无法按照预期方式工作。 有关详细信息，请参阅为混合环境[连接 Azure AD 策略](configure-azure-ad-connect.md)。         |
| 配置 Skype for Business 混合环境。 | 有以下三个基本步骤： <br><br> 1. 将本地环境配置为与 Microsoft 365。 <br> 2. 将本地环境配置为信任Microsoft 365并启用与 Microsoft 365 的共享 SIP 地址Microsoft 365。<br> 3. 在组织中启用共享 SIP 地址Microsoft 365空间。 <br><br> 此外，如果你有本地Exchange，则你可能希望在本地和联机环境Exchange OAuth。 <br> <br>有关详细信息，请参阅配置混合[Skype for Business配置](configure-federation-with-skype-for-business-online.md)。
|移动试点用户。  <br/> |完成准备和配置环境环境的步骤后Teams，你可以开始将试点用户移动到联机Microsoft 365组织。 有关详细信息，请参阅将用户[从本地移动到Teams。](move-users-from-on-premises-to-Teams.md)  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>成为混合部署组织对 DNS 的影响

默认情况下，租户创建为 TeamsOnly 模式。 管理员无法更改此配置。 但是，混合组织不得为 TeamsOnly 模式，因为这会中断其本地用户的联盟。 Teams内置机制，以确保租户范围的 TeamsOnly 配置不应用于新的混合租户，并且从成为混合的现有租户中删除租户范围的 TeamsOnly *配置*。 此机制基于任何已验证的 Microsoft 365 域 (的 LyncDiscover DNS 记录的值，因为 Skype for Business Server 本地部署在大多数情况下都将具有该记录) ，如下所述。

首次处理Microsoft 365订阅时，将发生以下情况：
- 如果尚未验证域Microsoft 365，租户将创建为 TeamsOnly 模式。 该值通过 TeamsUpgradeOverridePolicy 进行设置，它仅能由 Microsoft 设置。 如果策略值为 UpgradeToTeams，则它优先于 TeamsUpgradePolicy 的任何值。
- 如果已验证 Microsoft 365 域，但没有检测到公共 DNS LyncDiscover 记录，或者检测到的所有 LyncDiscover 记录均指向 Microsoft 365 (sipfed.online.lync.com、sipfed.online.gov.skypeforbusiness.us 等) ，则租户通过 TeamsUpgradeOverridePolicy) 创建为 TeamsOnly 模式 (。
- 如果至少有一个已验证Microsoft 365 LyncDiscover 记录的域，并且该记录指向除 Microsoft 365 外的其他位置，则租户将创建为"群岛"模式。

当现有Microsoft 365租户重新预配 (通常是由于已验证域或订阅详细信息) 更改，将发生以下情况：
- 如果为一个或多个 Microsoft 365 验证域找到 LyncDiscover 记录，并且该记录未指向 Microsoft 365，则删除通过 TeamsUpgradeOverridePolicy (的租户范围的 TeamsOnly 模式) 。 租户模式将恢复为 TeamsUpgradePolicy 的租户级别指定的任何内容，默认情况下，该模式为"群岛"模式。


此自动检测机制存在一些限制：
- 如果你的组织没有任何公共 DNS 记录，将不会删除 TeamsOnly 模式，Microsoft 365无法检测记录。 如果你的组织具有本地服务器Skype for Business Server没有公共 DNS 条目，你将需要联系 Microsoft 支持部门，以降级你的租户。
- 如果将公用 DNS 记录添加/更新到已验证Microsoft 365域，将不会检测到此 DNS 更改，并且不会删除 TeamsOnly 模式。 只有在重新预配租户时，TeamsOnly 模式才被删除，这通常发生在更改已验证Microsoft 365或订阅时。  
