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
ms.openlocfilehash: fe45f9e7d422da53e9dc531721d4b678685eb2b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中为反向代理设置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

每个反向代理服务器都要求有一个 web 服务器证书供侦听服务使用。 Web 服务器证书必须由公共证书颁发机构（CA）颁发。

有关此和其他证书要求的详细信息，请参阅[Lync Server 2013 中的外部用户访问证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>为反向代理设置 Web 服务证书

  - 你应该已经设置了反向代理，包括设置 Web 服务证书。 如果在开始部署 Edge 服务器之前未执行此操作，请使用[设置 Lync Server 2013 的反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的过程来创建请求并安装 web 服务证书，然后创建每个 web 发布规则并将其配置为使用该证书。

</div>

</div>

<span> </span>

</div>

</div>

</div>

