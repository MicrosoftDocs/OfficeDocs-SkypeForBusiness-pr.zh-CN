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
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Lync Server 2013 的备份和还原过程概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-26_

本节概述了 Lync Server 2013 的备份和还原过程的工作原理。 无论其位置如何，都可以对所有标准版服务器和企业版服务器使用相同的过程。

通常，备份过程的工作原理如下所示：

  - 在不属于任何池的独立计算机上创建作为共享文件夹的备份位置。 备份的位置在 **$Backup**中引用。

  - 在定期、计划的基础上，你备份 lync server 数据库和[Lync server 2013 中的备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)中描述的所有文件存储：按照[备份 lync server 2013](lync-server-2013-backing-up-lync-server.md)中所述的过程，数据集中管理存储包括所有服务器设置和配置。

  - 每次运行后续备份时，都将创建一个新的共享文件夹，并更改 **$Backup**引用的路径。

通常，还原过程的工作原理如下所示：

  - 当发生故障或中断时，请将 **$Backup**引用的位置中的数据还原到新计算机或全新计算机。
    
    <div>
    

    > [!IMPORTANT]  
    > 此还原过程不会将数据还原到现有服务器状态。 也就是说，此过程要求服务器干净或全新。

    
    </div>

  - 若要使你的用户和会议信息能够恢复到故障点，你可以使用配对的前端池实施灾难恢复拓扑，如在[Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。

  - 所有域名系统（DNS）配置、动态主机配置协议（DHCP）配置、域名、计算机完全限定的域名（Fqdn）、文件存储路径等在还原时的还原时间必须相同。退后。

如果运行 Lync Server 的服务器失败，则恢复包括以下步骤：

  - 使用与故障计算机相同的 FQDN 在新计算机或全新计算机上安装操作系统。

  - 重新安装证书。

  - 如果服务器托管数据库，请安装 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。

  - 通常情况下，如果服务器托管数据库，请运行拓扑生成器来创建和安装数据库并设置访问控制列表（Acl）。

  - 一般情况下，如果服务器托管了服务器角色，请运行 "Lync Server 部署向导" 的步骤1到步骤4以安装本地配置文件、安装服务器角色组件、分配证书和启动服务。
    
    <div>
    

    > [!NOTE]  
    > 如果服务器托管与服务器角色 collocated 的数据库，运行 Lync Server 部署向导的步骤2将重新创建数据库。

    
    </div>

  - 如果服务器托管数据库，请还原备份的数据。

</div>

<span> </span>

</div>

</div>

</div>

