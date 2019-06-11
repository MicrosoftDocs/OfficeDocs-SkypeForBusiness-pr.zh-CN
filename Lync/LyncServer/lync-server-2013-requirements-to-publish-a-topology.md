---
title: Lync Server 2013：发布拓扑的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e90604315732d9e9bfe4c45968ff0bcf5fbd2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布拓扑的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

本主题介绍了特定于发布拓扑的基础结构和软件要求, 无论是使用拓扑生成器还是 Lync Server 2013 管理外壳程序命令行界面。 除了适用于所有 Lync Server 2013 管理工具的常规操作系统、软件和权限要求外, 还提供了这些要求。 在发布拓扑之前, 请确保满足所有管理工具要求。

  - 必须在已加入到你正在创建的 Lync Server 2013 部署的相同域或林的计算机上运行拓扑生成器, 以便已完成 Active Directory 域服务准备步骤, 从而使你能够使用中的管理工具该计算机成功发布拓扑。

  - 拓扑中定义的计算机必须加入域 (边缘服务器除外) 和 AD DS 中。 但是, 当你发布拓扑时, 计算机无需联机。

  - 必须创建池的文件共享, 并将其提供给远程用户。

  - 为了发布企业版前端池, 基于 SQL Server 的后端服务器必须联接到您在其中部署服务器的域, 并使用相应的防火墙规则进行配置, 以使其可供远程用户使用。 有关指定防火墙例外的详细信息, 请参阅[了解适用于 Lync server 2013 的 SQL Server 的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)。 有关配置 SQL Server 的其他详细信息, 请参阅[配置 Lync server 2013 的 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)。
    
    <div>
    

    > [!NOTE]  
    > 标准版服务器具有一个 collocated 数据库, 该数据库将接受已发布的配置。 必须首先运行 Lync Server 部署向导中的 "<STRONG>准备第一个标准版服务器</STRONG>设置" 任务。

    
    </div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)  
[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)  


[Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)  


[Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

