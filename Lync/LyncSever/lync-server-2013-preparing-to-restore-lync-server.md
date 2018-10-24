---
title: 准备还原 Lync Server
TOCTitle: 准备还原 Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202179(v=OCS.15)
ms:contentKeyID: 52061056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 准备还原 Lync Server

 

_**上一次修改主题：** 2015-03-09_

在出现故障后开始还原服务器和数据库之前，您需要确定以下内容：

  - 需要还原的内容。

  - 执行还原时所需的硬件、软件、数据和工具。

## 确定还原内容

本主题介绍如何还原在服务器、池或中央管理存储级别出现的 Lync Server 故障。如果中央管理存储出现故障，Lync Server 部署将继续运行，但您无法进行任何配置更改。如果后端服务器或 Standard Edition Server 出现故障，则用户池将停止运行。如果任何其他服务器出现故障，则故障的程度取决于服务器运行的服务器角色以及服务器是否承载了一个或多个数据库。

### 要还原的内容

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果此项发生故障</th>
<th>请参阅此节：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">还原 Standard Edition Server</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理存储</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">还原承载中央管理存储的服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition 后端服务器</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">还原 Enterprise Edition 后端服务器</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 镜像后端主服务器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">还原镜像企业版后端服务器 - 主服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Edition 镜像后端辅助服务器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">还原镜像企业版后端服务器 - 镜像</a></p></td>
</tr>
<tr class="even">
<td><p>运行服务器角色的任何 Enterprise Edition Server，例如前端服务器、边缘服务器、控制器、中介服务器或持久聊天服务器。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">还原 Enterprise Edition 成员服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>整个 Lync Server 池</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">还原 Lync Server 池</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 文件存储</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">还原文件存储</a></p></td>
</tr>
<tr class="odd">
<td><p>独立镜像数据库或存档数据库</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">还原监控或存档数据</a></p></td>
</tr>
<tr class="even">
<td><p>独立持久聊天数据库</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">还原持久聊天数据</a></p></td>
</tr>
</tbody>
</table>


## 收集硬件、软件和工具

在还原服务器时，您需要从新的或干净的计算机开始。此外，您还必须具有以下可用的硬件和软件：

  - 具有与发生故障的服务器相同的完全限定域名 (FQDN) 的干净或新服务器。
    
    > [!IMPORTANT]
    > 在安装操作系统时，请确保不要删除 Active Directory 域服务 中的计算机帐户，并确保保留该帐户的组权限。


  - 操作系统的安装软件。若要安装操作系统，请使用组织确定的服务器部署过程和配置。在还原服务时，您应满足这些过程和配置要求。

  - SQL Server 2012 或 SQL Server 2008 R2 的安装软件。若要安装数据库服务器，请使用组织确定的适当版本的 SQL Server 和数据库服务器部署过程和配置。在还原服务时，您应满足这些过程和配置要求。
    
    > [!NOTE]  
	> 在安装本地配置存储时，Lync Server 部署向导会自动在每台 Standard Edition Server 和任何其他 Lync Server 服务器上安装 SQL Server 2012 Express，除非您在服务器上预先安装了 SQL Server 2012 或 SQL Server 2008 R2。
    


  - 用于生成系统映像的软件。
    
    > [!TIP]
    > 建议在安装操作系统和 SQL Server 之后、开始还原之前，生成系统的映像副本，以便可以在还原期间出错时使用此映像作为回滚点。


  - Lync Server 2013 安装软件。Lync Server 部署向导位于 Lync Server 安装文件夹或媒体中的 \\setup\\amd64\\Setup.exe。

还原期间，使用以下工具：

  - Lync Server 命令行管理程序 cmdlet

  - Import-CsUserData

  - 用于还原 Windows 文件夹的工具

  - 拓扑生成器

  - SQL Server 数据库实用工具，例如 SQL Server Management Studio

## 准备还原服务器

在还原服务器之前，您必须执行以下步骤：

1.  安装操作系统。

2.  如果服务器是后端服务器，请安装 SQL Server 2012 或 SQL Server 2008 R2。

3.  还原或重新注册您的证书。有关证书的详细信息，请参阅[备份和还原要求：数据](lync-server-2013-backup-and-restoration-requirements-data.md)中的“其他备份要求”。

4.  在开始还原之前生成系统映像以便在还原期间出错时用作回滚点。

> [!NOTE]  
> 本主题及相关主题的过程中介绍的 Lync Server 部署向导和 cmdlet 会设置所有必需的访问控制列表 (ACL)。



确保在开始还原之前，您计划还原的组件所需的硬件和软件可用。在安装操作系统和 SQL Server 后，以下还原过程中的大多数步骤都可以远程运行。过程中注明的例外情况除外。

在开始还原之前，您还应具有组织的备份和还原计划以及有关上次备份的信息，例如本文档中的工作表中的信息（有关详细信息，请参阅[备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)）。

