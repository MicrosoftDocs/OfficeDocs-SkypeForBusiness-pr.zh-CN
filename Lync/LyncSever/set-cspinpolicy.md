---
title: Set-CsPinPolicy
TOCTitle: Set-CsPinPolicy
ms:assetid: f0e1afb9-4c71-45c5-8093-6cd12db3d697
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412997(v=OCS.15)
ms:contentKeyID: 49314693
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPinPolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies one or more existing client personal identification number (PIN) policies. PIN authentication enables users to access Lync Server by providing a PIN instead of a user name and password. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsPinPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPinPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AllowCommonPatterns <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-MaximumLogonAttempts <UInt32>] [-MinPasswordLength <UInt32>] [-PINHistoryCount <UInt64>] [-PINLifetime <UInt64>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits.

    Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10

## EXAMPLE 2

Example 2 modifies two properties of the per-user PIN policy with the Identity RedmondUsersPinPolicy: it changes the value of the MinPasswordLength and the AllowCommonPatterns properties.

    Set-CsPinPolicy -Identity RedmondUsersPinPolicy -MinPasswordLength 10 -AllowCommonPatterns $True

## EXAMPLE 3

The command shown in Example 3 changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection.

    Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10

## Detailed Description

Lync Server enables users to connect to the system, or to join public switched telephone network (PSTN) conferences via telephone. Typically, logging on to the system or joining a conference requires the user to enter a user name or password; unfortunately, entering a user name and password can be a problem if you are using a phone that does not have an alphanumeric keypad. Because of that, Lync Server enables you to supply users with numeric-only PINs; when prompted, users can then log on to the system or join a conference by entering the PIN instead of a user name and password.

Lync Server uses client PIN policies to manage PIN authentication properties; for example, you can specify the minimum length for a PIN as well as determine whether to allow PINs that use "common patterns" such as consecutive digits (for example, a PIN like 123456). PIN policies can be configured at the global, site, and per-user scopes; you can use the **Set-CsPinPolicy** cmdlet to modify the property values for any of these policies.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsPinPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPinPolicy"}

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
<td><p><em>AllowCommonPatterns</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not &quot;common patterns&quot; are allowed in PINs. Common patterns include repeating digits (225577); 4 or more consecutive digits (991234); and PINs that match a user's phone number or extension number. If set to True common patterns (such as the PIN 123456, which includes consecutive digits) are allowed; if set to False common patterns are not allowed. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional text to accompany a PIN policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
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
<td><p>Unique identifier assigned to the policy when it was created. PIN policies can be assigned at the global, site, or per-user scope. To refer to the global instance, use this syntax: -Identity global. To refer to a policy at the site scope, use syntax similar to this: -Identity site:Redmond. To refer to a per-user policy, use syntax similar to this: -Identity RedmondPinPolicy.</p>
<p>If you do not specify an Identity, then the <strong>Set-CsPinPolicy</strong> cmdlet will modify the global policy.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>UserPinPolicy object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>MaximumLogonAttempts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the number of sequential logon failures that are allowed before a user's PIN is automatically locked. Logon failures are counted in two different ways: local logon failures and global logon failures. When a user first tries to logon, a new 30 minute observation window starts; each failed logon during that 30 minute window is recorded as both a local logon failure and a global logon failure. If the user reaches the MaximumLogonAttempts during that 30 minute observation window then he or she will temporarily be locked out of the system for one hour; during this time they will not be able to logon using PIN authentication even if they supply the correct PIN.</p>
<p>After the lockout period has expired, the user’s local logon attempts will be reset to 0. However, the user’s global logon attempts will not be reset. If the user continually fails to logon, he or she will eventually reach the maximum number of allowed global logon attempts. Any user who reaches that point will have their PIN locked by the system, and will not be able to use PIN authentication until an administrator has unlocked the PIN.</p>
<p>The maximum number of allowed logon attempts also varies with PIN size; this is why the MaximumLogonAttempts property does not show a default value when you run the <strong>Get-CsPinPolicy</strong> cmdlet. By default, a PIN length of 4 allows users 10 local logon attempts and 100 global logon attempts. A PIN length of 5 allows 25 local and 1000 global logon attempts, and PIN lengths greater than 6 allow 25 local tries and 5000 global tries. If you specify a value for the MaximumLogonAttempts property that value will be used for the maximum allowed number of local logon tries; however, global logon values do not change regardless of the value assigned to MaximumLogonAttempts.</p>
<p>Each time a user successfully logs on using PIN authentication the local failed logon attempts is reset to 0. The global logon attempts are only reset when an administrator unlocks a user’s PIN.</p>
<p>MaximumLogonAttempts can be set to any whole number between 1 and 999, inclusive. However, we recommend that you do not modify this property. When set to a null value (the default value) Lync Server 2013 will automatically calculate lockout policies. This typically provides the highest level of security.</p></td>
</tr>
<tr class="even">
<td><p><em>MinPasswordLength</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The minimum allowed length (that is, the minimum number of digits) in a PIN number. For example, if MinPasswordLength is set to 8, then a PIN of 1259 will be rejected because that PIN only has 4 digits. PIN lengths must have at least 4 digits but no more than 24 digits; the default value is 5.</p></td>
</tr>
<tr class="odd">
<td><p><em>PINHistoryCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Indicates how often users are allowed to reuse the same PIN. For example, if the PINHistoryCount is set to 3, then the first three times users reset their PINs they must use a new PIN; on the fourth reset, they can reuse their first PIN. (And, on the fifth reset, they can use their second PIN, and so on.) The PIN history count can be any whole number between 0 and 20, inclusive; 0 means that users can use the same PIN over and over again. By default, PINHistoryCount is set to 0.</p>
<p>If the PINLifetime is set to any value greater than 0 then the PINHistoryCount must also be greater than 0. For example, you cannot set PINLifetime to 30 and leave PINHistoryCount at 0.</p></td>
</tr>
<tr class="even">
<td><p><em>PINLifetime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Indicates the length of time (in days) that a PIN remains valid; after the PIN lifetime expires, users must select a new PIN before they will be allowed to use PIN authentication to gain access to the system. PINLifetime can be set to any whole number between 0 and 999, inclusive; 0 indicates that PINs never expire. By default, the PIN lifetime is set to 0 days.</p>
<p>If you set the PINLifetime to a value greater than 0 then you must also set the PINHistoryCount to a value greater than 0.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.UserPin.UserPolicy object. The **Set-CsPinPolicy** cmdlet accepts pipelined input of the PIN policy object.

## Return Types

The **Set-CsPinPolicy** cmdlet does not return a value or object. Instead, the cmdlet configures one or more instances of the Microsoft.Rtc.Management.WritableConfig.Policy.UserPin.UserPolicy object.

## 另请参阅

#### 其他资源

[Get-CsPinPolicy](get-cspinpolicy.md)  
[Grant-CsPinPolicy](grant-cspinpolicy.md)  
[New-CsPinPolicy](new-cspinpolicy.md)  
[Remove-CsPinPolicy](remove-cspinpolicy.md)

