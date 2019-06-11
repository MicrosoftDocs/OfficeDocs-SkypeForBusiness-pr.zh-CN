---
title: 删除前端池的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>删除前端池的 SQL Server 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-04_

删除 Microsoft Lync Server 2010 前端池或将其重新配置为使用其他数据库后, 可以删除托管了池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1.  从 Lync Server 2013 前端服务器, 打开拓扑生成器并下载现有拓扑。

2.  在拓扑生成器中, 导航到 "**共享组件**", 然后导航到 " **sql server 存储**", 右键单击与删除或重新配置的前端池相关联的 SQL Server 实例, 然后单击 "**删除**"。

3.  发布拓扑, 然后检查复制状态。

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>从 SQL Server 中删除用户和应用程序数据库

1.  若要删除 SQL Server 上的数据库, 您必须是要删除数据库文件的 SQL Server 的 SQL Server sysadmin 组的成员。

2.  打开 Lync Server 命令行管理程序

3.  若要删除 "池用户" 存储的数据库, 请键入:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是数据库服务器的完全限定的域名 (fqdn), \<实例\>是指定的数据库实例 (即, 如果定义了一个实例)。

4.  若要删除池应用商店的数据库, 请键入:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<fqdn\>是数据库服务器的 fqdn, \<实例\>是指定的数据库实例 (即, 如果定义了一个实例)。

5.  当**CsDataBase** cmdlet 提示你确认操作时, 请阅读信息, 然后按 " **Y** " (或按 enter) 继续操作, 或者按 N, 然后按 N, 然后按 N, 然后按**N** , 然后按 enter 以停止 cmdlet (也就是万一出现错误)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

