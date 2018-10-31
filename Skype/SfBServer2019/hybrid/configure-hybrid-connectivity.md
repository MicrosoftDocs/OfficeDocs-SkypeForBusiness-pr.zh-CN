---
title: 配置混合连接性
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 用于实现业务服务器 Skype 和 Skype 业务 online 之间的混合连接的说明。
ms.openlocfilehash: 2f14859e600a06a57b67a14249e954f3e4e6d4a2
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849353"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>配置混合 Skype 业务 server 和 Office 365 之间的连接
 
**摘要：** 阅读本主题可了解如何配置混合 Skype Business Server 和团队或 Skype 业务 online 之间的连接。  混合连接使您能够为业务 Online，将您的内部部署用户移动到团队或 Skype 和，用户可以充分利用云服务。
  
之前执行本主题中的步骤，您应该已经阅读[规划之间 Skype Business Server 和 Office 365 的混合连接性](plan-hybrid-connectivity.md)。
  
下表列出了需要为业务混合连接配置 Skype 的任务，并提供指向相关文章的详细信息。
  
|**步骤**|**说明**|
|:-----|:-----|
|创建 Office 365 租户帐户   <br/> |了解[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)上的 Office 365。  <br/> 若要确保你的环境满足 Office 365 要求，请参阅[系统要求](https://products.office.com/en-US/office-system-requirements)。  <br/> 有关设置 Office 365 的详细信息，请参阅 [Office 365 入门](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|将您的域添加到 Office 365 租户，并验证所有权  <br/> | 您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。 这是为了确认您是域的所有者。 <br/> 若要将您的域添加到 Office 365 租户，请按照[将域添加到 Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步骤。  <br/> |
|设置 Active Directory 同步  <br/> |Active Directory 同步保持内部部署 Active Directory 与 Office 365 持续同步。 这样可以创建的每个用户帐户和组的同步的版本。  <br/> <br> **重要：** 您需要在本地和联机部署之间您组织中的业务用户的所有 Skype 的同步的 AD 帐户即使用户不移到团队或 Skype 业务 online。 如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。 有关详细信息，请参阅[的混合环境配置 Azure AD 连接](configure-azure-ad-connect.md)。         |
| Skype 混合配置的业务 | 有三个基本步骤： <br><br> 1.配置内部部署环境与 Office 365 联盟。 <br> 2.配置为信任 Office 365 的本地环境并启用共享的 SIP 地址空间，与 Office 365。<br> 3.启用 Office 365 租户中的共享的 SIP 地址空间。 <br><br> 此外，如果您有 Exchange 内部部署，您可能希望为业务 Online 环境 Exchange 内部部署和 Skype 之间配置 OAuth。 <br> <br>有关详细信息，请参阅[业务混合配置 Skype](configure-federation-with-skype-for-business-online.md)。
|移动试用用户  <br/> |您已完成的步骤准备和配置您的环境的团队或 Skype 业务 online 后，您可以开始将试点用户移到 online Office 365 租户。 有关详细信息，请参阅[移动到业务 online Skype 本地用户](move-users-from-on-premises-to-skype-for-business-online.md)和[移动用户从本地向工作组](move-users-from-on-premises-to-Teams.md)。  <br/> | 

  