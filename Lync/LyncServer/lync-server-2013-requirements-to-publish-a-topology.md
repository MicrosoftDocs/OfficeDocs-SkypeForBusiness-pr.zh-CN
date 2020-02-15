---
title: Lync Server 2013：发布拓扑的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7537d512bfdb8c004cfc05e142d908034f5b535e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布拓扑的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

本主题介绍了特定于发布拓扑的基础结构和软件要求，无论是使用拓扑生成器还是 Lync Server 2013 管理命令行接口。 这些要求是对适用于所有 Lync Server 2013 管理工具的常规操作系统、软件和权限要求的补充。 在发布拓扑之前，请确保满足所有管理工具的要求。

  - 您必须在已加入到您正在创建的 Lync Server 2013 部署的相同域或林的计算机上运行拓扑生成器，以便 Active Directory 域服务准备步骤已完成，从而使您能够使用上的管理工具要成功发布拓扑的计算机。

  - 拓扑中定义的计算机必须加入域（边缘服务器除外）并且位于 AD DS 中。但在发布拓扑时，计算机不需要处于联机状态。

  - 必须创建池的文件共享，且该文件共享必须对远程用户可用。

  - 为了发布 Enterprise Edition 前端池，基于 SQL Server 的后端服务器必须加入到您在其中部署服务器的域，并使用适当的防火墙规则进行配置，以使其可供远程用户使用。 有关指定防火墙例外的详细信息，请参阅[了解使用 Lync server 2013 的 SQL Server 的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)。 有关配置 SQL Server 的其他详细信息，请参阅[CONFIGURE SQL server For Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Standard Edition server 具有一个并置数据库，该数据库将接受已发布的配置。 必须先在 Lync Server 部署向导中运行 "<STRONG>准备第一个 Standard Edition server</STRONG>安装程序" 任务。

    
    </div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)  
[在 Lync Server 2013 中委派安装程序权限](lync-server-2013-delegate-setup-permissions.md)  


[Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)  


[安装和管理 Lync Server 2013 所需的管理员权利和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

