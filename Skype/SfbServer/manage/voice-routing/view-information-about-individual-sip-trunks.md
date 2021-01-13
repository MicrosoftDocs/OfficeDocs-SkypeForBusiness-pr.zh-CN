---
title: 查看有关 Skype for Business Server 中单个 SIP 中继的信息
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
description: 在 Skype for Business Server 中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不是一个相同的，管理员必须使用 Get-CsTrunk cmdlet 查看有关单个 SIP 中继的信息。
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826172"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>查看有关 Skype for Business Server 中单个 SIP 中继的信息

在 Skype for Business Server 中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不是一个相同的，并且管理员必须使用 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 中继的信息。

可以从 skype for Business Server 命令行管理程序或远程会话运行 Get-CsTrunk cmdlet Windows PowerShell。

**查看所有 SIP 中继的信息**

以下命令返回有关组织使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配给池的所有 SIP 中继的信息**

此示例返回分配给池池的所有 SIP 中继atl-cs-001.litwareinc.com：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
