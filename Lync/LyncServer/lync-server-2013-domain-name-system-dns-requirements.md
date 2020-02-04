---
title: Lync Server 2013：域名系统（DNS）要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 的域名系统（DNS）要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-18_

若要部署 Lync Server，你必须创建可启用客户端和服务器发现的域名系统（DNS）记录，如果你的组织希望支持它，还可以支持自动客户端登录。

Lync 服务器通过以下方式使用 DNS：

  - 发现内部服务器或池以进行服务器至服务器的通信。

  - 允许客户发现用于各种 SIP 事务的前端池或标准版服务器。

  - 允许未登录的统一通信（UC）设备发现运行设备更新 Web 服务的前端池或标准版服务器，获取更新和发送日志。

  - 允许外部服务器和客户端连接到边缘服务器或 HTTP 反向代理，以便发送即时消息（IM）或会议。

  - 允许外部 UC 设备通过 Edge 服务器或 HTTP 反向代理连接到设备更新 Web 服务并获取更新。

  - 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。

<div>

## <a name="in-this-section"></a>本节内容

  - [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 中前端池的 DNS 要求](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Lync Server 2013 中标准版服务器的 DNS 要求](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 中自动客户端登录的 DNS 要求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [具有 Lync Server 2013 的移动性 DNS 要求](lync-server-2013-dns-requirements-for-mobility.md)

  - [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

