---
title: 配置混合连接 |部署 Skype for Business Server 2019 连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在 Skype for business Server 与 Skype for business Online 之间实现混合连接的说明。
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376745"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>配置 Skype for Business Server 与 Office 365 之间的混合连接

**摘要：** 阅读本主题，了解如何配置 Skype for Business Server 和团队或 Skype for business Online 之间的混合连接。  通过混合连接，你可以将本地用户移动到团队或 Skype for business Online，并使你的用户能够利用云服务。
  
在执行本主题中的步骤之前，您应具有 [Skype For Business Server 和 Office 365 之间的阅读计划混合连接](plan-hybrid-connectivity.md)。
  
下表列出了配置 Skype for Business 混合连接所需的任务，并提供了有关详细信息的相关文章的链接。
  
|步骤|说明|
|:-----|:-----|
|为 Office 365 创建租户帐户   <br/> |了解 office [365](https://go.microsoft.com/fwlink/p/?LinkId=254980)中的 office 365。  <br/> 若要确保你的环境已准备好适用于 Office 365，请参阅 [系统要求](https://products.office.com/office-system-requirements)。  <br/> 有关设置 Office 365 的详细信息，请参阅 [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982)入门。  <br/> |
|将您的域添加到 Office 365 组织并验证所有权  <br/> | 您必须将您的域添加到 Office 365 组织中，然后按照这些步骤使用 Office 365 验证域。 这是为了确认您是域的所有者。 <br/> 若要将您的域添加到 Office 365 组织中，请按照 " [向 office 365 添加域](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)" 中所述的步骤操作。  <br/> |
|设置 Active Directory 同步  <br/> |Active Directory 同步可使您的本地 Active Directory 持续与 Office 365 保持同步。 这将允许您创建每个用户帐户和组的同步版本。  <br/> <br> **重要说明：** 您需要在内部部署和联机部署之间为组织中的所有 Skype for Business 用户同步 AD 帐户，即使用户未移动到团队或 Skype for Business Online 也是如此。 如果不同步所有用户，组织中的内部部署用户和联机用户之间的通信可能无法按预期工作。 有关详细信息，请参阅 [Configure AZURE AD Connect for 混合环境](configure-azure-ad-connect.md)。         |
| 配置 Skype for Business 混合 | 有以下三个基本步骤： <br><br> 1. 将本地环境配置为与 Office 365 联合。 <br> 2. 将本地环境配置为信任 Office 365 并启用与 Office 365 共享的 SIP 地址空间。<br> 3. 在 Office 365 组织中启用共享 SIP 地址空间。 <br><br> 另外，如果你有本地 Exchange，则可能需要在本地 Exchange 和 Skype for business Online 环境之间配置 OAuth。 <br> <br>有关详细信息，请参阅 [配置 Skype For business 混合](configure-federation-with-skype-for-business-online.md)。
|移动试点用户  <br/> |完成准备和配置团队或 Skype for business Online 环境的步骤之后，可以开始将试点用户移动到您的在线 Office 365 组织。 有关详细信息，请参阅 [将用户从本地移动到 Skype For Business Online](move-users-from-on-premises-to-skype-for-business-online.md) 和 [将用户从本地移动到团队](move-users-from-on-premises-to-Teams.md)。  <br/> |
