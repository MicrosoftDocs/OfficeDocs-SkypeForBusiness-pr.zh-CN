---
title: Lync Server 2013：为反向代理服务器创建 DNS 记录
TOCTitle: 为反向代理服务器创建 DNS 记录
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429719(v=OCS.15)
ms:contentKeyID: 49313989
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为反向代理服务器创建 DNS 记录

 

_**上一次修改主题：** 2013-03-29_

按照[在 Lync Server 2013 中配置边缘支持的 DNS](lync-server-2013-configure-dns-for-edge-support.md) 中所述，创建指向 Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1、Forefront Threat Management Gateway 2010 Server 或 Internet Information Server 应用程序请求路由的公共外部接口的外部 DNS A 记录。需要以下内容的 DNS 记录：各个池的外部 Web 服务 FQDN、控制器（或控制器池）和各个简单 URL。

反向代理的客户端解析的最少 DNS 记录，必须创建以下记录：

  - 为控制器和控制器池定义已发布外部 Web 服务的主机 (A) 记录（例如，**webdirext.contoso.com**）

  - 为任何前端池和 Standard Edition Server 角色上承载的外部 Web 服务定义已发布外部 Web 服务的主机 (A) 记录（例如，**webext.contoso.com**）

  - 简单 URL 的主机 (A) 记录（例如， **dialin.contoso.com** 和 **meet.contoso.com** ）

  - Lync Discover 外部记录的主机 (A) 记录，并且还提供指向所有 Web 应用程序（包括 Lync Web App、计划程序和移动）的 AutoDiscover 的指针（例如， **lyncdiscover.contoso.com** ）

  - Office Web Apps Server URL 的主机 (A) 记录（例如，**officewebapp01.contoso.com**）

有关详细信息，请参阅 [Lync Server 2013 中的 DNS 摘要 - 反向代理](lync-server-2013-dns-summary-reverse-proxy.md)。

