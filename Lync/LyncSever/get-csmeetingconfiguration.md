---
title: Get-CsMeetingConfiguration
TOCTitle: Get-CsMeetingConfiguration
ms:assetid: 3aa2d905-0ce0-4675-8543-c7bb9b4a3d1a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425875(v=OCS.15)
ms:contentKeyID: 49312551
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsMeetingConfiguration

 

_**上一次修改主题：** 2015-03-09_

The **Get-CsMeetingConfiguration** cmdlet enables you to return information about the meeting configuration settings currently in use in your organization. Meeting configuration settings help dictate the type of meetings (also called “conferences”) that users can create, and control how (or even if) anonymous users and dial-in conferencing users can join these meetings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsMeetingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsMeetingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>] [-Tenant <Guid>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the meeting configuration settings currently in use in the organization.

    Get-CsMeetingConfiguration

## EXAMPLE 2

In Example 2, only one collection of meeting configuration settings is returned: the settings that have the Identity site:Redmond.

    Get-CsMeetingConfiguration -Identity site:Redmond

## EXAMPLE 3

Example 3 returns all the meeting configuration settings that have been configured at the service scope. This is done by including the Filter parameter and the filter value "service:\*", which limits returned data to settings where the Identity property begins with the characters "service:".

    Get-CsMeetingConfiguration -Filter "service:*"

## EXAMPLE 4

In Example 4, information is returned for all the meeting configuration settings where anonymous users are admitted by default. To accomplish this task, the command first uses the **Get-CsMeetingConfiguration** cmdlet without any parameters to return a collection of all the meeting configuration settings currently in use. That collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the AdmitAnonymousByDefault property is equal to True.

    Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True}

## Detailed Description

Meetings (also called “conferences”) are an integral part of Lync Server. The **CsMeetingConfiguration** cmdlets enable administrators to control the type of meetings that users can create, and determine how meetings handle anonymous users and dial-in conferencing users. For example, you can configure meetings so that anyone dialing in over the public switched telephone network (PSTN) is automatically admitted to the meeting. Alternatively, you can configure meetings so that dial-in users are not automatically admitted the meeting, but are instead routed to the meeting lobby. These dial-in users remain on hold in the lobby until a presenter admits them to the meeting.

The **Get-CsMeetingConfiguration** cmdlet enables you to return information about the meeting configuration setting collections currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsMeetingConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsMeetingConfiguration"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters in order to return a collection (or collections) of meeting configuration settings. To return a collection of all the settings configured at the site scope, use this syntax: -Filter site:*. To return a collection of all the settings that have the string value &quot;EMEA&quot; somewhere in their Identity (the only property you can filter on) use this syntax: -Filter *EMEA*.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of meeting configuration settings you want to return. To refer to the global settings, use this syntax: -Identity global. To refer to a collection configured at the site scope, use syntax similar to this: -Identity site:Redmond. Settings configured at the service scope can be retrieved using syntax like this: -Identity service:UserServer:atl-cs-001.litwareinc.com.</p>
<p>If this parameter is not specified, then the <strong>Get-CsMeetingConfiguration</strong> cmdlet will return a collection of all the meeting settings in use in the organization.</p>
<p>Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards, then include the Filter parameter instead.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the meeting configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Office 365 tenant account whose meeting configuration settings are to be retrieved.</p>
<p>For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsMeetingConfiguration** cmdlet does not accept pipelined data.

## Return Types

The **Get-CsMeetingConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.MeetingConfiguration object.

## 另请参阅

#### 其他资源

[New-CsMeetingConfiguration](new-csmeetingconfiguration.md)  
[Remove-CsMeetingConfiguration](remove-csmeetingconfiguration.md)  
[Set-CsMeetingConfiguration](set-csmeetingconfiguration.md)

