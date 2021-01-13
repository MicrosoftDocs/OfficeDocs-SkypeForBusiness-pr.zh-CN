---
title: 在 Skype for Business Server 中测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要：了解如何使用 Skype for Business Server 命令行管理程序测试 SIP 中继配置设置。
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830632"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中测试 SIP 中继配置设置
 
**摘要：** 了解如何使用 Skype for Business Server 命令行管理程序测试 SIP 中继配置设置。
  
SIP 中继配置设置定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP-Public Branch eXchange (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 这些设置按下面的指示执行此类操作：
  
- 是否应对中继启用媒体旁路。
    
- 发送实时传输控制协议 (RTCP) 的条件。
    
- 每个中继上是否需要安全实时传输 (SRTP) 加密。
    
安装 Skype for Business Server 时，将创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。 管理员还可以使用 Test-CsTrunkConfiguration cmdlet 验证中继是否可以将用户拨打的号码转换为网关可处理的号码。
  
只能使用 Windows PowerShell 和 [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet 测试中继配置设置。 此 cmdlet 可以从 Skype for Business Server 命令行管理程序 运行，也可以从 Skype for Business Server 命令行管理程序 的远程会话运行。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>测试 SIP 中继配置设置

- 以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


