---
title: Lync Server 2013：DNS 基础结构支持
TOCTitle: 域名系统 (DNS) 基础结构支持
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425850(v=OCS.15)
ms:contentKeyID: 49312493
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DNS 基础结构支持

 

_**上一次修改主题：** 2013-03-08_

Lync Server 2013 需要域名系统 (DNS) 并通过以下方式使用该系统：

  - 发现内部服务器或池以进行服务器至服务器的通信。

  - 使客户端可以发现用于各种 SIP 事务的前端池或 Standard Edition 服务器。

  - 将会议的简单 URL 与托管这些会议的服务器相关联。

  - 使外部服务器和客户端可以连接至用于即时消息 (IM) 或会议的边缘服务器或 HTTP 反向代理。

  - 使未登录的统一通信 (UC) 设备可以发现运行设备更新 Web 服务的前端池或 Standard Edition 服务器，获得更新和发送日志。

  - 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。

  - 为了 DNS 负载平衡。

> [!NOTE]  
> Lync Server 2013 不支持国际化域名 (IDN)。



> [!IMPORTANT]
> 您指定的名称必须与服务器上配置的计算机名相同。默认情况下，未加入到域的计算机的计算机名是一个短名称，而不是完全限定的域名 (FQDN)。 拓扑生成器使用的是 FQDN，而不是短名称。因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。分配您的 Lync Server、边缘服务器和池的 FQDN 时，<strong>只使用标准字符</strong>（包括 A–Z、a–z、0–9 和连字符）。不要使用 Unicode 字符或下划线。外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。

