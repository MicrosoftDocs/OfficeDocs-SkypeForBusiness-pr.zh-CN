---
title: Lync Server 2013：为反向代理设置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d03cec1dd2397b8471788f5c4661305e7ea93e42
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中为反向代理设置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

每台反向代理服务器都需要一个 Web 服务器证书，以供侦听服务使用。该 Web 服务器证书必须是由公共证书颁发机构 (CA) 颁发的。

有关此证书和其他证书要求的详细信息，请参阅[Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>为反向代理设置 Web 服务证书

  - 您应该已经设置了反向代理，包括设置 Web 服务证书。 如果在启动边缘服务器的部署之前未执行此操作，请使用为[Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的过程来创建请求并安装 web 服务证书，然后创建每个 web 发布规则并将其配置为使用证书。

</div>

</div>

<span> </span>

</div>

</div>

</div>

