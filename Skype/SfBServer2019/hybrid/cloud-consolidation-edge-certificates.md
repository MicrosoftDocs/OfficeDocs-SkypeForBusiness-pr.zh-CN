---
title: 更新边缘证书
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附录中包括有关云整合个团队和 Skype for Business 的一部分更新边缘证书的详细的步骤。
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247616"
---
# <a name="update-the-edge-certificate"></a>更新边缘证书

更新边缘证书是确保具有 SipDomain1 上 prem 环境可以加入与 SipDomain2 云环境和确保正确路由共享的地址空间环境中的两个 SIP 域之间的主要步。 请参阅步骤 14 中[个团队和 Skype for Business 的云整合](cloud-consolidation.md)上下文可能在其中执行此步骤。 在我们的示例中，SipDomain1 是 AcquiredCompany。<span>com 和 SipDomain2 是 OriginalCompany。<span>com。

在内部部署环境中的所有边缘服务器上的证书的使用者备用名称 (SAN) 必须更新以包括纯 online 租户中存在的所有 SIP 域 (不包括任何 onmicrosoft。<span>com 域），在窗体"sip。\<域 >"。  在本例中，这是 sip。OriginalCompany。<span>com。 关键迁移到云中的任何用户之前执行此步骤。

**步骤：**

1.  获取新的外部边缘证书具有云环境中的所有 SIP 域 SAN 中的所有现有项以及其他项的边缘 (不包括 *。 onmicrosoft.com 域) 中的窗体"sip。<DomainName>"。
2.  在每台边缘服务器上本地安装证书，并将其分配给每个边缘服务上的 Skype 边缘服务。  有关详细步骤，请参阅[部署中的业务服务器 2015 Skype 的边缘服务](https://technet.microsoft.com/en-us/library/dn951368.aspx)中的"外部边缘接口证书"一节。
3.  重新启动每台边缘服务器上的边缘服务。 可以使用以下 PowerShell 命令单个框来执行此操作：

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>另请参阅

[云整合个团队和 Skype for Business](cloud-consolidation.md)