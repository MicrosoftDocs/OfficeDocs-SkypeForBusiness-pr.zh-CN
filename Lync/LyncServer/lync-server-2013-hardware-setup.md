---
title: Lync Server 2013：硬件安装
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 的硬件安装

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

在需要用于实现拓扑的基础结构中设置硬件和其他组件需要在拓扑生成器中发布拓扑之前执行以下操作：

  - 使用拓扑生成器创建和保存的拓扑设计中的每个组件安装硬件，包括所有所需的计算机（运行 Lync Server 2013、数据库服务器、运行 Internet 信息服务（IIS）的服务器）和反向代理服务器（根据需要）、网络适配器、硬件负载平衡器和存储设备（如文件服务器）。 确认已遵循网络适配器的号码和速度建议。 如果你要使用硬件负载平衡器，请确保你拥有来自供应商的适当信息，以便将其配置为与 Lync Server 2013 配合使用。 如果你将使用文件服务器或其他服务器来承载 Lync Server 所需的文件共享，请确保服务器可用，并且已准备好配置文件共享。 有关如何定义拓扑以指定部署所需的组件的详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。 有关服务器硬件要求的详细信息，请参阅支持文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。

  - 请确保网络基础结构满足要求。 有关详细信息，请参阅规划文档中[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。

  - 设置 Active Directory 域服务。 设置 AD DS 包括准备 AD DS 和定义要在 AD DS 中部署的所有组件。 有关准备 AD DS 的详细信息，请参阅部署文档中的[准备适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 设置创建文件共享所需的权限。 在发布拓扑时，由 Lync Server 2013 使用文件共享的权限会自动配置为拓扑生成器。 但是，用于发布拓扑的用户帐户必须具有文件共享的完全控制（读/写/修改）才能使拓扑生成器配置所需的权限。 若要确保可在拓扑生成器发布过程中正确管理文件共享，应将用户所属的用户或域组作为文件共享所在的计算机上的本地管理员组的成员。 在多域方案中，域 A 用户或组应成为文件共享所在的域 B 中计算机上的本地管理员组的成员。
    
    有关使用分布式文件系统（DFS）中的文件共享进行更新的详细信息，请参阅[为 Lync Server 2013 配置文件存储](lync-server-2013-configure-dfs-file-storage.md)。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013 的文件共享无法在前端服务器上找到。

    
    </div>

  - 安装和设置用于 Web 服务的硬件负载平衡器。 在部署了域名系统（DNS）负载平衡的情况下，你仍然需要对这些池使用硬件负载平衡器，但仅适用于 HTTP/HTTPS 流量。 硬件负载平衡器用于来自端口443和80的客户端的 HTTPS 流量。 虽然您仍需要这些池的硬件负载平衡器，但它们的设置和管理主要用于 HTTP/HTTPS 流量，这些流量习惯于硬件负载平衡器的管理员。

完成本主题中所述的所有准备任务后，在发布拓扑之前，您还需要：

  - [在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [为 Lync Server 2013 配置 IIS](lync-server-2013-configure-iis.md)

  - [为 Lync Server 2013 配置 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 中配置前端池或 Standard Edition 服务器的 DNS 记录](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

