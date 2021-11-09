---
title: 在服务中查看 SIP 中继Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 摘要：了解如何查看有关 Skype for Business Server 中的 SIP 中继的信息。
ms.openlocfilehash: cf2bf0f6cf586e80fa6b3f2ba1308ee6254ea7e9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835850"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype for Business Server：查看有关单个 SIP 中继的信息 
 
**摘要：** 了解如何查看有关 Skype for Business Server 中的 SIP 中继的信息。
  
SIP 中继用于将Skype for Business Server IP 语音电话网络与公用电话交换网 (PSTN) 。 在该产品的以前版本中，中继用于将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关限制为一个中继。 因此，PSTN 网关和 SIP 中继基本相同。 对于管理员，这意味着他们只需查看有关关联的 PSTN 网关的信息，就可以查看有关单个 SIP 中继的信息。
  
但是Skype for Business Server，现在可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不再相同。 反过来，这意味着管理员必须使用新的 [Get-CsTrunk](/powershell/module/skype/get-cstrunk) cmdlet 才能查看有关单个 SIP 中继的信息。
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>查看所有 SIP 中继的信息

- 以下命令返回有关组织使用的所有 SIP 中继的信息：
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>查看特定 SIP 中继的信息

- 此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看分配给池的所有 SIP 中继的信息

- 此示例返回分配给池池的所有 SIP 中继 atl-cs-001.litwareinc.com：
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
