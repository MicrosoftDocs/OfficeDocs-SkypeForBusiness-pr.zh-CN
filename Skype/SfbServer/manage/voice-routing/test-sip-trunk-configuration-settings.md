---
title: 在 Skype for Business Server 中测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 '
ms.openlocfilehash: 1489fe1e45223bac6b62ed23a09212a569ea7838
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826182"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中测试 SIP 中继配置设置

SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：

- 是否应对中继启用媒体旁路。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个中继上是否需要安全实时协议 (SRTP) 加密。

安装 Skype for Business Server 时，将创建 SIP 中继配置设置的全局集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。 管理员还可使用 [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 验证中继能否将用户拨打的号码转换为网关可以处理的号码。

只能使用 Windows PowerShell 和 Test-CsTrunkConfiguration cmdlet 测试中继配置设置。 此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。 

**测试 SIP 中继配置设置**

以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
