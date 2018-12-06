---
title: Merge-CsLegacyTopology
TOCTitle: Merge-CsLegacyTopology
ms:assetid: 396d6c84-7b38-41ae-9273-665f76cdd9ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425870(v=OCS.15)
ms:contentKeyID: 49312548
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Merge-CsLegacyTopology

 

_**上一次修改主题：** 2015-03-09_

The **Merge-CsLegacyTopology** cmdlet enables you to migrate topology information from Microsoft Office Communications Server 2007 R2 or Microsoft Office Communications Server 2007 to Lync Server. This helps provide interoperability between Lync Server and earlier versions of the software. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Merge-CsLegacyTopology -TopologyXmlFileName <String> <COMMON PARAMETERS>

    Merge-CsLegacyTopology -Reserved <PSObject> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Report <String>] [-UserInputFileName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 merges topology information and trusted service entries from Communications Server 2007 R2 or Communications Server 2007 with a new installation of Lync Server. The required parameter TopologyXmlFileName is used to indicate the path to the output file generated when you run the **Merge-CsLegacyTopology** cmdlet.

    Merge-CsLegacyTopology -TopologyXmlFileName C:\New_Topology.xml

## EXAMPLE 2

Example 2 is a variation of the command used in Example 1. In Example 2, however, the UserInputFileName parameter is included in order to merge Edge Server information into the topology. The parameter value C:\\EdgeServers.xml points to a custom XML file containing Edge Server information for Office Communications Server.

    Merge-CsLegacyTopology -TopologyXmlFileName C:\New_Topology.xml -UserInputFileName C:\EdgeServers.xml

## Detailed Description

The **Merge-CsLegacyTopology** cmdlet is the first tool to use when migrating from an earlier version of Office Communications Server (either Office Communications Server 2007 R2 or Office Communications Server 2007) to Lync Server. The **Merge-CsLegacyTopology** cmdlet is used to migrate trusted service entries and topology information for the following components: domains, user services, Registrar, 中介服务器, and 边缘服务器. In addition, the cmdlet migrates trusted service entries for the 会议助理应用程序; Communicator Web Access; and conferencing directories. (A trusted service entry is an Active Directory record that represents a server trusted by Lync Server.) Merging the topology information enables users homed on Lync Server to communicate with users homed on Communications Server 2007 or Communications Server 2007 R2.

Before you can run the **Merge-CsLegacyTopology** cmdlet you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package; this application is installed by running OCSWMIBC.msi. (OCSWMIBC.msi can be found on the installation DVD in the Setup.) After installing the Compatibility interfaces package, the **Merge-CsLegacyTopology** cmdlet can then be called. The **Merge-CsLegacyTopology** cmdlet will use WMI to read legacy data from the earlier version of Office Communications Server; it will then take the retrieved data and create corresponding objects in Lync Server. For example, for each SIP domain found in your installation of Office Communications Server, a corresponding SIP domain will be created in your new installation of Lync Server.

After running the **Merge-CsLegacyTopology** cmdlet, you should then run the **Import-CsLegacyConfiguration** cmdlet and the **Import-CsLegacyConferenceDirectory** cmdlet.

The **Merge-CsLegacyTopology** cmdlet needs to be run at least twice: once at the start of a migration (in order to introduce the Communications Server 2007 or Communications Server 2007 R2 topology), and once at the end of migration, when the previous Office Communications Server environment has been decommissioned. You will also need to run the cmdlet any time you make a change to your legacy Office Communications Server environment. For example, if you add a 中介服务器 to or decommission a pool from your Office Communications Server topology, you will need to re-run the **Merge-CsLegacyTopology** cmdlet in order to import the modified topology.

The **Import-CsLegacyConfiguration** cmdlet and the **Import-CsLegacyConferenceDirectory** cmdlet depend on values configured by the **Merge-CsLegacyTopology** cmdlet. That means that you might receive error messages from either the **Import-CsLegacyConfiguration** cmdlet or the **Import-CsLegacyConferenceDirectory** cmdlet that instruct you to run the **Merge-CsLegacyTopology** cmdlet as a possible solution to the problem that just occurred. If you do not re-run the **Merge-CsLegacyTopology** cmdlet, then additional errors can occur, especially if an item is removed from the Office Communications Server environment while it is still in use by Lync Server.

If you need to merge Edge Servers from a previous installation of Office Communications Server you must first create a custom XML file that contains your Edge Server; you must create the file yourself because Edge Server settings are not stored in Active Directory, and, as a result, cannot be retrieved by the **Merge-CsLegacyTopology** cmdlet. After you have created this XML file (see the Lync Server Deployment Guide for information on how to create this file) you must include the path to that file and the UserInputFileName parameter when running the **Merge-CsLegacyTopology** cmdlet. If you do not do this no Edge Servers will be included in your merged topology.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Merge-CsLegacyTopology** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Merge-CsLegacyTopology"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Reserved</em></p></td>
<td><p>Required</p></td>
<td><p>PS topology object</p></td>
<td><p>Enables you to merge the topology using a topology object instead of a topology XML file.</p></td>
</tr>
<tr class="even">
<td><p><em>TopologyXmlFileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Path to the output file to be created when the <strong>Merge-CsLegacyTopology</strong> cmdlet is run. Note that this file differs from the file specified using the Report parameter; the latter file is used for recording error information while the Topology XML file contains your newly created Lync Server topology. This file will later be used to publish the new topology.</p>
<p>If the specified file already exists, it will be overwritten when you run the <strong>Merge-CsLegacyTopology</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\MergeTopology.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>UserInputFileName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Path to the XML file used to import 边缘服务器 data from an earlier version of Office Communications Server. This XML file (which you must create following the guidelines detailed in the Lync Server Deployment Guide) is required because 边缘服务器 settings are not stored in Active Directory 域服务. If you do not need to import 边缘服务器 information, then this parameter can be omitted.</p>
<p>If this parameter is not used, remote and external access features (including federation) might not function as expected in an environment running both Communications Server 2007 R2 or Communications Server 2007 R2 and Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Merge-CsLegacyTopology** cmdlet does not accept pipelined input.

## Return Types

The **Merge-CsLegacyTopology** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Import-CsLegacyConfiguration](import-cslegacyconfiguration.md)  
[Import-CsLegacyConferenceDirectory](import-cslegacyconferencedirectory.md)  
[Move-CsLegacyUser](move-cslegacyuser.md)

