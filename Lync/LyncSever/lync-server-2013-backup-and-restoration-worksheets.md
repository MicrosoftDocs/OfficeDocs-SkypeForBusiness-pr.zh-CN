---
title: 备份和还原工作表
TOCTitle: 备份和还原工作表
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202169(v=OCS.15)
ms:contentKeyID: 52060989
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份和还原工作表

 

_**上一次修改主题：** 2015-03-09_

组织的备份和还原计划应包含有关如何以及何时备份数据和设置的详细信息。您可以使用此处提供的工作表帮助您记录此类信息，以便满足特定部署和组织的备份和还原要求。

以下工作表用于记录备份和还原 Lync Server 池或 Standard Edition Server 的数据库、文件存储和设置信息所需的信息。将这些工作表的一个或多个副本保留在安全的位置，以便您在需要还原 Lync Server 时可轻松访问它们。

> [!NOTE]  
> 本节的工作表仅包含还原 Lync Server 数据库和服务器的数据和设置所需的信息。如果需要记录其他还原信息（例如，重新安装操作系统和其他软件的信息），请使用组织的部署计划以及备份和还原计划来满足这些要求。



## 数据库备份和还原工作表

下表用于记录备份和还原 Lync Server 数据库所需的信息。

### 用于备份和还原的数据库信息

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
<th>服务器名称 (FQDN)</th>
<th>备份计划</th>
<th>数据库备份工具</th>
<th>备份集</th>
<th>备份目标</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>后端服务器上的用于用户数据的 Rtc 数据库</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> cmdlet</p></td>
<td><p>名称：</p>
<p>到期时间：</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>存档数据库服务器上的 LcsLog（默认名称）数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名称：</p>
<p>到期时间：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>监控数据库服务器上的用于呼叫详细信息记录 (CDR) 的 LcsCdr 数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名称：</p>
<p>到期时间：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>监控数据库服务器上的用于用户体验质量 (QoE) 数据的 QoEMetrics 数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名称：</p>
<p>到期时间：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>持久聊天数据库</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>SQL Server 管理工具或 <strong>Export-CsPersistentChatData</strong> cmdlet</p></td>
<td><p>名称：</p>
<p>到期时间：</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


无需对以下数据库备份或还原：

  - Rtcdyn。该数据库中的临时用户数据不是还原服务必需的数据。

  - Rtcab。该通讯簿数据库在 Active Directory 域服务 中根据全局地址列表 (GAL) 自动重新创建。

  - Rgsdyn。该数据库中的临时响应组服务数据不是还原服务必需的数据。

  - Cpsdyn。呼叫寄存应用程序的动态信息不是还原服务必需的信息。

  - MgcComp。持久聊天的合规性数据库不是还原服务必需的数据库。

## 文件存储备份和还原工作表

下表用于记录备份和还原文件存储所需的信息。文件存储包含会议内容元数据、会议合规性日志、设备更新日志以及响应组、呼叫寄存和通知应用程序的音频文件等数据。

### 用于备份和还原的文件存储信息

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
<th>服务器名称 (FQDN)</th>
<th>备份计划</th>
<th>文件系统备份工具</th>
<th>要备份的文件共享*</th>
<th>备份目标</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 文件存储</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>标准备份工具，例如 Robocopy</p></td>
<td><p>对于 Enterprise Edition，位于文件服务器上。对于 Standard Edition 部署，默认情况下，位于 Standard Edition 服务器上。通常每个站点使用一个文件存储位置。</p></td>
<td><p></p></td>
<td><p>名为 <strong>Meeting.Active</strong> 的文件不应进行备份。在召开会议时，会使用并锁定这些文件。</p></td>
</tr>
</tbody>
</table>


## 设置备份和还原工作表

下表用于记录备份和还原设置所需的信息。

### 用于备份和还原的设置信息

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
<th>服务器名称 (FQDN)</th>
<th>备份计划</th>
<th>备份工具</th>
<th>配置文件 (.xml) 名称</th>
<th>备份位置</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>中央管理存储中的用于拓扑配置（全局）的 Xds 数据库</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>中央管理存储中的用于 E9-1-1 位置信息（全局）的 Lis 数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> cmdlet</p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>后端服务器上的用于响应组配置（池）的 RgsConfig 数据库</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> cmdlet</p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>

