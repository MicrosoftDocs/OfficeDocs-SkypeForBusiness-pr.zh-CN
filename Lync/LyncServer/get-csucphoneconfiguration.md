---
title: Get-CsUCPhoneConfiguration
TOCTitle: Get-CsUCPhoneConfiguration
ms:assetid: 014bba9e-b5c4-477d-9273-c993e7a7ee9e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398070(v=OCS.15)
ms:contentKeyID: 49311803
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsUCPhoneConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information regarding management options for Lync Phone Edition. This includes such things as the required security mode and whether or not the phone should automatically be locked after a specified period of inactivity. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsUCPhoneConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsUCPhoneConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns all of the UC phone configuration settings currently in use in the organization. Calling the **Get-CsUCPhoneConfiguration** cmdlet without any parameters always returns a complete collection of phone configuration settings.

    Get-CsUCPhoneConfiguration

## EXAMPLE 2

In Example 2, only the UC phone configuration settings that have the Identity site:Redmond are returned. Because Identities must be unique, this command will never return more than one collection of phone configuration settings.

    Get-CsUCPhoneConfiguration -Identity site:Redmond

## EXAMPLE 3

In Example 3, all the UC phone settings that have been configured at the site scope are returned. To do this, the **Get-CsUCPhoneConfiguration** cmdlet is called, along with the Filter parameter; the filter value "site:\*" limits the returned data to settings where the Identity property (the only property you can filter on) begins with the string value "site:". By definition, any settings that have an Identity that begins with the string value "site:" are settings that have been configured at the site scope.

    Get-CsUCPhoneConfiguration -Filter site:*

## EXAMPLE 4

Example 4 returns the UC phone configuration settings where the SIP security mode is set to Medium. (SIP security can be set to Low, Medium, or High.) To carry out this task, the command first uses the **Get-CsUCPhoneConfiguration** cmdlet without any additional parameters in order to return a collection of all the UC phone settings configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the SIPSecurityMode property is equal to Medium.

    Get-CsUCPhoneConfiguration | Where-Object {$_.SIPSecurityMode -eq "Medium"}

## EXAMPLE 5

In Example 5, UC phone settings are returned that meet one or both of the following criteria: 1) phone locking is not enforced; and/or, 2) the minimum PIN length is less than 6 digits. To do this, the command first calls the **Get-CsUCPhoneConfiguration** cmdlet to return a collection of all the UC phone settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects those items that meet one (or both) of the following criteria: 1) the EnforcePhoneLock property is equal to False; and/or, 2) the MinPhoneLength property is less than 6.

The -or operator tells the **Where-Object** cmdlet to pick settings that meet either (or both) of the criteria. To pick settings that meet both the criteria (in this case, meaning that phone locking is not enforced and the PIN length is less than 6) use the -and operator:

Where-Object {$\_.EnforcePhoneLock -eq $False -and $\_.MinPhonePinLength -lt 6}

    Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False -or $_.MinPhonePinLength -lt 6}

## Detailed Description

Lync Phone Edition represents the merging of the telephone and Lync Server. Lync Phone Edition uses special hardware (that is, a Lync-compatible telephone) that can function as a Voice over Internet Protocol (VoIP) telephone. In addition, this hardware can also act as a Lync-like endpoint: you can set your current status; check the status of your Lync contacts; search for new contacts; and carry out many of the other activities you are used to doing with Lync.

The CsUCPhoneConfiguration cmdlets enable you to manage your Lync Phone Edition phones; for example, you can control such things as the minimum length of the personal identification number (PIN) used to log on to the phone, and whether or not that phone will automatically lock itself after a specified period of inactivity.

Phone configuration settings can be applied at either the global scope or at the site scope. (Settings applied at the site scope take precedence over settings applied at the global scope.) The **Get-CsUCPhoneConfiguration** cmdlet enables you to retrieve information about the phone configuration settings current employed throughout your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsUCPhoneConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsUCPhoneConfiguration"}

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
<td><p>Enables you to use wildcard characters in order to return a collection (or collections) of UC phone configuration settings. To return a collection of all the settings configured at the site scope, use this syntax: -Filter site:*. To return a collection of all the settings that have the string value &quot;EMEA&quot; somewhere in their Identity (the only property you can filter for), use this syntax: -Filter *EMEA*.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of unified communications (UC) phone configuration settings you want to return. To refer to the global settings use this syntax: -Identity global. To refer to a collection configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards then include the Filter parameter instead.</p>
<p>If this parameter is not specified then the <strong>Get-CsUCPhoneConfiguration</strong> cmdlet returns a collection of all the UC phone configuration settings in use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the UC phone configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsUCPhoneConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsUCPhoneConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.UcPhoneSettings object.

## 另请参阅

#### 其他资源

[New-CsUCPhoneConfiguration](new-csucphoneconfiguration.md)  
[Remove-CsUCPhoneConfiguration](remove-csucphoneconfiguration.md)  
[Set-CsUCPhoneConfiguration](set-csucphoneconfiguration.md)

