---
title: Lync Server 2013：对池进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中对池进行故障回复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

在发生灾难的池重新联机后 (即在此示例中为 Pool1), 请执行以下步骤将你的部署还原到正常的工作状态。

请注意, 故障回复过程需要几分钟才能完成。作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。

1.  通过键入以下 cmdlet 对最初驻留在 Pool1 中的用户进行故障回复, 并已故障转移到 Pool2:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

无需执行其他步骤。 如果您通过中央管理服务器进行了故障转移, 您可以将其保留在 Pool2 中。

</div>

<span> </span>

</div>

</div>

</div>

