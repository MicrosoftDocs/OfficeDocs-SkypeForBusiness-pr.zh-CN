---
title: Lync Server 2013：查看有关各个 SIP 中继的信息
description: Lync Server 2013：查看有关各个 SIP 中继的信息。
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
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569608"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中查看有关各个 SIP 中继的信息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

SIP 中继用于通过公共交换电话网络连接 Lync Server 2013 Voice over IP phone 网络。 在产品的以前版本中，中继用于将出站呼叫从中介服务器路由到 PSTN 网关，并且每个网关限制为单个中继。 因此，PSTN 网关和 SIP 中继本质上是相同的。 对于管理员而言，这意味着他们只需查看有关相关 PSTN 网关的信息即可查看有关单个 SIP 中继的信息。

但是，在 Lync Server 2013 中，现在可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不再是同一个。 反过来，这意味着管理员必须使用新的 [CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 才能查看有关单个 SIP 中继的信息。

Get-CsTrunk cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>查看所有 SIP 中继的信息

  - 以下命令将返回有关您组织中使用的所有 SIP 中继的信息：
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>查看特定 SIP 中继的信息

  - 此命令仅返回标识为 pstngateway：192.168.0.240 的 SIP 中继的信息：
    
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

