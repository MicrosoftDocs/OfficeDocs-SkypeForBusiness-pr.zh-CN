---
title: 查看 Business server Skype 中的单个 SIP 中继的信息
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在业务服务器 Skype，多个中继可以分配给单个 PSTN 网关;这意味着，网关和中继不是同一个，并且管理员必须使用 Get-cstrunk cmdlet 可以查看有关各个 SIP 中继的信息。
ms.openlocfilehash: 4c57bdfb8671c8aee3f0bb3dbc48fdc5cb920b07
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885175"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>查看 Business server Skype 中的单个 SIP 中继的信息

在业务服务器 Skype，多个中继可以分配给单个 PSTN 网关;这意味着网关和中继不是同一个，管理员必须使用[Get-cstrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet 可以查看有关各个 SIP 中继的信息。

从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行 Get-cstrunk cmdlet。

**查看所有 SIP 中继的信息**

以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配给池的所有 SIP 中继的信息**

在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
