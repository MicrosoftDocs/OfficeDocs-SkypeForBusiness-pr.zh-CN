---
title: Skype for Business Server：测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要：了解如何使用命令行管理程序测试 SIP 中继Skype for Business Server设置。
ms.openlocfilehash: 08bcbc0548af42b7242047ce9c848f00f1af7096
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616998"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype for Business Server：测试 SIP 中继配置设置
 
**摘要：** 了解如何使用命令行管理程序测试 SIP Skype for Business Server设置。
  
SIP 中继配置设置定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP-Public Branch eXchange (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 这些设置按下面的指示执行此类操作：
  
- 是否应该在中继上启用媒体旁路
    
- 发送实时传输控制协议 (RTCP) 的条件
    
- 每个中继上是否需要安全实时传输 (SRTP) SRTP 加密
    
在安装Skype for Business Server时，将创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点范围或服务范围为 PSTN 网关服务创建自定义设置集合 (，但只能) 。 管理员还可使用 Test-CsTrunkConfiguration cmdlet 验证中继能否将用户拨打的号码转换为网关可以处理的号码。
  
只能使用 Windows PowerShell 和 [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration) cmdlet 测试中继配置设置。 可以从命令行管理程序或命令行管理Skype for Business Server远程会话中运行此 cmdlet Skype for Business Server运行。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>测试 SIP 中继配置设置

- 以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
