---
title: Lync Server 2013：查看有关单个 SIP 中继的信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18b65d119b917d5ba48ef3e6805e4f70ea482ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中查看有关单个 SIP 中继的信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

SIP 中继用于通过公共交换电话网络连接 Lync Server 2013 语音 over IP 电话网络。 在本产品的以前版本中，中继用来将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关仅限于一个中继。 因此，PSTN 网关和 SIP 中继基本上完全相同。 对于管理员而言，这意味着他们只需通过查看有关相关联的 PSTN 网关的信息，即可查看有关个别 SIP 中继的信息。

但是，在 Lync Server 2013 中，多个中继现在可以分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。 而这意味着管理员必须使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet，才能查看有关个别 SIP 中继的信息。

CsTrunk cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>查看所有 SIP 中继的信息

  - 以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>查看特定 SIP 中继的信息

  - 此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看分配到池的所有 SIP 中继的信息

  - 在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

