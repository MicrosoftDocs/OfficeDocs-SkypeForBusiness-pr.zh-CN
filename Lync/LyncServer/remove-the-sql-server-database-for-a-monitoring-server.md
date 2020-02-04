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
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>删除监控服务器的 SQL Server 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

删除 Microsoft Lync Server 2010 监视服务器之后，你可以删除托管了服务器数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓扑生成器删除 SQL Server 数据库

1.  在 Lync Server 2013 前端服务器上，打开拓扑生成器。

2.  在拓扑生成器中，导航到 "**共享组件**"，然后导航到 " **sql server 存储**"，右键单击与删除或重新配置的监视服务器相关联的 SQL server 实例，然后单击 "**删除**"。

3.  发布拓扑，然后检查复制状态。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>从 SQL Server 中删除数据库文件

1.  若要删除基于 SQL Server 的服务器上的数据库，您必须是要从中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmin 组的成员。

2.  打开 Lync Server 命令行管理程序。

3.  在命令行中键入：
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是数据库服务器的完全限定的域名（fqdn）， \<实例\>是可选的命名数据库实例。

4.  当**CsDataBase** cmdlet 提示你确认操作时，请阅读信息，然后按 " **Y** " （或按 enter）继续操作，或者按 N，然后按 N，然后按 N，然后按**N** ，然后按 enter 以停止 cmdlet （也就是万一出现错误）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

