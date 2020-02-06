---
title: 查看 Skype for Business 服务器中单个 SIP 中继的相关信息
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
description: 在 Skype for Business 服务器中，可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不是同一个，并且管理员必须使用 CsTrunk cmdlet 查看有关单个 SIP 主干的信息。
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816921"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>查看 Skype for Business 服务器中单个 SIP 中继的相关信息

在 Skype for Business 服务器中，可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不是同一个，并且管理员必须使用[CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 主干的信息。

CsTrunk cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。

**查看所有 SIP 中继的信息**

以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配到池的所有 SIP 中继的信息**

在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
