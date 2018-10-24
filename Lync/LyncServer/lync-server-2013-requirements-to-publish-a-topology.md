---
title: Lync Server 2013：发布拓扑的要求
TOCTitle: 发布拓扑的要求
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg195733(v=OCS.15)
ms:contentKeyID: 49313465
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中发布拓扑的要求

 

_**上一次修改主题：** 2013-02-21_

本主题介绍了特定于发布拓扑（无论使用 拓扑生成器还是 Lync Server 2013 命令行管理程序命令行接口进行发布）的基础结构和软件要求。这些要求是适用于所有 Lync Server 2013 管理工具的一般操作系统、软件和权限要求之外的要求。在发布拓扑之前，请确保您满足所有管理工具要求。

  - 您必须在加入了正创建的 Lync Server 2013 部署的所在的域或林的计算机上运行 拓扑生成器，以便完成 Active Directory 域服务 准备步骤，这将使您能够使用相应计算机上的管理工具来成功发布拓扑。

  - 拓扑中定义的计算机必须加入域（边缘服务器除外）并且位于 AD DS 中。但在发布拓扑时，计算机不需要处于联机状态。

  - 必须创建池的文件共享，且该文件共享必须对远程用户可用。

  - 若要发布 Enterprise Edition 前端池，必须将基于 SQL Server 的后端服务器加入将部署服务器的域，将该后端服务器联机，并为其配置适当的防火墙规则以使其对远程用户可用。有关指定防火墙例外的详细信息，请参阅 [了解 SQL Server 与 Lync Server 2013 一起使用时的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)。有关配置 SQL Server 的其他详细信息，请参阅 [为 Lync Server 2013 配置 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)。
    
    > [!NOTE]  
	> Standard Edition Server 具有将接受已发布配置的并置数据库。必须在 Lync Server 部署向导中首先运行“准备第一台 Standard Edition Server”设置任务。
    


## 另请参阅

#### 任务

[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)  
[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)  

#### 概念

[Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)  

#### 其他资源

[Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

