---
title: Update-CsAddressBook
TOCTitle: Update-CsAddressBook
ms:assetid: 109c5fe7-0154-4161-b19f-01bab024bb3d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398194(v=OCS.15)
ms:contentKeyID: 49312030
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Update-CsAddressBook

 

_**上一次修改主题：** 2015-03-09_

Forces the specified Address Book servers to synchronize their contents with the 用户数据库. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Update-CsAddressBook [-Force <SwitchParameter>] [-Fqdn <Fqdn>]

## Examples

## EXAMPLE 1

In Example 1, the **Update-CsAddressBook** cmdlet is called without any parameters. This synchronizes all the Address Book servers in the organization.

    Update-CsAddressBook

## EXAMPLE 2

In Example 2, only a single Address Book server is synchronized: the server with the FQDN atl-abs-001.litwareinc.com.

    Update-CsAddressBook -Fqdn atl-abs-001.litwareinc.com

## Detailed Description

Address Book servers are intermediaries between Active Directory and Lync Server. The Address Book server ensures that the user information stored in Lync Server is in synch with the user information stored in Active Directory. This is done by periodically synching Address Book files with the information stored in the 用户数据库. By default, this synchronization takes place every five minutes. (However, that time interval can be modified by using the **Set-CsAddressBookConfiguration** cmdlet.)

If you can’t wait for synchronization to take place or if it appears that, for some reason, synchronization isn’t taking place, you can use the **Update-CsAddressBook** cmdlet to force an Address Book server to immediately synch with the user information stored in the 用户数据库.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Update-CsAddressBook** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Update-CsAddressBook"}

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
<td><p>Suppresses any confirmation prompts or non-fatal error messages that might occur when you run the cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Fqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to specify an individual Address Book to be updated. If this parameter is not included then all of your Address Book servers will be synchronized with the 用户数据库. Individual Address Book servers should be referenced by their fully qualified domain name (FQDN); for example, atl-abs-001.litwareinc.com.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Update-CsAddressBook** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Update-CsAddressBook** cmdlet updates existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.AddressBook.AddressBookSettings object.

## 另请参阅

#### 其他资源

[Get-CsAddressBookConfiguration](get-csaddressbookconfiguration.md)  
[Test-CsAddressBookService](test-csaddressbookservice.md)  
[Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)

