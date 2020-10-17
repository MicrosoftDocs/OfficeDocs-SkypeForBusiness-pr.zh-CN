---
title: Lync Server 2013：对池进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ad8ee15d0242a5512284e00064dfe9b49c41c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522359"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中对池进行故障回复

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

在经历灾难的池恢复联机（即此示例中的 Pool1）后，执行以下步骤来使部署恢复常规工作状态。

请注意，故障回复过程需要几分钟时间才能完成。一个 20,000 个用户的池需要占用 60 分钟的时间，可以此为参考。

1.  通过键入以下 cmdlet 返回到最初驻留在 Pool1 中并已故障转移到 Pool2 的用户：
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

无需执行其他步骤。 如果对中央管理服务器进行了故障转移，则可以将其保留在 Pool2 中。

</div>

<span> </span>

</div>

</div>

</div>

