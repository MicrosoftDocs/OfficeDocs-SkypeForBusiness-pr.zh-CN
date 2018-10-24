---
title: Get-CsAdServerSchema
TOCTitle: Get-CsAdServerSchema
ms:assetid: fba777e5-886c-4914-a492-f2237721c57c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413070(v=OCS.15)
ms:contentKeyID: 49314828
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAdServerSchema

 

_**上一次修改主题：** 2015-03-09_

Returns information indicating whether your Active Directory schema has been correctly configured to allow for the installation of Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAdServerSchema [-Report <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns the current state of the Active Directory server schema. If the schema is up to date, the command returns the following value: SCHEMA\_VERSION\_STATE\_CURRENT.

    Get-CsAdServerSchema

## EXAMPLE 2

Example 2 also returns the current state of the Active Directory server schema. In addition, the command writes more detailed information about that schema to a file named C:\\Logs\\Server\_Schema.html. This information includes details such as the schema major version and minor version.

    Get-CsAdServerSchema -Report C:\Logs\Server_Schema.html

## Detailed Description

Lync Server cannot be installed until your Active Directory schema has been properly extended; that means that objects and attributes specific to Lync Server must be added to Active Directory 域服务 before installation can take place. For example, user account objects must be modified to allow for attributes that do such things as indicate the voice policy assigned to a user or report whether or not that account has been enabled for Enterprise Voice.

The **Get-CsAdServerSchema** cmdlet returns a single value that tells you whether or not Active Directory has been extended and is prepared for the installation of Lync Server. If the **Get-CsAdServerSchema** cmdlet returns the value SCHEMA\_VERSION\_STATE\_CURRENT, the schema has been extended. If the cmdlet returns any other value, then the schema has not been extended.

The **Get-CsAdServerSchema** cmdlet typically runs as part of the Setup Wizard; if Setup determines that the schema is not correctly prepared, you will receive an error message and Setup will stop. However, you can also run the **Get-CsAdServerSchema** cmdlet independently of the Setup Wizard, giving you the opportunity to verify the schema status before you try to install Lync Server.

The **Get-CsAdServerSchema** cmdlet performs the same function as the following Microsoft Office Communications Server 2007 R2 command: Lcscmd.exe /domain /action:CheckSchemaPrepState.

Who can run this cmdlet: By default, any user who has read permissions to Active Directory can run the **Get-CsAdServerSchema** cmdlet locally. Typically all domain members have this permission.

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
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\SchemaPrep.html&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsAdServerSchema** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsAdServerSchema** cmdlet returns instances of the Microsoft.Rtc.Management.Deployment.SchemaVersionState object.

## 另请参阅

#### 其他资源

[Install-CsAdServerSchema](install-csadserverschema.md)

