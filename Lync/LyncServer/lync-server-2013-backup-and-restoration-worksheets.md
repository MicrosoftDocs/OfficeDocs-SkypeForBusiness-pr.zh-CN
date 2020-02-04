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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 的备份和还原工作表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-18_

您的组织的备份和还原计划应包含有关备份数据和设置的方式和时间的详细信息。 你可以使用此处介绍的工作表来帮助你为特定部署以及你的组织的备份和还原要求记录此信息。

使用以下工作表记录用于备份和还原 Lync Server 池或标准版服务器的数据库、文件存储和设置信息所需的信息。 将这些工作表的一个或多个副本保留在一个安全位置，以便在需要还原 Lync 服务器时可以随时访问它们。

<div>


> [!NOTE]  
> 本部分中的工作表仅涵盖还原 Lync Server 数据库和服务器的数据和设置所需的信息。 如果需要记录其他还原信息，例如用于重新安装操作系统和其他软件的信息，请使用组织的部署计划和备份和还原计划来满足这些要求。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>数据库备份和还原工作表

使用下表记录备份和还原 Lync Server 数据库所需的信息。

### <a name="database-information-for-backup-and-restoration"></a>用于备份和还原的数据库信息

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
<th>服务器名称（FQDN）</th>
<th>备份计划</th>
<th>数据库备份工具</th>
<th>备份集</th>
<th>备份目标</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用户数据的后端服务器上的 Rtc 数据库</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> cmdlet</p></td>
<td><p>姓</p>
<p>满</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>存档数据库服务器上的 LcsLog （默认名称）数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>姓</p>
<p>满</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>用于针对通话详细记录（CDRs）监控数据库服务器的 LcsCdr 数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>姓</p>
<p>满</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>用于监视数据库服务器上的 QoEMetrics 数据库的体验质量（QoE）数据</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>姓</p>
<p>满</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>持久聊天数据库</p></td>
<td></td>
<td></td>
<td><p>SQL Server 管理工具或<strong>Export-CsPersistentChatData</strong> cmdlet</p></td>
<td><p>姓</p>
<p>满</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


不需要以下数据库的备份或还原：

  - Rtcdyn. 还原服务不需要此数据库中的瞬时用户数据。

  - Rtcab. 通讯簿数据库将从 Active Directory 域服务中的全局地址列表（GAL）自动重新创建。

  - Rgsdyn. 还原服务不需要此数据库中的暂时性响应组服务数据。

  - Cpsdyn. 还原服务不需要调用寄存应用程序的动态信息。

  - MgcComp. 用于持久聊天的合规性数据库不是还原服务所必需的。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>文件存储备份和还原工作表

使用下表记录备份和还原文件存储所需的信息。 文件存储包含会议内容元数据、会议合规性日志、更新设备更新日志以及响应组的音频文件、呼叫寄存和发布应用程序等数据。

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
<th>服务器名称（FQDN）</th>
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
<td><p>在 "适用于企业版的文件服务器" 上。 对于标准版，默认情况下为标准版部署。 通常，每个站点一个。</p></td>
<td></td>
<td><p>名为 "<strong>会议" 的</strong>文件不应备份。 这些文件正在使用中，并且在会议发生时被锁定。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>设置备份和还原工作表

使用下表记录备份和还原设置所需的信息。

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
<th>服务器名称（FQDN）</th>
<th>备份计划</th>
<th>备份工具</th>
<th>配置文件（.xml）名称</th>
<th>备份位置</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓扑配置的中央管理存储中的 Xds 数据库（全局）</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9 的中央管理存储中的 .lis 数据库-1-1-1 位置信息（全局）</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>响应组配置的后端服务器上的 RgsConfig 数据库（池）</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> cmdlet</p></td>
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

