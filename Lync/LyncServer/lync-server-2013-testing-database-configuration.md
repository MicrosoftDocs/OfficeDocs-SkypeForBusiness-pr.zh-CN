---
title: Lync Server 2013：测试数据库配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c1698d576188a8bd87f94e5c61060267bf0fab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中测试数据库配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>验证计划</p></td>
<td><p>每天</p></td>
</tr>
<tr class="even">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员，并且需要具有对 SQL Server 的管理员权限。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsDatabase</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**CsDatabase** cmdlet 验证与一个或多个 Lync Server 2013 数据库的连接。 在运行时， **CsDatabase** cmdlet 会读取 Lync Server 拓扑，尝试连接到相关数据库，然后报告每次尝试成功或失败。 如果可以建立连接，该 cmdlet 还将返回数据库名称、SQL Server 版本以及所有已安装的镜像数据库的位置等信息。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例 1 中显示的命令验证中央管理数据库的配置。

    Test-CsDatabase -CentralManagementDatabase

示例2验证安装在计算机 atl-sql-001.litwareinc.com 上的所有 Lync Server 数据库。

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

在示例 3 中，仅对安装在计算机 atl-sql-001.litwareinc.com 上的存档数据库执行验证。请注意，包括了 SqlInstanceName 参数以指定存档数据库所在的 SQL Server 实例 (Archinst)。

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

示例 4 中显示的命令用于验证本地计算机上安装的数据库。

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果数据库连接配置正确，您将收到与以下内容类似的输出，其中 "成功" 属性被标记为**True**：

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： xds

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

成功： True

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： .lis

DataSource

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

成功： True

如果数据库配置正确但仍可用，则 "成功" 字段将显示为**False**，并将提供其他警告和信息：

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： xds

DataSource

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

成功： False

SqlServerFqdn： atl-cs-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： .lis

DataSource

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

成功： False

警告： CsDatabase 遇到错误。 请参阅日志文件获取

详细分析，并确保解决所有错误（2）和警告（0）

，然后再继续。

警告：详细结果可在以下位置找到：

"C：\\用户\\测试\\AppData\\本地\\临时\\2\\测试-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6 "。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是**测试 CsDatabase**可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 如果数据库配置错误或尚未部署，则此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-csservice](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

