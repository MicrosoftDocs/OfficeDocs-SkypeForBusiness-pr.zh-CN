---
title: Lync Server 2013：控制器概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Lync Server 2013 中的控制器概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

Director 是运行 Lync Server 2013 的服务器, 用于验证用户请求, 但不会在家任何用户帐户。 您也可以在以下两种方案中部署控制器:

  - 如果通过部署边缘服务器启用外部用户访问, 则还应部署 Director。 在此方案中, 控制器对外部用户进行身份验证, 然后将其流量传递到内部服务器。 当使用 Director 对外部用户进行身份验证时, 它将从执行这些用户的身份验证的开销中免除前端池服务器。 它还有助于将内部前端池与恶意流量 (如拒绝服务攻击) 隔离。 如果网络被此类攻击中的无效外部通信所淹没, 则该流量将在 Director 处结束。

  - 如果在中心网站上部署多个前端池, 则通过向该网站添加 Director, 可以简化身份验证请求并提高性能。 在此方案中, 所有请求首先转到 Director, 然后将其路由到正确的前端池。

</div>

<span> </span>

</div>

</div>

</div>

