---
title: Lync Server 2013：硬件安装
TOCTitle: 硬件安装
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425852(v=OCS.15)
ms:contentKeyID: 49312529
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的硬件安装

 

_**上一次修改主题：** 2013-02-21_

要安装实现拓扑所需的基础结构中必需的硬件和其他组件，必须在使用 拓扑生成器发布拓扑之前执行以下操作：

  - 为使用 拓扑生成器创建和保存的拓扑设计中的每个组件安装硬件，包括全部所需的计算机（运行 Lync Server 2013 的服务器、数据库服务器、运行 Internet Information Services (IIS) 的服务器和反向代理服务器，具体根据需要）、网络适配器、硬件负载平衡器和存储设备（如文件服务器）。确认您已遵循针对网络适配器的数量和速度的建议。如果要使用硬件负载平衡器，请确保您具有来自供应商的正确信息，以将其配置为用于 Lync Server 2013。如果要使用文件服务器或其他服务器来保存 Lync Server 需要的文件共享，请确保该服务器可用并且可用于配置文件共享。有关如何定义指定部署所需组件的拓扑的详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。有关服务器硬件要求的详细信息，请参阅可支持性文档中的[支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)。

  - 确保网络基础结构符合要求。有关详细信息，请参阅规划文档中的[Lync Server 2013 中的网络基础结构要求](lync-server-2013-network-infrastructure-requirements.md)。

  - 设置 Active Directory 域服务。设置 AD DS 包括准备 AD DS 和定义要在 AD DS 中部署的所有组件。有关准备 AD DS 的详细信息，请参阅部署文档中的 [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 设置创建文件共享所需的权限。在发布拓扑时，拓扑生成器将自动配置 Lync Server 2013 使用文件共享的权限。但是，用于发布拓扑的用户帐户必须在文件共享上具有完全控制权限（读/写/修改），拓扑生成器才能配置所需权限。要确保可在拓扑生成器发布过程中正确管理文件共享，用户或用户所属的域组应该成为文件共享所在计算机上本地 Administrators 组的成员。在多域方案中，域 A 用户或组应该成为文件共享所在域 B 中的计算机上本地 Administrators 组的成员。
    
    有关在分布式文件系统 (DFS) 中使用文件共享更新的详细信息，请参阅 [为 Lync Server 2013 配置文件存储](lync-server-2013-configure-dfs-file-storage.md)。
    
    > [!WARNING]
    > Lync Server 2013 Enterprise Edition 的文件共享不能位于 前端服务器上。


  - 为 Web 服务安装和设置硬件负载平衡器。部署域名系统 (DNS) 负载平衡后，还需要在这些池中使用硬件负载平衡器，但仅用于 HTTP/HTTPS 流量。硬件负载平衡器用于客户端通过端口 443 和 80 发送的 HTTPS 流量。尽管还需要在这些池中使用硬件负载平衡器，但是主要针对 HTTP/HTTPS 流量进行设置和管理，这都是硬件负载平衡器管理员所熟悉的内容。

完成本主题中介绍的所有准备任务后，在发布拓扑前，还需要执行以下操作：

  - [在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [为 Lync Server 2013 配置 IIS](lync-server-2013-configure-iis.md)

  - [为 Lync Server 2013 配置 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 中配置前端池或 Standard Edition 服务器的 DNS 记录](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

