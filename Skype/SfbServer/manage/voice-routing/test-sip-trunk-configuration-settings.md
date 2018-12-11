---
title: 测试 SIP 中继配置设置中 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。 '
ms.openlocfilehash: d49b76c10505a009e6eed64d60632b52b08f3866
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222700"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>测试 SIP 中继配置设置中 Skype 业务服务器

SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。 这些设置可执行如下所指定内容的操作：

- 是否在中继上启用媒体旁路功能。
- 在其下发送实时传输控制协议 (RTCP) 数据包的条件。
- 是否每个中继上是否需要安全实时协议 (SRTP) 加密。

在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。 管理员还可以使用[测试 CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 来验证中继，可以将用户可以处理由网关的号码拨打的号码的转换。

只能使用 Windows PowerShell 和 Test-CsTrunkConfiguration cmdlet 测试中继配置设置。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

**测试 SIP 中继配置设置**

以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```