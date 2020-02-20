---
title: 删除前端池的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65c192bbc800c7b122911950e59439c43d8b0480
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>删除前端池的 SQL Server 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

删除 Microsoft Lync Server 2010 前端池或将池重新配置为使用其他数据库之后，可以删除托管池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1.  在 Lync Server 2013 前端服务器中，打开拓扑生成器并下载现有拓扑。

2.  在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的前端池关联的 SQL Server 实例，然后单击 "**删除**"。

3.  发布拓扑，然后检查复制状态。

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>从 SQL Server 中删除用户和应用程序数据库

1.  若要删除 SQL Server 上的数据库，您必须是要从中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。

2.  打开 Lync Server 命令行管理程序

3.  若要删除池用户存储的数据库，请键入：
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是数据库服务器的完全限定域名（FQDN）， \<实例\>是命名的数据库实例（如果定义了一个实例）。

4.  若要删除池应用程序存储的数据库，请键入：
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<fqdn\>是数据库服务器的 fqdn， \<实例\>是命名的数据库实例（如果定义了一个实例）。

5.  当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 **Y**（或按 Enter 键）继续，或者如果您想要停止该 cmdlet（也就是，在出现错误的情况下），请按 **N**，然后按 Enter 键。

</div>

</div>

<span> </span>

</div>

</div>

</div>

