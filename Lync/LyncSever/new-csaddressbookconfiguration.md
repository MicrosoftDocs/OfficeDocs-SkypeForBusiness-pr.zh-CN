﻿---
title: New-CsAddressBookConfiguration
TOCTitle: New-CsAddressBookConfiguration
ms:assetid: 5a92a2b0-c46e-44e3-b07c-fc9ff0d33b2b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398395(v=OCS.15)
ms:contentKeyID: 49312950
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAddressBookConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of Address Book configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsAddressBookConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableFileGeneration <$true | $false>] [-EnablePhotoSearch <$true | $false>] [-Force <SwitchParameter>] [-IgnoreGenericRules <$true | $false>] [-InMemory <SwitchParameter>] [-KeepDuration <UInt32>] [-MaxDeltaFileSizePercentage <UInt32>] [-MaxFileShareThreadCount <Int32>] [-RunTimeOfDay <DateTime>] [-SynchronizePollingInterval <TimeSpan>] [-UseNormalizationRules <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new collection of Address Book configuration settings with the identity site:Redmond. To create the new collection you must call the **New-CsAddressBookConfiguration** cmdlet along with the Identity parameter and any other optional parameters (for example, the KeepDuration and SynchronizePollingInterval parameters).

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

## EXAMPLE 2

Example 2 creates a new collection of Address Book settings for the Paris site; this new collection uses two values (KeepDuration and SynchronizePollingInterval) copied from the Address Book settings configured for the Redmond suite. To carry out this task, the first command uses the **Get-CsAddressBookConfiguration** cmdlet to return a collection of all the Address Book settings configured for the Redmond site; this information is stored in a variable named $x.

The second command then uses the **New-CsAddressBookConfiguration** cmdlet to create Address Book settings for the Pairs site. This command includes two optional parameters -- KeepDuration and SynchronizePollingInterval -- that include the values copied from site:Redmond. For example, KeepDuration uses the parameter value $x.KeepDuration; that parameter value represents the KeepDuration information copied from the Redmond site.

    $x = Get-CsAddressBookConfiguration -Identity site:Redmond
    New-CsAddressBookConfiguration -Identity site:Paris -KeepDuration $x.KeepDuration -SynchronizePollingInterval $x.SynchronizePollingInterval

## EXAMPLE 3

Example 3 shows how you can use the InMemory parameter to create an in-memory-only instance of an Address Book settings collection, modify those settings in memory, then use the **Set-CsAddressBookConfiguration** cmdlet to create an actual collection with the Identity site:Redmond. To accomplish all that, the first command creates a new in-memory-only instance of an Address Book settings configuration, storing that instance in a variable named $x. The InMemory parameter ensures these Address Book settings will exist only in memory; if you end your Lync Server session or delete the variable $x, the settings will disappear and will not be applied to the Redmond site.

In commands 2 and 3, two properties of these virtual Address Book settings are modified: command 2 sets the value of the KeepDuration property to 15 days and command 3 sets the SynchronizePollingInterval to 10 minutes (00:10:00). The fourth and final command then uses the **Set-CsAddressBookConfiguration** cmdlet and the Instance parameter to transform the virtual Address Book settings into an actual collection of setting configured at the Redmond site.

    $x = New-CsAddressBookConfiguration -Identity site:Redmond -InMemory
    $x.KeepDuration = 15
    $x.SynchronizePollingInterval = "00:10:00"
    Set-CsAddressBookConfiguration -Instance $x

## Detailed Description

Address Book servers are intermediaries between AD DS and Lync Server. The Address Book server ensures that the user information stored in Lync Server is in synch with the user information stored in AD DS. This is done by periodically synching Address Book files with information stored in the 用户数据库.

In addition, Address Book servers periodically generate index files that are downloaded to computers running Lync. When a user searches for contacts, he or she either search through these index files or search the Address Book index files stored in the 中央管理存储.

Address Book servers are governed using Address Book configuration settings; these settings determine such things as how often Address Book files are synchronized with the user database and how often these Address Book index files are generated. When you install Lync Server, a set of global Address Book settings is created for you. You can also create custom configuration settings that can be applied to individual sites. These settings, if they exist, apply to any Address Book servers operating in the site, and take precedence over the global settings.

Site-level settings are created by using the **New-CsAddressBookConfiguration** cmdlet. You can only create settings at the site scope; if you try to create new settings anywhere else, including the global scope, your command will fail. Your command will also fail if the site in question already contains a collection of Address Book settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAddressBookConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsAddressBookConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier to be assigned to the new collection of Address Book settings. Because you can only create new collections at the site scope, the Identity will always be the prefix &quot;site:&quot; followed by the site name; for example &quot;site:Redmond&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableFileGeneration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) the Address Book server generates Address Book index files that can be downloaded by clients. When set to False, these index files are not generated. That means that client applications will have to use the 通讯簿 Web 查询服务 when searching for contacts.</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePhotoSearch</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, user photos will be displayed in search results.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreGenericRules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the Address Book server ignores the generic normalization rules used when parsing phone numbers. Generic rules are the rules that are built into Lync Server. These rules cannot be changed; however, by setting the value of this property to True you can instruct your Address Book servers to ignore these rules and instead use custom rules that you create yourself. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>KeepDuration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the amount of time (in days) that Address Book servers will keep change files. Change files older than the value of the KeepDuration property will be deleted. The KeepDuration can be set to any integer value between 1 and 90, inclusive. The default value is 30 days.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxDeltaFileSizePercentage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>When changes are made to Active Directory (such as a new user being enabled for Lync Server) the Address Book server typically records these changes in a &quot;delta file,&quot; a file consisting only of the updated information; Lync can then download the delta files rather than a complete Address Book file. The MaxDeltaFileSizePercentage property determines how large the delta files can get before they are incorporated into the complete Address Book file. By default, delta files can be as large as 20 percent of the complete Address Book file before a new Address Book file is generated. At that point, Lync clients will download the complete file rather than a delta file.</p>
<p>MaxDeltaFileSizePercentage must be entered as a percentage value, from 1 to 100, inclusive.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxFileShareThreadCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Specifies the maximum number of system resources that can be used by the Address Book server if there are problems accessing the service file share. The default value is 300.</p></td>
</tr>
<tr class="odd">
<td><p><em>RunTimeOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Indicates the time of day when the servers generate new Address Book files. The RunTimeOfDay property is based on a 24-hour clock (hours:minutes:seconds), with 00:00:00 representing midnight and 23:59:00 representing 11:59 P.M..</p>
<p>The default value is 01:30:00 (1:30 A.M.).</p></td>
</tr>
<tr class="even">
<td><p><em>SynchronizePollingInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Indicates how often Address Book servers synchronize their information with the information stored in the 用户数据库. The SynchronizePollingInterval can be set to any value between 5 seconds (00:00:05) and 3 hours (03:00:00). The default value is 5 minutes (00:05:00).</p></td>
</tr>
<tr class="odd">
<td><p><em>UseNormalizationRules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether Address Book servers should use phone normalization rules when retrieving phone numbers. If set to False, phone numbers will be retrieved as-is, and it will be up to the client application to apply normalization rules when displaying these numbers.</p>
<p>The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsAddressBookConfiguration** cmdlet does not accept pipelined input.

## Return Types

Creates instances of the Microsoft.Rtc.Management.WritableConfig.Settings.AddressBook.AddressBookSettings object.

## 另请参阅

#### 其他资源

[Get-CsAddressBookConfiguration](get-csaddressbookconfiguration.md)  
[Remove-CsAddressBookConfiguration](remove-csaddressbookconfiguration.md)  
[Set-CsAddressBookConfiguration](set-csaddressbookconfiguration.md)

