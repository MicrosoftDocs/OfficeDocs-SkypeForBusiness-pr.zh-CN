---
title: 查看 Skype for Business 服务器中单个 SIP 中继的相关信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '摘要: 了解如何在 Skype for Business 服务器中查看有关 SIP 中继的信息。'
ms.openlocfilehash: a8cb5559b1431987adeef7c50b7810b7e9b4adc7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300914"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>查看 Skype for Business 服务器中单个 SIP 中继的相关信息
 
**摘要:** 了解如何在 Skype for Business 服务器中查看有关 SIP 中继的信息。
  
SIP 中继用于连接 Skype for Business 服务器使用公共交换电话网络 (PSTN) 的 IP 电话网络语音。 在本产品的以前版本中，中继用来将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关仅限于一个中继。 因此，PSTN 网关和 SIP 中继基本上完全相同。 对于管理员而言，这意味着他们只需通过查看有关相关联的 PSTN 网关的信息，即可查看有关个别 SIP 中继的信息。
  
但是, 在 Skype for Business 服务器中, 可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。 而这意味着管理员必须使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet，才能查看有关个别 SIP 中继的信息。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>查看所有 SIP 中继的信息

- 以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>查看特定 SIP 中继的信息

- 此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看分配给池的所有 SIP 中继的信息

- 在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
