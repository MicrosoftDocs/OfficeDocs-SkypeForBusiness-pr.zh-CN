---
title: Set-CsManagementConnection
TOCTitle: Set-CsManagementConnection
ms:assetid: f7cf19ba-6c56-4f74-9757-843e1ca0c9a1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413045(v=OCS.15)
ms:contentKeyID: 49314783
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsManagementConnection

 

_**上一次修改主题：** 2015-03-09_

Modifies the management connection to the 中央管理存储. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsManagementConnection -Connection <String> -StoreProvider <FileSystem | Sql | Memory> [-Confirm [<SwitchParameter>]] [-EnableCaching <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 changes the management connection to the SQL Server instance rtcbackup found on the computer atl-sql-001.litwareinc.com.

    Set-CsManagementConnection -StoreProvider Sql -Connection "atl-sql-001.litwareinc.com\rtcbackup"

## EXAMPLE 2

In Example 2, the management connection is set to file system and, more specifically, to the folder C:\\TestTopology on the local computer.

    Set-CsManagementConnection -StoreProvider FileSystem -Connection "C:\TestTopology"

## Detailed Description

Configuration data for Lync Server is stored in the 中央管理存储. It is crucial that both Windows PowerShell and the management replica services be able to locate this database. When you install Lync Server, a service control point is created in Active Directory 域服务 that provides location information for this database. Typically, computers rely on this service control point in order to connect to the 中央管理存储. To see the details behind this connection (that is, if you want to know which computer the 中央管理存储 is running on, as well information about the SQL Server connection to that 中央管理存储) all you have to do is run the **Get-CsManagementConnection** cmdlet.

For the most part, after your management connection has been set you will not need to change it. However, in case of hardware or software failure, you might need to temporarily use a connection; for example, you can configure a computer to work from the local replica. The **Set-CsManagementConnection** cmdlet provides a way for you to provide a new location for the 中央管理存储.

Note that any changes you make to Lync Server while using a temporary management connection will not persist if and when you switch back to your original connection. (You can switch back by running the **Remove-CsManagementConnection** cmdlet.) For example, suppose you decide to temporarily use the file system as your store provider. You change the management connection, and then create several new voice policies (each of which will be instantiated as XML files). When you switch back to your original management connection, these new voice policies will disappear because they were never recorded in the 中央管理存储 now being used.

You should also keep in mind that any changes made by running this cmdlet only affect the local computer. You cannot use the **Set-CsManagementConnection** cmdlet to change the management connection on other computers.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsManagementConnection** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins.

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
<td><p><em>Connection</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Location information for the SQL Server instance or the file system folder being used as the management connection.</p>
<p>For example, if the new management connection is to a SQL Server instance named rtcbackup on the computer atl-sql-001.litwareinc.com then use this syntax: -Connection &quot;atl-sql-001.litwareinc.com\rtcbackup&quot;.</p>
<p>If you want to create a management connection to the folder C:\TestTopology then use this syntax: -Connection &quot;C:\TestTopology&quot;. If the folder does not exist, the <strong>Set-CsManagementConnection</strong> cmdlet will create it.</p></td>
</tr>
<tr class="even">
<td><p><em>StoreProvider</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Store.StoreProvider</p></td>
<td><p>Indicates the type of back-end store used for configuration information. To store configuration data in SQL Server, set the StoreProvider like this: -StoreProvider Sql. To store configuration data to the file system, use this syntax: -StoreProvider FileSystem. You should not modify the StoreProvider property unless instructed to do so by Microsoft support personnel.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableCaching</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), caching is enabled for the management connection.</p></td>
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

None. The **Set-CsManagementConnection** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsManagementConnection** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.Store.StoreProvider object.

## 另请参阅

#### 其他资源

[Get-CsManagementConnection](get-csmanagementconnection.md)  
[Remove-CsManagementConnection](remove-csmanagementconnection.md)  
[Set-CsConfigurationStoreLocation](set-csconfigurationstorelocation.md)

