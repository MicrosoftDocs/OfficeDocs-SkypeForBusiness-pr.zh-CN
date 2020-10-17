---
title: Lync Server 2013：备份和还原工作表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161a8577558705c773974b1cc733337b29b6dbd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532619"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 的备份和还原工作表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-18_

您的组织的备份和还原计划应包含有关如何以及何时备份数据和设置的详细信息。 您可以使用此处介绍的工作表来帮助您为特定部署记录此信息，并为您的组织的备份和还原要求提供此信息。

使用以下工作表记录备份和还原 Lync Server 池或 Standard Edition server 的数据库、文件存储和设置信息所需的信息。 将这些工作表的一个或多个副本保留在一个安全的位置，以便在需要还原 Lync Server 时可随时访问它们。

<div>


> [!NOTE]  
> 本节中的工作表仅包含还原 Lync Server 数据库和服务器的数据和设置所需的信息。 如果需要记录其他还原信息（如用于重新安装操作系统和其他软件的信息），请使用贵组织的部署计划和备份和还原计划来满足这些要求。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>数据库备份和还原工作表

使用下表记录备份和还原 Lync Server 数据库时所需的信息。

### <a name="database-information-for-backup-and-restoration"></a>备份和还原的数据库信息

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>数据库</th>
<th> (FQDN) 的服务器名称</th>
<th>备份计划</th>
<th>数据库备份工具</th>
<th>备份集</th>
<th>备份目标</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用于用户数据的后端服务器上的 Rtc 数据库</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-csuserdata</strong> cmdlet</p></td>
<td><p>别名</p>
<p>时间</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>存档数据库服务器上的 LcsLog (默认名称) 数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>别名</p>
<p>时间</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>监视数据库服务器上的 LcsCdr 数据库中的呼叫详细信息记录 (Cdr) </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>别名</p>
<p>时间</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>监控数据库服务器上的 QoEMetrics 数据库的体验质量 (QoE) 数据</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>别名</p>
<p>时间</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>持久聊天数据库</p></td>
<td></td>
<td></td>
<td><p>SQL Server 管理工具或 <strong>export-cspersistentchatdata</strong> cmdlet</p></td>
<td><p>别名</p>
<p>时间</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


不需要对以下数据库进行备份或还原：

  - Rtcdyn. 此数据库中的临时用户数据不是还原服务所必需的。

  - Rtcab. 通讯簿数据库将自动从 Active Directory 域服务中 (GAL) 的全局地址列表中重新创建。

  - Rgsdyn. 此数据库中的临时响应组服务数据不是还原服务所必需的。

  - Cpsdyn. 用于呼叫寄存应用程序的动态信息不是还原服务所必需的。

  - MgcComp. 用于持久聊天的合规性数据库不是还原服务所必需的。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>文件存储备份和还原工作表

使用下表记录备份和还原文件存储区所需的信息。 文件存储区包含会议内容元数据、会议合规性日志、设备更新的更新日志以及响应组、呼叫寄存和通知应用程序的音频文件等数据。

### <a name="file-store-information-for-backup-and-restoration"></a>用于备份和还原的文件存储信息

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>内容</th>
<th> (FQDN) 的服务器名称</th>
<th>备份计划</th>
<th>文件系统备份工具</th>
<th>要备份的文件共享 *</th>
<th>备份目标</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 文件存储</p></td>
<td></td>
<td></td>
<td><p>标准备份工具，如 Robocopy</p></td>
<td><p>在文件服务器上的 Enterprise Edition。 默认情况下为 Standard edition （针对 Standard Edition 部署）。 通常，每个站点一个。</p></td>
<td></td>
<td><p>名为 <strong>Meeting.Active</strong> 的文件不应进行备份。 这些文件正在使用，并在会议发生时被锁定。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>设置备份和还原工作表

使用下表可记录备份和还原设置所需的信息。

### <a name="settings-information-for-backup-and-restoration"></a>备份和还原的设置信息

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>数据库</th>
<th> (FQDN) 的服务器名称</th>
<th>备份计划</th>
<th>备份工具</th>
<th>配置文件 ( .xml) 名称</th>
<th>备份位置</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用于拓扑配置 (全局) 的中央管理存储中的 Xds 数据库</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>CsConfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9 的中央管理存储中的 .lis 数据库-1-1 位置信息 (全局) </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>CsLisConfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p> (池) 的后端服务器上的 RgsConfig 数据库的响应组配置</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>CsRgsConfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

