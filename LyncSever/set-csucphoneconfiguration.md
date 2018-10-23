---
title: Set-CsUCPhoneConfiguration
TOCTitle: Set-CsUCPhoneConfiguration
ms:assetid: f77456aa-992a-47d2-bdc7-5e3cbbfb6926
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413042(v=OCS.15)
ms:contentKeyID: 49314779
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUCPhoneConfiguration

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify management options for Lync Phone Edition. This includes such things as the required security mode and whether or not the phone should automatically be locked after a specified period of inactivity. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUCPhoneConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsUCPhoneConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-CalendarPollInterval <TimeSpan>] [-Confirm [<SwitchParameter>]] [-EnforcePhoneLock <$true | $false>] [-Force <SwitchParameter>] [-LoggingLevel <Off | Low | Medium | High>] [-MinPhonePinLength <Byte>] [-PhoneLockTimeout <TimeSpan>] [-SIPSecurityMode <Low | Medium | High>] [-Voice8021p <Byte>] [-VoiceDiffServTag <Byte>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 sets the SIP security mode of the global UC phone settings to Medium.

    Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

## EXAMPLE 2

Example 2 modifies the UC phone settings configured for the Redmond site. In this case, the PhoneLockTimeout property is set to 30 minutes; this is done by including the PhoneLockTimeout parameter and the parameter value "00:30:00" (00 hours: 30 minutes: 00 seconds).

    Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"

## EXAMPLE 3

Example 3 is a variation of the command shown in Example 2. This time, however, the PhoneLockTimeout property is modified for all the UC phone settings configured at the site scope. To do this, the command starts off by calling the **Get-CsUCPhoneConfiguration** cmdlet; the Filter parameter and the filter value "site:\*" limit the returned data to phone settings configured at the site scope. This filtered collection is then piped to the **Set-CsUCPhoneConfiguration** cmdlet, which uses the PhoneLockTimeout parameter and the parameter value "00:30:00" (00 hours: 30 minutes: 00 seconds) to set the phone lock timeout value for each item in the collection to 30 minutes.

    Get-CsUCPhoneConfiguration -Filter "site:*" | Set-CsUCPhoneConfiguration -PhoneLockTimeout "00:30:00"

## EXAMPLE 4

Example 4 configures the EnforcePhoneLock and the PhoneLockTimeout properties for all the UC phone settings where the SIP security mode is set to either Low or Medium. To perform this task, the command first uses the **Get-CsUCPhoneConfiguration** cmdlet to return all the UC phone configuration settings in the organization; this information is then piped to the **Where-Object** cmdlet, which picks out only those settings where the SIPSecurityMode property is not equal to High. (Because SIP security can only be set to Low, Medium, or High, this clause will select all the settings where SIPSecurityMode is set to either Low or Medium.) The filtered collection is then piped to the **Set-CsUCPhoneConfiguration** cmdlet, which uses the EnforcePhoneLock and the PhoneLockTimeout parameters to modify the phone locking and phone lock timeout properties.

    Get-CsUCPhoneConfiguration | Where-Object {$_.SIPSecurityMode -ne "High"} | Set-CsUCPhoneConfiguration -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

## EXAMPLE 5

In Example 5, the phone lock timeout value is set to 10 minutes for all the UC phone settings where the PhoneLockTimeout property is currently less than 10 minutes. (In effect, this makes 10 minutes the minimum phone lock timeout for the entire organization.) To do this, the command first uses the **Get-CsUCPhoneConfiguration** cmdlet to return a collection of all the UC phone settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the PhoneLockTimeout property is less than 10 minutes (00 hours: 10 minutes: 00 seconds). In turn, the filtered collection is piped to the **Set-CsUCPhoneConfiguration** cmdlet, which sets the PhoneLockTimeout value for each item in the collection to 10 minutes.

    Get-CsUCPhoneConfiguration | Where-Object {$_.PhoneLockTimeout -lt "00:10:00"} | Set-CsUCPhoneConfiguration -PhoneLockTimeout "00:10:00"

## Detailed Description

Lync Phone Edition represents the merging of the telephone and Lync Server. Lync Phone Edition uses special hardware (that is, a Lync-compatible telephone) that can function as a Voice over Internet Protocol (VoIP) telephone. In addition, this hardware can also act as a Lync-like endpoint: you can set your current status; check the status of your Lync contacts; search for new contacts; and carry out many of the other activities you are used to doing with Lync.

The **CsUCPhoneConfiguration** cmdlets enable you to use configuration settings to manage phones running Lync Server. For example, you can control such things as the minimum length of the personal identification number (PIN) used to log on to the phone and whether or not the phone will automatically lock itself after a specified period of inactivity.

Unified communications (UC) phone configuration settings can be applied at either the global scope or at the site scope. When you first install Lync Server, a single set of UC phone configuration settings is created and applied at the global scope. However, at any time after that you can use the **New-CsUCPhoneConfiguration** cmdlet to create a collection of settings that are applied at the site scope. This lets you tailor UC phone management to the unique needs of each individual site.

In addition to creating new collections of UC phone settings, you can use the **Set-CsUCPhoneConfiguration** cmdlet to modify the property values of an existing collection. For example, by default logging is disabled for UC phones. To enable logging at the global level, you can use the **Set-CsUCPhoneConfiguration** cmdlet to change the value of the global collection’s LoggingLevel property to True.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsUCPhoneConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUCPhoneConfiguration"}

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
<td><p><em>CalendarPollInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Indicates how often the UC device retrieves information from your Outlook calendar. The value must be specified using the format hours:minutes:seconds; for example, to set the time interval to 1 hour (the maximum allowed interval) use this syntax: -CalendarPollInterval &quot;01:00:00&quot;. The default value is 3 minutes (00:03:00).</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnforcePhoneLock</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether or not UC phones are automatically locked after the number of minutes specified by PhoneLockTimeout. The default value is True.</p></td>
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
<td><p>Represents the unique identifier assigned to the collection of UC phone configuration settings. To refer to the global settings, use this syntax: -Identity global. To refer to a collection configured at the site scope use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcard characters when specifying an Identity.</p>
<p>If this parameter is omitted, then the <strong>Set-CsUCPhoneConfiguration</strong> cmdlet will modify the global settings.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>UcPhoneSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>LoggingLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LoggingLevel</p></td>
<td><p>Enables logging on the UC device. Valid values are Off; Low; Medium; and High. The default value is Off.</p></td>
</tr>
<tr class="even">
<td><p><em>MinPhonePinLength</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Byte</p></td>
<td><p>Specifies the minimum number of digits required for personal identification numbers (PINs).</p>
<p>Minimum value: 4</p>
<p>Maximum value: 15</p>
<p>Default: 6</p></td>
</tr>
<tr class="odd">
<td><p><em>PhoneLockTimeout</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the length of time, in minutes, that a UC phone will remain idle before automatically locking.</p>
<p>This value must be less than 01:00:00 (1 hour). The default value is 00:10:00 (10 minutes).</p></td>
</tr>
<tr class="even">
<td><p><em>SIPSecurityMode</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.SIPSecurityMode</p></td>
<td><p>Specifies the level of security that the server applies to SIP sessions initiated by a UC phone.</p>
<p>Valid values are:</p>
<p>Low (allow any type of authorization or transport).</p>
<p>Medium (NTLM or Kerberos is required for user authentication).</p>
<p>High (NTLM or Kerberos is required for user authentication and TLS is required for SIP connections).</p>
<p>The default value is High.</p></td>
</tr>
<tr class="odd">
<td><p><em>Voice8021p</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Byte</p></td>
<td><p>Specifies the user priority value (the 802.1p value) for voice traffic within the Lync Server deployment.</p>
<p>This setting is effective only for networks in which switches and bridges are 802.1p-capable. The minimum value for this property is 0 and the maximum value is 7. The default value is 0.</p></td>
</tr>
<tr class="even">
<td><p><em>VoiceDiffServTag</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Byte</p></td>
<td><p>Specifies the decimal representation of the 6-bit DiffServ Code Point (DSCP) priority marking. This marking defines the Per Hop Behavior (PHB) for IP packets passed by the UC phones that are managed by this server.</p>
<p>This value must be between 0 and 63, inclusive. The default value is 40.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.UcPhoneSettings object. The **Set-CsUCPhoneConfiguration** cmdlet accepts pipelined instances of the UC phone settings object.

## Return Types

The **Set-CsUCPhoneConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.UcPhoneSettings object.

## 另请参阅

#### 其他资源

[Get-CsUCPhoneConfiguration](get-csucphoneconfiguration.md)  
[New-CsUCPhoneConfiguration](new-csucphoneconfiguration.md)  
[Remove-CsUCPhoneConfiguration](remove-csucphoneconfiguration.md)

