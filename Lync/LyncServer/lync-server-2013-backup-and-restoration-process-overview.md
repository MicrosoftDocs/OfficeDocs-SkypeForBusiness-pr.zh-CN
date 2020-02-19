---
title: Lync Server 2013：备份和还原过程概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 249e60cfaaadcc0bb615d3388ef6dce818c79966
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Lync Server 2013 的备份和还原过程概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-26_

本节提供了有关 Lync Server 2013 备份和还原过程的工作原理的概述。 所有 Standard Edition 服务器和 Enterprise Edition 服务器都使用相同的过程，而不考虑其位置。

通常情况下，备份过程的工作方式如下所示：

  - 您将备份位置创建为独立计算机上的共享文件夹，该文件夹不是任何池的一部分。 备份的位置在 **$Backup**中引用。

  - 在定期计划的基础上，您可以备份 lync server 2013 中的[备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)中描述的所有 lync server 数据库和所有文件存储区：数据按照[备份 lync server 2013](lync-server-2013-backing-up-lync-server.md)中所述的过程操作中央管理存储包括所有服务器设置和配置。

  - 每次运行后续备份时，都会创建一个新的共享文件夹，并更改 **$Backup**引用的路径。

通常情况下，还原过程的工作方式如下所示：

  - 当发生故障或中断时，您将 **$Backup**引用的位置中的数据还原到新的或清理的计算机。
    
    <div>
    

    > [!IMPORTANT]  
    > 此还原过程不会将数据还原到现有的服务器状态。 也就是说，此过程要求服务器是干净的或新的。

    
    </div>

  - 若要使您的用户和会议信息能够恢复到故障点，您可以实施具有配对前端池的灾难恢复拓扑，如在[Lync Server 2013 中规划高可用性和灾难恢复中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。

  - 所有域名系统（DNS）配置、动态主机配置协议（DHCP）配置、域名、计算机完全限定域名（Fqdn）、文件存储路径等在还原时必须相同，因为它们的还原时间在退后。

如果运行 Lync Server 的服务器出现故障，恢复过程将包括以下步骤：

  - 在具有故障计算机的 FQDN 相同的新计算机或干净计算机上安装操作系统。

  - 重新安装证书。

  - 如果服务器托管数据库，则安装 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。

  - 通常情况下，如果服务器托管数据库，则运行拓扑生成器以创建和安装数据库并设置访问控制列表（Acl）。

  - 通常情况下，如果服务器托管服务器角色，请运行 Lync Server 部署向导的步骤1到步骤4以安装本地配置文件，安装服务器角色组件，分配证书，并启动服务。
    
    <div>
    

    > [!NOTE]  
    > 如果服务器托管了与服务器角色并置的数据库，运行 Lync Server 部署向导的步骤2将重新创建数据库。

    
    </div>

  - 如果服务器托管数据库，请还原备份的数据。

</div>

<span> </span>

</div>

</div>

</div>

