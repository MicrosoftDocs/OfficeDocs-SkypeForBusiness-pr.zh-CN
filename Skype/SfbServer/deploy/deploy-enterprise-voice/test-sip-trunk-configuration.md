---
title: 测试 SIP 中继配置设置中 Skype 业务服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要： 了解如何使用 Skype 业务 Server 命令行管理程序测试 SIP 中继配置设置。
ms.openlocfilehash: ea0874eabacfb814c5cc668654c56c86c788beff
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984069"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>测试 SIP 中继配置设置中 Skype 业务服务器
 
**摘要：** 了解如何使用 Skype 业务 Server 命令行管理程序测试 SIP 中继配置设置。
  
SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置可执行如下所指定内容的操作：
  
- 是否在中继上启用媒体旁路功能。
    
- 发送实时传输控制协议 (RTCP) 数据包所依据的条件。
    
- 在每个中继上是否需要安全实时传输协议 (SRTP) 加密。
    
在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。 管理员还可以使用 Test-CsTrunkConfiguration cmdlet 验证中继是否可以将用户拨打的号码转换为网关可处理的号码。
  
仅可以使用 Windows PowerShell 和[测试 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet 测试中继配置设置。 从业务 Server 命令行管理程序 Skype 或业务 Server Management Shell 的 Skype 的远程会话，则可以运行此 cmdlet。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>测试 SIP 中继配置设置

- 以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


