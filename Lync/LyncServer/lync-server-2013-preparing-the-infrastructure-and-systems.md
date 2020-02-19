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
ms.openlocfilehash: 95156c862c2c6fbee1b3a4625d8b9db234012a91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>为 Lync Server 2013 准备基础结构和系统

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

部署 Lync Server 2013 需要使用拓扑生成器来定义和发布拓扑设计。 若要确定拓扑所需的组件，请使用拓扑生成器创建并保存拓扑设计。 在拓扑生成器中发布您的拓扑之前，请执行以下操作：

  - 获取并安装拓扑结构设计中使用拓扑生成器创建和保存的每个组件的硬件，其中包括所有必需的计算机（运行 Lync Server 2013 的服务器、数据库服务器、运行 Internet 信息服务的服务器）（IIS）和反向代理服务器（如果适用）、网络适配器、硬件负载平衡器和存储设备（如文件服务器）。 有关如何定义拓扑以指定部署所需的组件的详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。 有关服务器的硬件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。

  - 请确保网络基础结构满足要求。 有关详细信息，请参阅规划文档中的[Lync Server 2013 的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。

  - 设置 Active Directory 域服务。 要发布和启用拓扑，您需要在 AD DS 中使用计算机帐户代表内部服务器。 通过将计算机加入 AD DS 可完成此操作。 有关准备 AD DS 的详细信息，请参阅[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 创建文件共享。 Standard Edition 服务器可以为所需文件承载文件共享，而在企业部署中，无法在前端服务器中托管文件共享。 必须正确设置在文件夹和共享中部署和设置访问控制列表 (ACL) 所需的权限和组成员身份，才能确保拓扑生成器成功完成操作。 应确保运行拓扑生成器的人员具有以下权限和组成员身份：
    
      - 本地 Administrators 成员
    
      - Domain Users 成员
    
      - 对文件存储的共享和文件夹的完全控制权限

  - 为 Enterprise Edition 安装和配置 SQL Server。若要成功安装 SQL Server，基于 SQL Server 的服务器必须处于联机状态，而发布拓扑的人员需要为 SQL Server 上的本地管理员，并且必须具有 SQL Server 实例上 SQL Server sysadmin 组的成员身份。

完成此主题中介绍的所有准备任务之后，发布拓扑之前，还需要执行其他准备任务，包括安装 Windows 操作系统和其他必备软件、设置 IIS 和配置 DNS。 有关这些任务的详细信息，请参阅[运行 Lync server 2013 的服务器的系统要求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、为[lync SERVER 2013 配置 IIS](lync-server-2013-configure-iis.md)以及[准备 lync server 2013 的基础结构和系统](lync-server-2013-preparing-the-infrastructure-and-systems.md)。 此外，您应该熟悉客户端和客户端要求。 有关详细信息，请参阅[在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 的硬件设置](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 的软件安装程序](lync-server-2013-software-setup.md)

  - [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)

  - [为 Lync Server 2013 配置 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 for a 前端池或 Standard Edition Server 中配置 DNS 记录](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

