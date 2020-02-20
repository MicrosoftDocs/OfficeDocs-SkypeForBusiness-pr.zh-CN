---
title: Lync Server 2013：正在准备还原 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b397f389de461a04974fe063437caaabd9d4137
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>准备还原 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在出现故障后开始还原服务器和数据库之前，您需要确定以下内容：

  - 需要还原的内容。

  - 您需要还原的硬件、软件、数据和工具。

<div>

## <a name="determining-what-to-restore"></a>确定还原内容

本主题介绍如何还原在服务器、池或中央管理存储级别发生的 Lync Server 中断。 如果中央管理存储失败，Lync Server 部署将继续正常运行，但不能进行任何配置更改。 如果后端服务器或 Standard Edition Server 出现故障，则用户池将停止运行。 如果任何其他服务器出现故障，则故障的程度取决于服务器运行的服务器角色以及服务器是否承载了一个或多个数据库。

### <a name="what-to-restore"></a>要还原的内容

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
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">在 Lync Server 2013 中还原 Standard Edition 服务器</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理存储</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">在 Lync Server 2013 中还原承载中央管理存储的服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>企业版后端</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync Server 2013 中还原企业版后端服务器</a></p></td>
</tr>
<tr class="even">
<td><p>企业版镜像后端主服务器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">在 Lync Server 2013 中还原镜像的企业版后端服务器-主要</a></p></td>
</tr>
<tr class="odd">
<td><p>企业版镜像后端辅助服务器</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013-镜像中还原镜像的企业版后端服务器</a></p></td>
</tr>
<tr class="even">
<td><p>运行服务器角色的任何企业版服务器，如前端服务器、边缘服务器、控制器、中介服务器、或持久聊天服务器。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync Server 2013 中还原企业版成员服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>整个 Lync Server 池</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">在 Lync Server 2013 中还原 Lync Server 池</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 文件存储</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">在 Lync Server 2013 中还原文件存储</a></p></td>
</tr>
<tr class="odd">
<td><p>独立监控数据库或存档数据库</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">在 Lync Server 2013 中还原监视或存档数据</a></p></td>
</tr>
<tr class="even">
<td><p>独立的持久聊天数据库</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">在 Lync Server 2013 中还原持久聊天数据</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>收集硬件、软件和工具

在还原服务器时，您需要从新的或干净的计算机开始。 此外，还必须具有以下可用的硬件和软件：

  - 具有与发生故障的服务器相同的完全限定域名 (FQDN) 的干净或新服务器。
    
    <div>
    

    > [!IMPORTANT]  
    > 安装操作系统时，请确保不删除 Active Directory 域服务中的计算机帐户，并验证是否保留了帐户的组权限。

    
    </div>

  - 操作系统的安装软件。 若要安装操作系统，请使用组织确定的服务器部署过程和配置。 还原服务时，应具有这些过程和配置要求。

  - 适用于 SQL Server 2012 或 SQL Server 2008 R2 的安装软件。 若要安装数据库服务器，请使用组织确定的适当版本的 SQL Server 和数据库服务器部署过程和配置。 还原服务时，应具有这些过程和配置要求。
    
    <div>
    

    > [!NOTE]  
    > 安装本地配置存储时，Lync Server 部署向导会自动在每个 Standard Edition 服务器和任何其他 Lync Server 服务器上安装 SQL Server 2012 Express，除非您已预安装 SQL Server 2012 或 SQL Server 2008 R2服务器。

    
    </div>

  - 用于生成系统映像的软件。
    
    <div>
    

    > [!TIP]  
    > 我们建议您在安装操作系统和 SQL Server 后，以及在开始还原之前，获取系统的图像副本，以便您可以将此映像用作回滚点，以防还原过程中出现问题。

    
    </div>

  - Lync Server 2013 安装软件。 Lync Server 部署向导位于 Lync Server 安装文件夹或位于\\安装程序\\amd64\\setup.exe 的媒体中。

还原期间，使用以下工具：

  - Lync Server 命令行管理程序 cmdlet

  - Import-Export-csuserdata

  - 用于还原 Windows 文件夹的工具

  - 拓扑生成器

  - SQL Server 数据库实用工具，例如 SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>准备还原服务器

在还原服务器之前，必须执行以下步骤：

1.  安装操作系统。

2.  如果服务器是后端服务器，请安装 SQL Server 2012 或 SQL Server 2008 R2。

3.  还原或重新注册证书。 有关证书的详细信息，请参阅[Lync Server 2013： data 中的 "备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)" 中的 "其他备份要求"。

4.  在开始还原之前获取系统的映像以用作回滚点，以防还原过程中出现问题。

<div>


> [!NOTE]  
> 本主题中的过程中描述的 Lync Server 部署向导和 cmdlet 以及相关主题设置所有必需的访问控制列表（Acl）。



</div>

验证您计划还原的组件所需的硬件和软件在开始还原之前是否可用。 在安装操作系统和 SQL Server 后，以下还原过程中的大多数步骤都可以远程运行。 过程中注明的例外情况除外。

您还应了解您的组织的备份和还原计划以及上一次备份中的信息，如本文档中的工作表中的信息（有关详细信息，请参阅[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)），以便在开始还原之前使用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

