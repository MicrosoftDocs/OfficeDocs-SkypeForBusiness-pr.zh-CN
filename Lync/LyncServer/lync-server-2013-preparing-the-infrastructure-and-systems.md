---
title: Lync Server 2013：准备基础结构和系统
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>为 Lync Server 2013 准备基础结构和系统

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

部署 Lync Server 2013 需要使用拓扑生成器来定义和发布拓扑设计。 若要确定拓扑所需的组件，请使用拓扑生成器创建和保存拓扑设计。 在拓扑生成器中发布拓扑之前，请执行以下操作：

  - 获取并安装拓扑结构设计中使用拓扑生成器创建和保存的每个组件的硬件，包括所有所需的计算机（运行 Lync Server 2013 的服务器、数据库服务器、运行 Internet 信息服务的服务器）（IIS）和反向代理服务器（根据需要）、网络适配器、硬件负载平衡器和存储设备（如文件服务器）。 有关如何定义拓扑以指定部署所需的组件的详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。 有关服务器硬件要求的详细信息，请参阅支持文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。

  - 请确保网络基础结构满足要求。 有关详细信息，请参阅规划文档中[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。

  - 设置 Active Directory 域服务。 若要发布和启用拓扑，你需要由 AD DS 中的计算机帐户表示的内部服务器。 这可通过将计算机加入到 AD DS 来完成。 有关准备 AD DS 的详细信息，请参阅[准备适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 创建文件共享。 标准版服务器可以托管所需文件的文件共享，而在企业部署中，文件共享不能托管在前端服务器上。 必须正确设置用于部署和设置文件夹和共享的访问控制列表（ACL）所需的权限和组成员身份，拓扑生成器才能成功完成。 应确保运行拓扑生成器的人员具有下列权限和组成员身份：
    
      - 本地管理员的成员
    
      - 域用户的成员
    
      - 文件存储的 "共享和文件夹" 的 "完全控制"

  - 对于企业版，请安装并配置 SQL Server。 若要使 SQL Server 安装成功，基于 SQL Server 的服务器必须处于联机状态，并且发布拓扑的人员是 SQL Server 上的本地管理员，并且必须是 sql server 实例上 SQL Server sysadmin 组的成员。

完成本主题中所述的所有准备任务后，在发布拓扑之前，还需要执行其他准备任务，包括安装 Windows 操作系统和其他必备软件，设置IIS 和配置 DNS。 有关这些任务的详细信息，请参阅[运行 Lync server 2013 的服务器的系统要求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、[配置 lync SERVER 2013 的 IIS](lync-server-2013-configure-iis.md)以及[准备适用于 lync server 2013 的基础结构和系统](lync-server-2013-preparing-the-infrastructure-and-systems.md)。 此外，你应该熟悉客户和客户端要求。 有关详细信息，请参阅[在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 的硬件安装](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 的软件安装](lync-server-2013-software-setup.md)

  - [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)

  - [为 Lync Server 2013 配置 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 中配置前端池或 Standard Edition 服务器的 DNS 记录](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

