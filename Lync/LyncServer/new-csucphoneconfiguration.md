---
title: New-CsUCPhoneConfiguration
TOCTitle: New-CsUCPhoneConfiguration
ms:assetid: 633a593e-565d-4c04-affb-589502050212
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398445(v=OCS.15)
ms:contentKeyID: 49313047
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsUCPhoneConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of settings used to manage Lync Phone Edition. These settings enable you to configure such things as the required security mode, and to specify whether or not the phone should automatically be locked after a specified period of inactivity. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsUCPhoneConfiguration -Identity <XdsIdentity> [-CalendarPollInterval <TimeSpan>] [-Confirm [<SwitchParameter>]] [-EnforcePhoneLock <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LoggingLevel <Off | Low | Medium | High>] [-MinPhonePinLength <Byte>] [-PhoneLockTimeout <TimeSpan>] [-SIPSecurityMode <Low | Medium | High>] [-Voice8021p <Byte>] [-VoiceDiffServTag <Byte>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new collection of UC phone settings for the Redmond site. In this example, two optional parameters are included along with the required parameter Identity: CalendarPollInterval, which sets the calendar polling time to every 10 minutes (00 hours: 10 minutes: 00 seconds); and LoggingLevel, which sets the UC phone logging level to Medium. As soon as this command completes, the new settings will be applied to the Redmond site and users in that site will have their UC phones governed by the new settings. Note that this command will fail if the Redmond site already has a collection of UC phone settings.

    New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"

## EXAMPLE 2

Example 2 demonstrates the use of the InMemory parameter; this parameter enables you to create a new set of UC phone settings that exists in memory only. (These settings are stored in the variable $x.) After this virtual collection has been created, you can modify the in-memory-only settings using commands similar to those shown in lines 2 and 3 of the example: in line 2, the CalendarPollInterval property is set the 10 minutes (00 hours: 10 minutes: 00 seconds), and in line 3 the LoggingLevel property is set to Medium.

After you have finished modifying the property values, you can then use the **Set-CsUCPhoneConfiguration** cmdlet to turn the virtual settings stored in $x into an actual collection of settings applied to the Redmond site. Note that, with the use of the InMemory parameter, the settings are not actually applied until you call the **Set-CsUCPhoneConfiguration** cmdlet. If you do not call this cmdlet, your virtual settings will disappear when you end your Windows PowerShell session or when you delete the variable $x.

    $x = New-CsUCPhoneConfiguration -Identity site:Redmond -InMemory
    $x.CalendarPollInterval = "00:10:00" 
    $x.LoggingLevel = "Medium"
    Set-CsUCPhoneConfiguration -Instance $x

## Detailed Description

Lync Phone Edition represents the merging of the telephone and Lync Server. Lync Phone Edition uses special hardware (that is, a Lync Phone Edition compatible telephone) that can function as a Voice over Internet Protocol (VoIP) telephone. In addition, this hardware can also act as a Lync-like endpoint: you can set your current status; check the status of your Lync contacts; search for new contacts; and carry out many of the other activities you are used to doing with Lync.

Lync Server ships with a number of cmdlets that enable you to manage your phones running Lync Phone Edition; for example, you can control such things as the minimum length of the personal identification number (PIN) used to log on to the phone and whether or not the phone will automatically lock itself after a specified period of inactivity.

Unified communications (UC) phone configuration settings can be applied at either the global scope or at the site scope. (Settings applied at the site scope take precedence over settings applied at the global scope.) When you first install Lync Server, a single set of UC phone configuration settings is created and applied at the global scope. However, at any time after that you can use the **New-CsUCPhoneConfiguration** cmdlet to create a collection of settings that are applied at the site scope. This lets you tailor UC phone management to the unique needs of each individual site.

The **New-CsUCPhoneConfiguration** cmdlet enables you to create new UC phone settings at the site scope. Note that there can only be one collection of settings per site. For example, suppose you try to create a collection of settings that has the Identity site:Redmond, but the Redmond site already has a set of UC phone settings assigned to it. In that case, your command will fail. Instead, you must do one of two things: either remove the existing settings, and then use the **New-CsUCPhoneConfiguration** cmdlet to create a new collection of settings; or simply use the **Set-CsUCPhoneConfiguration** cmdlet to modify the existing settings.

You cannot create a new collection of settings at the global scope. The only thing you can do at the global scope is use the **Set-CsUCPhoneConfiguration** cmdlet to modify the existing settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsUCPhoneConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC roles this cmdlet )has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsUCPhoneConfiguration"}

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
<td><p>Represents the unique identifier to be assigned to the new collection of UC phone configuration settings. Because you can only create new collections at the site scope, the Identity will always be the prefix &quot;site:&quot; followed by the site name; for example &quot;site:Redmond&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>CalendarPollInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Indicates how often the UC device retrieves information from your Outlook calendar. The value must be specified using the format hours:minutes:seconds; for example, to set the time interval to 1 hour (the maximum allowed interval) use this syntax: -CalendarPollInterval &quot;01:00:00&quot;. The default value is 3 minutes (00:03:00).</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>EnforcePhoneLock</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether or not UC phones are automatically locked after the number of minutes specified by PhoneLockTimeout. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>LoggingLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LoggingLevel</p></td>
<td><p>Enables logging on the UC device. Valid values are Off; Low; Medium; and High. The default value is Off.</p>
<p></p></td>
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
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p>
<p></p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsUCPhoneConfiguration** cmdlet does not accept pipelined input.

## Return Types

Creates instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.UcPhoneSettings object.

## 另请参阅

#### 其他资源

[Get-CsUCPhoneConfiguration](get-csucphoneconfiguration.md)  
[Remove-CsUCPhoneConfiguration](remove-csucphoneconfiguration.md)  
[Set-CsUCPhoneConfiguration](set-csucphoneconfiguration.md)

