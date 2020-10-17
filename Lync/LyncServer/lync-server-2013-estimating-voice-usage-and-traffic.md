---
title: Lync Server 2013：估计语音使用和流量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9541619578c69a571d93d8c4960b3ecb33476027
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531999"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>估计 Lync Server 2013 的语音使用和流量

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-08-07_

Microsoft Lync Server 2013，规划工具使用以下指标估计每个站点上的用户流量和支持该流量所需的端口数。

  - <span></span>  
    对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。

  - <span></span>  
    对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。

  - <span></span>  
    对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。

反过来，端口数将决定所需的中介服务器和网关的数量。 公共交换电话网络 (PSTN) 网关，大多数组织都考虑从2个端口向多达960个端口部署大小范围。  (更大的网关，但主要由电话服务提供程序使用。 ) 

例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。

</div>

<span> </span>

</div>

</div>

</div>

