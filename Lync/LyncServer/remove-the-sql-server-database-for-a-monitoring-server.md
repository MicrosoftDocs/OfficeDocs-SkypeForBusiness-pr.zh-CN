---
title: 删除监控服务器的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f175f17b41a72c63aba77e6eb59aadce985ced82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>删除监控服务器的 SQL Server 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

删除 Microsoft Lync Server 2010 监视服务器后，可以删除托管服务器数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1.  在 Lync Server 2013 前端服务器上，打开拓扑生成器。

2.  在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的监视服务器相关联的 SQL Server 实例，然后单击 "**删除**"。

3.  发布拓扑，然后检查复制状态。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>从 SQL Server 中删除数据库文件

1.  要删除基于 SQL Server 的服务器上的数据库，您必须是从其中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmin 组成员。

2.  打开 Lync Server 命令行管理程序。

3.  在命令行中键入：
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是数据库服务器的完全限定的域名（FQDN）， \<实例\>是可选的命名数据库实例。

4.  当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 **Y**（或按 Enter 键）继续，或者如果您想要停止该 cmdlet（也就是，在出现错误的情况下），请按 **N**，然后按 Enter 键。

</div>

</div>

<span> </span>

</div>

</div>

</div>

