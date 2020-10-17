---
title: Lync Server 2013：控制器概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb187711174785833716b2d14ffe7979cedcbc96
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520819"
---
# <a name="overview-of-the-director-in-lync-server-2013"></a>Lync Server 2013 中的控制器概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

控制器是运行 Lync Server 2013 的服务器，用于验证用户请求，但不会驻留任何用户帐户。 您可以选择在以下两种方案中部署控制器：

  - 如果通过部署边缘服务器启用外部用户访问，则还应部署控制器。 在这种情况下，控制器对外部用户进行身份验证，然后将其流量传递到内部服务器。 当使用控制器对外部用户进行身份验证时，它将从对这些用户执行身份验证的开销中缓解前端池服务器。 它还有助于将内部前端池与恶意流量（如拒绝服务攻击）隔离。 如果网络受到此类攻击中无效外部流量的攻击，则这些流量将终止于控制器。

  - 如果在中央站点部署多个前端池，通过向该站点添加控制器，可以简化身份验证请求并提高性能。 在这种情况下，所有请求都首先转到控制器，然后再将它们路由到正确的前端池。

</div>

<span> </span>

</div>

</div>

</div>

