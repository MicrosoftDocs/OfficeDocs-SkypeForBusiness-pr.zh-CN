---
title: Update-CsUserDatabase
TOCTitle: Update-CsUserDatabase
ms:assetid: 86ed4291-70cc-4c41-ab2a-e5f7546a0f1f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398682(v=OCS.15)
ms:contentKeyID: 49313477
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Update-CsUserDatabase

 

_**上一次修改主题：** 2015-03-09_

Forces the back-end user database to clear its replication status with Active Directory. This causes the database to re-read all the user-related information stored in Active Directory 域服务. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Update-CsUserDatabase [-Force <SwitchParameter>] [-Fqdn <Fqdn>]

## Examples

## EXAMPLE 1

The command shown in Example 1 locates the user database for the pool where the local computer is located, then forces that database to connect to and return complete user information from Active Directory.

    Update-CsUserDatabase

## EXAMPLE 2

Example 2 shows how you can force a specific user database to re-read data from Active Directory. In this case, that’s the user database for the pool atl-cs-001.litwareinc.com.

    Update-CsUserDatabase -Fqdn atl-cs-001.litwareinc.com

## Detailed Description

The Lync Server user database holds detailed information about such things as contacts, groups, and access permissions. As such, the database is required to periodically synch its contents with the information stored in Active Directory.

More often than not, the automatic synch between the user database and Active Directory will keep the information in the user database up to date. However, it is possible that a problem might occur that prevents this automatic synchronization from taking place. In a case such as that, you can use the **Update-CsUserDatabase** cmdlet to force the user database to refresh its contents by re-reading all of the user information stored in Active Directory. You might also need to run this cmdlet if a product update ever includes a change to the user replicator service.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Update-CsUserDatabase** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Update-CsUserDatabase"}

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
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Fqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the computer hosting the user database. If this parameter is not specified then the <strong>Update-CsUserDatabase</strong> cmdlet will update the user database for the pool that the local computer belongs to.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Update-CsUserDatabase** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Update-CsUserDatabase** cmdlet updates instances of the Microsoft.Rtc.Management.Xds.DisplayuserDatabase object.

## 另请参阅

#### 其他资源

[Get-CsUserDatabaseState](get-csuserdatabasestate.md)  
[Set-CsUserDatabaseState](set-csuserdatabasestate.md)

