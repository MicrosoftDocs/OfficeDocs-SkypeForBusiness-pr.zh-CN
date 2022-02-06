---
title: Skype for Business Server - 查看有关单个 SIP 中继的信息
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 在Skype for Business Server中，可以将多个中继分配给一个 PSTN 网关。 网关和中继不是同一个，管理员必须使用 Get-CsTrunk cmdlet 查看有关单个 SIP 中继的信息。
---

# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype for Business Server - 查看有关单个 SIP 中继的信息

在 Skype for Business Server 中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不是一个且相同的，并且管理员必须使用 [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 中继的信息。

可以从 Get-CsTrunk 命令行管理程序或 Windows PowerShell 的远程会话中运行 Skype for Business Server cmdlet。

**查看所有 SIP 中继的信息**

以下命令返回有关组织使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配给池的所有 SIP 中继的信息**

此示例返回分配给池池的所有 SIP 中继 atl-cs-001.litwareinc.com：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
