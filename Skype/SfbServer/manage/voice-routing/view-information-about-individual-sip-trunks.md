---
title: 查看有关服务中单个 SIP 中继Skype for Business Server
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
description: 在Skype for Business Server中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不同，管理员必须使用 Get-CsTrunk cmdlet 查看有关单个 SIP 中继的信息。
ms.openlocfilehash: 1fd465bcbf547471f9ca5ead562d8b77976be79621bd4246be85341126577936
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351452"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>查看有关服务中单个 SIP 中继Skype for Business Server

在Skype for Business Server中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不是一个相同的，并且管理员必须使用[Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 中继的信息。

该Get-CsTrunk cmdlet 可以从命令行管理程序Skype for Business Server远程会话运行Windows PowerShell。

**查看所有 SIP 中继的信息**

以下命令返回有关组织使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配给池的所有 SIP 中继的信息**

此示例返回分配给池池的所有 SIP 中继 atl-cs-001.litwareinc.com：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`