---
title: Lync Server 2013：强化和保护数据库
description: Lync Server 2013：强化和保护数据库。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577428"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>强化和保护 Lync Server 2013 的数据库

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-05_

Microsoft Lync Server 2013 还取决于用于存储用户信息、会议状态、存档数据和呼叫详细记录 (Cdr) 的 SQL Server 数据库。 您可以在 Lync Server 后端数据库上最大限度地提高 Lync Server 2013 数据的可用性，具体方法是以改进容错和简化故障排除的方式对应用程序数据进行分区。 要实现这些目标，可按照以下方式对应用程序数据进行分区：

  - **使用服务器分区最佳做法**    将您的操作系统、应用程序和程序文件与数据文件分开。

  - **存储事务日志文件和数据库文件**    单独存储这些文件以提高容错能力并优化恢复，并将其存储在加密的磁盘或卷上。

  - **使用服务器群集**    对后端服务器进行群集以优化 Lync Server 2013 系统可用性。

  - **确保所有数据备份均已加密并正确处理**    丢失、放弃或错放备份媒体可能会对 Lync Server 2013 部署的数据安全造成重大威胁

在除 Standard Edition server 之外的任何 Lync Server 2013 服务器上，不能远程访问 RTCLOCAL 实例) 的 SQL Server Express (实例，并且不会创建任何本地防火墙例外，除非在 Standard Edition Server 上使用 SQL Server Express。 在 Standard Edition Server 上，后端数据库和中央管理存储 (CMS) 均设置为可远程访问。 要强化 SQL Server 数据库，可执行以下操作：

  - 在 Standard Edition Server 上自定义 SQL Server Express 防火墙，限制可远程访问数据库的服务器的范围。默认情况下，所有 IP 地址都可以远程访问数据库。

  - 使用 SQL Server 配置管理器指定 SQL Server 远程访问使用的协议、IP 地址和端口：
    
      - Lync Server 2013 使用 TCP/IP 协议。 它支持 IP 版本 4 (IPv4)，但不支持 IP 版本 6 (IPv6)。
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 可以在启用了双 IP 堆栈的网络中正常运行。

        
        </div>
    
      - Lync Server 2013 支持多个 IP 地址 (多穴网络地址卡) 。 可以指定 SQL Server 只侦听特定 IP 地址（单个地址或子网），并且只使用特定协议。
    
      - Lync Server 2013 支持静态和动态 SQL Server 端口。

  - 应在静态（非默认）端口上运行 SQL Server，而不要运行 SQL Server 浏览器（这样就不会向客户端报告侦听端口）。 这需要在每个 SQL Server 客户端上进行自定义配置，包括前端服务器、监视服务器、存档服务器和管理控制台 (运行 Lync Server 命令行管理程序、Lync Server 控制面板或拓扑生成器) ，以及运行 Lync Server 数据库的所有其他服务器) 。

<div>


> [!NOTE]  
> 只能将数据库访问权限赋予受信任的数据库管理员。 恶意数据库管理员可以在数据库中插入或修改数据，以通过 Lync Server 2013 服务器获取权限，或从服务获取敏感信息，即使尚未授予数据库管理员对 Lync Server 2013 服务器的直接访问或控制权限也是如此。



</div>

有关自定义配置和强化 SQL Server 数据库的详细信息，请参阅 NextHop 博客文章 "使用 Lync Server 2010 with a Custom SQL Server Network Configuration" at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。

<div>


> [!NOTE]  
> 您还可以加强操作系统和应用程序服务器，也可以使用组策略在 Lync Server 部署中实施安全 lockdowns。 有关详细信息，请参阅 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">强化和保护 Lync Server 2013 的服务器和应用程序</A>。



</div>

</div>

<span> </span>

</div>

</div>

</div>

