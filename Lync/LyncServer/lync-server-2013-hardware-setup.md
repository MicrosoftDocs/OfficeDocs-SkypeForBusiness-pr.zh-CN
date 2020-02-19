---
title: Lync Server 2013：硬件安装程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 的硬件设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

若要在基础结构中设置需要实现拓扑所需的硬件和其他组件，需要在拓扑生成器中发布拓扑之前，执行以下操作：

  - 为拓扑设计中使用拓扑生成器创建和保存的每个组件安装硬件，其中包括所有必需的计算机（运行 Lync Server 2013 的服务器、数据库服务器、运行 Internet 信息服务的服务器（IIS）和根据需要反向代理服务器）、网络适配器、硬件负载平衡器和存储设备（如文件服务器）。 确认您已遵循针对网络适配器的数量和速度的建议。 如果要使用硬件负载平衡器，请确保供应商提供了正确的信息，以便将其配置为与 Lync Server 2013 一起使用。 如果要使用文件服务器或其他服务器来承载 Lync Server 所需的文件共享，请确保该服务器可用，并且已准备好配置文件共享。 有关如何定义拓扑以指定部署所需的组件的详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。 有关服务器的硬件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。

  - 请确保网络基础结构满足要求。 有关详细信息，请参阅规划文档中的[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。

  - 设置 Active Directory 域服务。 设置 AD DS 包括准备 AD DS 和定义要在 AD DS 中部署的所有组件。 有关准备 AD DS 的详细信息，请参阅部署文档中的[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 设置创建文件共享所需的权限。 由 Lync Server 2013 使用文件共享的权限是在发布拓扑时由拓扑生成器自动配置的。 但是，用于发布拓扑的用户帐户必须具有对文件共享的完全控制权限（读/写/修改），以便拓扑生成器能够配置所需的权限。 若要确保在拓扑生成器发布过程中可以正确管理文件共享，应将用户所属的用户或域组设为文件共享所在的计算机上本地 Administrators 组的成员。 在多域方案中，域 A 用户或组应该成为文件共享所在域 B 中的计算机上本地 Administrators 组的成员。
    
    有关使用分布式文件系统（DFS）中的文件共享进行更新的详细信息，请参阅[Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 的文件共享不能位于前端服务器上。

    
    </div>

  - 安装和设置用于 Web 服务的硬件负载平衡器。 部署域名系统 (DNS) 负载平衡后，还需要在这些池中使用硬件负载平衡器，但仅用于 HTTP/HTTPS 流量。 硬件负载平衡器用于客户端通过端口 443 和 80 发送的 HTTPS 流量。 尽管还需要在这些池中使用硬件负载平衡器，但是主要针对 HTTP/HTTPS 流量进行设置和管理，这都是硬件负载平衡器管理员所熟悉的内容。

完成本主题中介绍的所有准备任务后，在发布拓扑前，还需要执行以下操作：

  - [在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [为 Lync Server 2013 配置 IIS](lync-server-2013-configure-iis.md)

  - [为 Lync Server 2013 配置 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 for a 前端池或 Standard Edition Server 中配置 DNS 记录](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

