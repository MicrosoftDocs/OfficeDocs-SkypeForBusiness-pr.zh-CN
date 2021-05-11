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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关在客户端和服务器之间实现Skype for Business Server连接Teams。
ms.openlocfilehash: 1b1fee4fe513778433bff077ce23973e4bfc0d8a
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305936"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>配置 Skype for Business Server 和 Teams

**摘要：** 阅读本主题，了解如何配置 Skype for Business Server Teams (或 Skype for Business Online 之间的混合连接，直到其停用) 。  混合连接使你能够将本地用户移动到 Teams (或 Skype for Business Online) ，并允许用户充分利用云服务。
  
在执行本主题中的步骤之前，应先阅读规划 Skype for Business Server[和 Teams 之间的混合连接](plan-hybrid-connectivity.md)。
  
下表列出了配置混合连接Skype for Business所需的任务，并提供指向相关文章的链接，了解详细信息。
  
|步骤|说明|
|:-----|:-----|
|为租户创建租户Microsoft 365   <br/> |若要了解[Microsoft 365，Microsoft 365。](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> 若要确保您的环境已准备好进行Microsoft 365，请参阅系统[要求](https://products.office.com/office-system-requirements)。  <br/> 有关设置 Microsoft 365 的详细信息，请参阅 Microsoft 365[入门](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|将域添加到你的Microsoft 365并验证所有权  <br/> | 您必须将域添加到 Microsoft 365 组织，然后按照步骤使用 Microsoft 365。 这是为了确认您是域的所有者。 <br/> 若要将域添加到组织Microsoft 365，请按照向组织添加域中所述[Microsoft 365。](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|设置 Active Directory 同步  <br/> |Active Directory 同步可保持本地 Active Directory 与 Microsoft 365。 这允许你创建每个用户帐户和组的同步版本。  <br/> <br> **重要提示：** 你需要在本地和联机部署之间同步组织中所有 Skype for Business 用户的 AD 帐户，即使用户未移至 Teams (或 Skype for Business Online) 。 如果不同步所有用户，则组织中本地用户和联机用户之间的通信可能无法按照预期方式工作。 有关详细信息，请参阅为混合环境[连接 Azure AD 策略](configure-azure-ad-connect.md)。         |
| 配置 Skype for Business 混合环境 | 有以下三个基本步骤： <br><br> 1. 将本地环境配置为与 Microsoft 365。 <br> 2. 将本地环境配置为信任 Microsoft 365，并启用与 Microsoft 365 的共享 SIP 地址Microsoft 365。<br> 3. 在您的组织中启用共享 SIP Microsoft 365空间。 <br><br> 另外，如果你有本地 Exchange，则可能需要在本地 Exchange 和 Skype for business Online 环境之间配置 OAuth。 <br> <br>有关详细信息，请参阅配置混合[Skype for Business配置](configure-federation-with-skype-for-business-online.md)。
|移动试点用户  <br/> |完成为 Teams (或 Skype for Business Online) 准备和配置环境的步骤后，你可以开始将试点用户移动到联机 Microsoft 365 组织。 有关详细信息，请参阅将用户[从](move-users-from-on-premises-to-Teams.md)本地移动到 Teams 和 将用户从本地移动到[Skype for Business Online。](move-users-from-on-premises-to-skype-for-business-online.md)  <br/> |
