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
ms.openlocfilehash: c2e6516ee1162c02f2bebc8c385c2f41e87d7781
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>准备还原 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

在出现故障后开始还原服务器和数据库之前，需要确定以下事项：

  - 需要还原哪些内容。

  - 您需要恢复的硬件、软件、数据和工具。

<div>

## <a name="determining-what-to-restore"></a>确定要还原的内容

本主题介绍如何还原在服务器、池或中央管理存储级别发生的 Lync 服务器中断。 如果中央管理存储失败，则 Lync Server 部署将继续正常运行，但不能更改任何配置。 如果后端服务器或标准版服务器出现故障，用户池将停止运行。 如果任何其他服务器出现故障，则故障的大小取决于服务器运行的服务器角色以及服务器托管一个还是多个数据库。

### <a name="what-to-restore"></a>还原内容

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果此操作失败</th>
<th>请参阅以下部分：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">在 Lync Server 2013 中还原标准版服务器</a></p></td>
</tr>
<tr class="even">
<td><p>中央管理存储</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">在 Lync Server 2013 中还原托管中央管理存储的服务器</a></p></td>
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
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013 中还原镜像的企业版后端服务器-镜像</a></p></td>
</tr>
<tr class="even">
<td><p>任何运行服务器角色的企业版服务器，如前端服务器、边缘服务器、控制器、中介服务器、或持久聊天服务器。</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync Server 2013 中还原企业版成员服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>整个 Lync 服务器池</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">在 Lync Server 2013 中还原 Lync 服务器池</a></p></td>
</tr>
<tr class="even">
<td><p>企业版文件存储</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">在 Lync Server 2013 中还原文件存储</a></p></td>
</tr>
<tr class="odd">
<td><p>独立监视数据库或存档数据库</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">在 Lync Server 2013 中还原监视或存档数据</a></p></td>
</tr>
<tr class="even">
<td><p>独立的持久聊天数据库</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">在 Lync Server 2013 中还原永久聊天数据</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>收集硬件、软件和工具

还原服务器时，需要从新的或全新的计算机开始。 此外，你必须具有以下可用硬件和软件：

  - 具有与失败的服务器相同的完全限定的域名（FQDN）的全新服务器或新服务器。
    
    <div>
    

    > [!IMPORTANT]  
    > 在安装操作系统时，请确保不要删除 Active Directory 域服务中的计算机帐户，并验证是否保留帐户的组权限。

    
    </div>

  - 操作系统的安装软件。 若要安装操作系统，请使用服务器部署过程和由你的组织建立的配置。 还原服务时，应具备这些过程和配置要求。

  - SQL Server 2012 或 SQL Server 2008 R2 的安装软件。 若要安装数据库服务器，请使用相应版本的 SQL Server 和由你的组织建立的数据库服务器部署过程和配置。 还原服务时，应具备这些过程和配置要求。
    
    <div>
    

    > [!NOTE]  
    > 在安装本地配置存储时，Lync Server 部署向导会在每个标准版服务器和任何其他 Lync Server 服务器上自动安装 SQL Server 2012 Express，除非已预安装 SQL Server 2012 或 SQL Server 2008 R2服务器。

    
    </div>

  - 用于拍摄系统映像的软件。
    
    <div>
    

    > [!TIP]  
    > 我们建议你在安装操作系统和 SQL Server 之后以及开始还原之前获取系统的映像副本，以便你可以将此映像用作回退点，以防还原过程中出现错误。

    
    </div>

  - Lync Server 2013 安装软件。 Lync Server 部署向导位于 Lync Server 安装文件夹或位于\\安装\\amd64\\setup.exe 的媒体中。

在还原期间，你可以使用以下工具：

  - Lync Server Management Shell cmdlet

  - Import-CsUserData

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

4.  在启动还原之前获取系统的映像，以用作回滚点，以防还原过程中出现问题。

<div>


> [!NOTE]  
> 在本主题的过程中介绍的 Lync Server 部署向导和 cmdlet 以及相关主题，设置所有所需的访问控制列表（Acl）。



</div>

验证在开始还原之前，验证你要还原的组件是否可用所需的硬件和软件。 安装操作系统和 SQL Server 后，可以远程运行以下还原过程中的大部分步骤。 这些过程中将注明异常。

你还应了解你的组织的备份和还原计划以及上次备份中的信息，例如此文档中的工作表中的信息（有关详细信息，请参阅[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)），在开始还原之前可用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

