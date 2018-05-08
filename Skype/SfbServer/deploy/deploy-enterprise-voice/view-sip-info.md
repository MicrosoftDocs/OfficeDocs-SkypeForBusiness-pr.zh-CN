---
title: 在 Skype for Business Server 2015 中查看有关各个 SIP 中继的信息
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 摘要： 了解如何为业务服务器 2015 Skype 中查看有关 SIP 中继的信息。
ms.openlocfilehash: 9a27c5c78f15fbdc64aa52cf842697ab0b002252
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中查看有关各个 SIP 中继的信息
 
**摘要：**了解如何为业务服务器 2015 Skype 中查看有关 SIP 中继的信息。
  
SIP 中继用于通过 IP 电话网络与公共公用电话交换网 (PSTN) 的业务 Server 语音连接 Skype。 在本产品的以前版本中，中继用来将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关仅限于一个中继。 因此，PSTN 网关和 SIP 中继基本上完全相同。 对于管理员而言，这意味着他们只需通过查看有关相关联的 PSTN 网关的信息，即可查看有关个别 SIP 中继的信息。
  
在业务服务器 Skype，但是，多个中继可以现在将分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。 反过来，这意味着，管理员必须使用新[Get-cstrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet，以查看有关各个 SIP 中继的信息。
  
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


