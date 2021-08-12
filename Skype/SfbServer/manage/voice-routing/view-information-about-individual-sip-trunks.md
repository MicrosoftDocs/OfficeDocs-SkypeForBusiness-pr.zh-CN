---
title: Skype for Business Server - 查看有关单个 SIP 中继的信息
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
description: 在Skype for Business Server中，可以将多个中继分配给一个 PSTN 网关。 网关和中继不是同一个，管理员必须使用 Get-CsTrunk cmdlet 查看有关单个 SIP 中继的信息。
ms.openlocfilehash: f78aad8aa55202cdd59107be8f5e66dc2f83e1d336dc2f66c4982b7f534c88cc
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848387"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype for Business Server - 查看有关单个 SIP 中继的信息

在Skype for Business Server中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不是一个相同的，并且管理员必须使用[Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 中继的信息。

该Get-CsTrunk cmdlet 可以从命令行管理程序Skype for Business Server或远程会话运行Windows PowerShell。

**查看所有 SIP 中继的信息**

以下命令返回有关组织使用的所有 SIP 中继的信息：

`Get-CsTrunk`

**查看特定 SIP 中继的信息**

此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看分配给池的所有 SIP 中继的信息**

此示例返回分配给池池的所有 SIP 中继 atl-cs-001.litwareinc.com：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
