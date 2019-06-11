---
title: Lync Server 2013：DNS 基础结构支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa9670761e16032abf0c205bbb740cbe1f43c4a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 基础结构支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-08_

Lync Server 2013 需要域名系统 (DNS), 并通过以下方式使用它:

  - 发现内部服务器或池以进行服务器至服务器的通信。

  - 使客户能够发现用于各种 SIP 事务的前端池或标准版服务器。

  - 将会议的简单 Url 与托管这些会议的服务器相关联。

  - 允许外部服务器和客户端连接到边缘服务器, 或使用 HTTP 反向代理发送即时消息 (IM) 或会议。

  - 若要启用未登录的统一通信 (UC) 设备以发现前端池或运行设备更新 Web 服务的标准版服务器, 请获取更新和发送日志。

  - 使移动客户端能够自动发现 Web 服务资源, 而无需用户在设备设置中手动输入 Url。

  - 用于 DNS 负载平衡。

<div>


> [!NOTE]  
> Lync Server 2013 不支持国际化域名 (IDNs)。



</div>

<div>


> [!IMPORTANT]  
> 您指定的名称必须与服务器上配置的计算机名相同。 默认情况下，未加入到域的计算机的计算机名是一个短名称，而不是完全限定的域名 (FQDN)。 拓扑生成器使用 FQDN，而不是短名称。 因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。 分配您的 Lync Server、边缘服务器和池的 FQDN 时，<STRONG>只使用标准字符</STRONG>（包括 A–Z、a–z、0–9 和连字符）。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。



</div>

</div>

<span> </span>

</div>

</div>

</div>

