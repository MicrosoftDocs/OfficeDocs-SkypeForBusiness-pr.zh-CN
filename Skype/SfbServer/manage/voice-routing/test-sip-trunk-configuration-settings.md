---
title: 在 Skype for Business 服务器中测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 '
ms.openlocfilehash: 9f254d833f5d679343a39062bc2ed68c9122af56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274917"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business 服务器中测试 SIP 中继配置设置

SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 这些设置可执行如下所指定内容的操作：

- 是否在中继上启用媒体旁路功能。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个主干上是否需要安全的实时协议 (SRTP) 加密。

安装 Skype for Business 服务器时, 将为你创建一个全局 SIP 中继配置设置集合。 此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。 管理员还可以使用[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 验证主干能否将用户所拨的号码转换为可由网关处理的号码。

只能使用 Windows PowerShell 和 Test-CsTrunkConfiguration cmdlet 测试中继配置设置。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 

**测试 SIP 中继配置设置**

以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
