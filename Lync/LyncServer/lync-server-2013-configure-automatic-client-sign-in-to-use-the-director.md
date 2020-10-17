---
title: Lync Server 2013：将自动客户端 Sign-In 配置为使用控制器
description: Lync Server 2013：将自动客户端 Sign-In 配置为使用控制器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9c45a1a677d3a30704d8dca1771ef865cef29ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546648"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a>将自动客户端 Sign-In 配置为在 Lync Server 2013 中使用控制器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

当您部署 Lync Server 2013、控制器或控制器池时，建议使用自动客户端 Sign-In 作为最佳实践。 有关如何为自动客户端登录配置 DNS 服务器的详细信息，请参阅规划文档中的 [Lync Server 2013 中的自动客户端登录的 dns 要求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) 。

如果已部署自动客户端登录，请参阅以下几节以在一台或多台控制器上配置自动客户端登录。

<div>

## <a name="single-director-instance"></a>单个控制器实例

如果已部署自动客户端 Sign-In 并将其指向前端服务器或前端池，则需要将 DNS SRV 记录更改为指向控制器。

</div>

<div>

## <a name="director-pool"></a>控制器池

如果已部署自动客户端 Sign-In 并将其指向前端服务器或前端池，则需要将 DNS SRV 记录更改为指向控制器池。

</div>

</div>

<span> </span>

</div>

</div>

</div>

