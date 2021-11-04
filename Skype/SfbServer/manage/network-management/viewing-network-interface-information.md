---
title: 查看网络接口信息
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 可以使用 cmdlet 和 Windows PowerShell cmdlet 查看Get-CsNetworkInterface信息。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。
ms.openlocfilehash: 6414dc6e032ccd01d66af666d2c3edc2d1e021c7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742098"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>在网络中查看网络接口Skype for Business Server

可以使用 **Get-CsNetworkInterface** cmdlet 和 Windows PowerShell查看网络接口信息。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。

## <a name="to-view-network-interface-information"></a>查看网络接口信息

若要查看网络接口信息，请在命令行管理程序中Skype for Business Server命令，然后按 Enter：
    
`Get-CsNetworkInterface`

对于每个网络接口，此命令返回的信息类似于以下内容：

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

有关详细信息，请参阅 [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface)。
