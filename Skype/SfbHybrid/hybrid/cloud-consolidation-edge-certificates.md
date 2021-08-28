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
ms.localizationpriority: medium
description: 此附录包括更新边缘证书的详细步骤，作为云解决方案和 Teams Skype for Business。
ms.openlocfilehash: 1c4708f593b1a9bd8fbc2a427e2f0c5df9feab5c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610199"
---
# <a name="update-the-edge-certificate"></a>更新 Microsoft Edge 证书

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


更新边缘证书是确保具有 SipDomain1 的一个内部部署环境可以使用 SipDomain2 加入云环境并确保在跨两个 SIP 域的共享地址空间环境中正确路由的关键步骤。 请参阅云合并中的步骤[14，了解Teams Skype for Business](cloud-consolidation.md)执行此步骤的上下文。 在我们的示例中，SipDomain1 是 AcquiredCompany。 <span>com 和 SipDomain2 为 OriginalCompany。 <span>com.

必须更新内部部署环境中 (边缘服务器上证书的 SAN) 主题备用名称，以包括纯联机租户环境中存在的所有 SIP 域 (不包括任何 onmicrosoft。 <span>com domains) ，格式为"sip. \<domain> "。  在我们的示例中，这是 sip。OriginalCompany。 <span>com. 在将任何用户迁移到云之前，此步骤至关重要。

**步骤：**

1.  获取边缘的新外部边缘证书，该边缘具有云环境中所有 SIP 域的所有现有条目以及 SAN 中的其他条目 (但 *.onmicrosoft.com 域) 格式为 <DomainName> "sip."。
2.  在每台边缘服务器上本地安装证书，并将其分配给Skype服务上的边缘服务。  有关详细步骤，请参阅 Deploy Edge Service in [Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)中的"外部边缘接口证书"一节。
3.  在每个边缘服务器上重新启动边缘服务。 可以使用以下 PowerShell 命令为单个框进行此操作：

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>另请参阅

[云解决方案Teams Skype for Business](cloud-consolidation.md)