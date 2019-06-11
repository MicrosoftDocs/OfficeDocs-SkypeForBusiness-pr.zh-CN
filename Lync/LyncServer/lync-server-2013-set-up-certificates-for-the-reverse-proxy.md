---
title: Lync Server 2013：为反向代理设置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中为反向代理设置证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

每个反向代理服务器都要求有一个 web 服务器证书供侦听服务使用。 Web 服务器证书必须由公共证书颁发机构 (CA) 颁发。

有关此和其他证书要求的详细信息, 请参阅[Lync Server 2013 中的外部用户访问证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>为反向代理设置 Web 服务证书

  - 你应该已经设置了反向代理, 包括设置 Web 服务证书。 如果在开始部署 Edge 服务器之前未执行此操作, 请使用[设置 Lync Server 2013 的反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的过程来创建请求并安装 web 服务证书, 然后创建每个 web 发布规则, 然后将其配置为使用证书。

</div>

</div>

<span> </span>

</div>

</div>

</div>

