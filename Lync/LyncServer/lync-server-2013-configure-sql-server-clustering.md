---
title: Lync Server 2013：配置 SQL Server 群集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>配置 Lync Server 2013 的 SQL Server 群集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-01-10_

Microsoft Lync Server 2013 支持 SQL Server 2012 和 SQL Server 2008 R2 的群集。 有关支持哪些内容的详细信息，请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。

在安装和部署企业版前端服务器和后端数据库之前，应设置和配置 SQL Server 群集。 有关 SQL Server 2012 中故障转移群集的最佳做法和设置说明， <http://technet.microsoft.com/en-us/library/hh231721.aspx>请参阅。 有关 SQL Server 2008 中的故障转移群集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>，请参阅。

安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。

<div>


> [!IMPORTANT]  
> 若要在基于 SQL Server 的服务器上安装和部署数据库，您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。 如果您不是 SQL Server sysadmin 组的成员，则需要请求将其添加到组中，直到部署数据库文件。 如果你不能成为 sysadmin 组的成员，你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些步骤所需的正确用户权限和权限的详细信息，请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>配置 SQL Server 群集

1.  完成 SQL Server 群集的安装和配置后，通过使用 SQL Server 实例虚拟群集名称（在 SQL Server 群集设置中配置）和实例，在拓扑结构生成器中定义 SQL Server 应用商店。SQL Server 数据库的名称。 不同于单个基于 SQL Server 的服务器，你将对基于 SQL Server 的群集服务器使用虚拟节点完全限定的域名（FQDN）。
    
    <div>
    

    > [!NOTE]  
    > 无需为拓扑生成器配置单独的 Windows Server 群集节点。 你将仅使用虚拟 SQL Server 群集名称。

    
    </div>

2.  如果使用拓扑生成器部署数据库，您必须是 SQL Server sysadmin 组的成员。 如果你是 SQL Server sysadmin 组的成员，但你在域（例如 SQL Server 数据库管理员角色）中没有权限，则你有权创建数据库，但无法在 Lync Server 中读取所需的信息。 有关部署 Lync Server 所需的用户权利和权限的详细信息，请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

3.  通过使用 SQL Server Management Studio，确保将数据库文件夹和日志文件文件夹默认值正确映射到 SQL Server 群集中的共享磁盘。 如果您将使用拓扑生成器创建数据库，则这是必需的过程。
    
    <div>
    

    > [!NOTE]  
    > 如果未安装 SQL Server Management Studio，则可以通过重新运行 SQL Server 安装来安装它，然后选择管理工具作为现有 SQL Server 部署的新增功能。

    
    </div>

4.  使用拓扑生成器或 Windows PowerShell cmdlet 为基于 SQL Server 的服务器安装数据库。 若要使用拓扑生成器，请使用以下过程。 若要使用 Windows PowerShell cmdlet，请参阅[在 Lync server 2013 中使用 Lync Server Management Shell 进行数据库安装](lync-server-2013-database-installation-using-lync-server-management-shell.md)。

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>使用拓扑生成器创建数据库

1.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
    <div>
    

    > [!WARNING]  
    > 以下过程假定你已在拓扑生成器中定义并配置了拓扑。 有关定义拓扑的详细信息，请参阅<A href="lync-server-2013-defining-and-configuring-the-topology.md">在 Lync Server 2013 中定义和配置拓扑</A>。 若要使用拓扑生成器发布拓扑和配置数据库，您必须以具有正确的用户权限和组成员身份的用户身份登录。 有关所需权限和组成员身份的详细信息，请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。

    
    </div>

2.  在拓扑生成器中，在发布拓扑时，在 "**创建数据库**" 页面上，单击 "**高级**"。

3.  "**选择数据库文件位置**" 页面具有两个选项，可确定如何将数据库文件部署到 SQL Server 群集。 选择下列选项之一：
    
      - **自动确定数据库文件位置。** 此选择使用一个算法根据基于 SQL Server 的服务器上的驱动器配置确定数据库日志和数据文件位置。 将以一种方式分发文件，以尝试提供最佳性能。
    
      - 使用 SQL Server 实例默认值。 选择此选项将根据 SQL Server 实例设置安装日志和数据文件。 在将数据库文件部署到 SQL Server 之后，你的 SQL Server 数据库管理员可能需要重新定位文件以优化特定 SQL Server 配置要求的性能。

4.  完成拓扑的发布，并确认操作期间没有出现任何错误。

</div>

</div>

<span> </span>

</div>

</div>

</div>

