---
title: 更新 Microsoft Edge 证书
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附录包括更新边缘证书的详细步骤，作为 Teams 和 Skype for Business 云整合的一部分。
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120341"
---
# <a name="update-the-edge-certificate"></a>更新 Microsoft Edge 证书

更新边缘证书是确保具有 SipDomain1 的一个内部部署环境可以使用 SipDomain2 加入云环境并确保在跨两个 SIP 域的共享地址空间环境中正确路由的关键步骤。 有关可能执行此步骤的上下文，请参阅 Teams 和 [Skype for Business](cloud-consolidation.md) 云合并中的步骤 14。 在我们的示例中，SipDomain1 是 AcquiredCompany。 <span>com 和 SipDomain2 为 OriginalCompany。 <span>com.

必须更新 (环境中) 边缘服务器上证书的主题备用名称 SAN) ，以包括纯联机租户环境中存在的所有 SIP 域 (不包括任何 onmicrosoft。 <span>com domains) ，格式为"sip. \<domain> "。  在我们的示例中，这是 sip。OriginalCompany。 <span>com. 在将任何用户迁移到云之前，此步骤至关重要。

**步骤：**

1.  获取边缘的新外部边缘证书，该边缘具有云环境中所有 SIP 域的所有现有条目以及 SAN 中的其他条目 (但 *.onmicrosoft.com 域) 格式为 <DomainName> "sip."。
2.  在每个边缘服务器上本地安装证书，并将其分配给每个边缘服务上的 Skype 边缘服务。  有关详细步骤，请参阅 Deploy Edge Service in [Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)中的"外部边缘接口证书"部分。
3.  在每个边缘服务器上重新启动边缘服务。 可以使用以下 PowerShell 命令为单个框进行此操作：

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>另请参阅

[Teams 和 Skype for Business 云合并](cloud-consolidation.md)