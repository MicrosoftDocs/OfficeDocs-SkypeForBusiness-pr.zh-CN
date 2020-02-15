---
title: 查看有关 Skype for Business Server 中各个 SIP 中继的信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在 Skype for Business Server 中，可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不是相同的，并且管理员必须使用 CsTrunk cmdlet 来查看有关单个 SIP 中继的信息。
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048175"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>查看有关 Skype for Business Server 中各个 SIP 中继的信息

在 Skype for Business Server 中，可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不是一个，也不相同，并且管理员必须使用[CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 来查看有关单个 SIP 中继的信息。

CsTrunk cmdlet 可以从 Skype for Business Server 命令行管理程序或 Windows PowerShell 的远程会话中运行。

**查看所有 SIP 中继的信息**

以下命令将返回有关您组织中使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅返回标识为 pstngateway：192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配到池的所有 SIP 中继的信息**

在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
