﻿---
title: Set-CsAddressBookConfiguration
TOCTitle: Set-CsAddressBookConfiguration
ms:assetid: a700328b-c738-447a-a03c-319852b42240
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412784(v=OCS.15)
ms:contentKeyID: 49313846
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAddressBookConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of Address Book configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAddressBookConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsAddressBookConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableFileGeneration <$true | $false>] [-EnablePhotoSearch <$true | $false>] [-Force <SwitchParameter>] [-IgnoreGenericRules <$true | $false>] [-KeepDuration <UInt32>] [-MaxDeltaFileSizePercentage <UInt32>] [-MaxFileShareThreadCount <Int32>] [-RunTimeOfDay <DateTime>] [-SynchronizePollingInterval <TimeSpan>] [-UseNormalizationRules <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example sets the RunTimeOfDay property (the property that determines the time of day when Address Book synchronization takes place) to 23:00 (11:00 PM on a 24-hour clock). The Identity parameter is used to limit the change to the Address Book configuration settings with the identity site:Redmond.

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

## EXAMPLE 2

In Example 2, the RunTimeOfDay property is set to 11:00 PM (23:00) for all the Address Book setting collections configured at the site scope. To do this, the command first uses the **Get-CsAddressBookConfiguration** cmdlet and the Filter parameter to return a collection of all the site-specific settings; the filter value "site:\*" limits the returned data to collections configured at the site scope. This information is then piped to the **Set-CsAddressBookConfiguration** cmdlet, which modifies the value of the RunTimeOfDay property for each item in the collection.

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

## EXAMPLE 3

Example 3 modifies the KeepDuration property for any Address Book settings collections where KeepDuration is less than 30 days. To carry out this task, the **Get-CsAddressBookConfiguration** cmdlet is used, without any additional parameters, to return a collection of all the Address Book settings configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the KeepDuration property is less than 30 days. This filtered collection is then piped to the **Set-CsAddressBookConfiguration** cmdlet, which changes the value of the KeepDuration property for each item in the collection to 30 days.

    Get-CsAddressBookConfiguration | Where-Object {$_.KeepDuration -lt 30} | Set-CsAddressBookConfiguration -KeepDuration 30

## Detailed Description

Address Book servers are intermediaries between AD DS and Lync Server. The Address Book server ensures that the user information stored in Lync Server is in synch with the user information stored in AD DS. This is done by periodically synching Address Book files with information stored in the 用户数据库.

In addition, Address Book servers periodically generate index files that are downloaded to computers running Lync. When a user searches for contacts, he or she either search through these index files or search the Address Book index files stored in the 中央管理存储.

Address Book servers are governed using Address Book configuration settings; these settings determine such things as how often Address Book files are synchronized with the user database and how often these Address Book index files are generated. When you install Lync Server, a set of global Address Book settings is created for you. You can also create custom configuration settings that can be applied to individual sites. These settings, if they exist, apply to any Address Book servers operating in the site, and take precedence over the global settings.

The **Set-CsAddressBookConfiguration** cmdlet enables you to modify any of the Address Book configuration settings collection currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAddressBookConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAddressBookConfiguration"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableFileGeneration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) the Address Book server generates Address Book index files that can be downloaded by clients. When set to False, these index files are not generated. That means that client applications will have to use the 通讯簿 Web 查询服务 when searching for contacts.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePhotoSearch</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, user photos will be displayed in search results.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier assigned to the collection of Address Book settings. To refer to the global settings, use this syntax: -Identity global. To refer to a collection configured at the site scope, use syntax similar to this: -Identity site:Redmond. You cannot use wildcard characters when specifying an Identity.</p>
<p>If this parameter is omitted, then the <strong>Set-CsAddressBookConfiguration</strong> cmdlet will modify the global settings.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreGenericRules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the Address Book server ignores the generic normalization rules used when parsing phone numbers. Generic rules are the rules that are built into Lync Server. These rules cannot be changed; however, by setting the value of this property to True you can instruct your Address Book servers to ignore these rules and instead use custom rules that you create yourself. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>AddressBookSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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
<td><p>When changes are made to Active Directory (such as a new user being enabled for Lync Server), the Address Book server typically records these changes in a &quot;delta file,&quot; a file consisting only of the updated information; Lync can then download the delta files rather than a complete Address Book file. The MaxDeltaFileSizePercentage property determines how large the delta files can get before they are incorporated into the complete Address Book file. By default, delta files can be as large as 20 percent of the complete Address Book file before a new Address Book file is generated. At that point, Lync clients will download the complete file rather than a delta file.</p>
<p>MaxDeltaFileSizePercentage must be entered as a percentage value between 1 and 100, inclusive.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.AddressBook.AddressBookSettings object. The **Set-CsAddressBookConfiguration** cmdlet accepts pipelined input of Address Book configuration objects.

## Return Types

The **Set-CsAddressBookConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.AddressBook.AddressBookSettings object.

## 另请参阅

#### 其他资源

[Get-CsAddressBookConfiguration](get-csaddressbookconfiguration.md)  
[New-CsAddressBookConfiguration](New-CsAddressBookConfiguration.md)  
[Remove-CsAddressBookConfiguration](remove-csaddressbookconfiguration.md)

