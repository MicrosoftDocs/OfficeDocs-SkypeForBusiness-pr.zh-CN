---
title: New-CsPinPolicy
TOCTitle: New-CsPinPolicy
ms:assetid: d64fb0f9-1cdc-4497-992a-d002abafe92e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398935(v=OCS.15)
ms:contentKeyID: 49314383
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPinPolicy

 

_**上一次修改主题：** 2015-03-09_

Creates a new client personal identification number (PIN) policy. PIN authentication enables users to access Lync Server by providing a PIN instead of a user name and password. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsPinPolicy -Identity <XdsIdentity> [-AllowCommonPatterns <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MaximumLogonAttempts <UInt32>] [-MinPasswordLength <UInt32>] [-PINHistoryCount <UInt64>] [-PINLifetime <UInt64>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **New-CsPinPolicy** cmdlet is used to create a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 10. All the remaining policy properties will be configured using the default values.

    New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10

## EXAMPLE 2

The command shown in Example 2 creates a new policy with the Identity site:Redmond. This command uses the parameters MinPasswordLength, PINHistoryCount, and PINLifetime to explicitly configure three different property values for the new policy.

    New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10 -PINHistoryCount 10 -PINLifetime 30

## EXAMPLE 3

The commands shown in Example 3 demonstrate how you can create a new PIN policy in memory only, modify the property values for that policy, and then use the **Set-CsPinPolicy** cmdlet to turn that in-memory-only policy into an actual PIN policy. In the first line above, the **New-CsPinPolicy** cmdlet and the InMemory parameter are used to create an in-memory policy with the Identity site:Redmond; this policy is stored in the variable $x. If the policy was not assigned to a variable it would be created in memory only and then immediately disappear as soon as the command completed.

After the virtual policy has been assigned to the variable $x, the next three commands are used to modify property values for that policy; for example, line 2 sets the value of the MinPasswordLength property to 10. After all the properties have been configured, the **Set-CsPinPolicy** cmdlet is used to create an actual policy with the Identity site:Redmond; this is done by using the Instance parameter and passing the variable $x as the parameter value. After the **Set-CsPinPolicy** cmdlet has been called, you will be able to view the policy and its property values by using the **Get-CsPinPolicy** cmdlet.

    $x = New-CsPinPolicy -Identity "site:Redmond" -InMemory
    $x.MinPasswordLength = 10
    $x.PINHistoryCount = 10
    $x.PINLifetime = 30
    Set-CsPinPolicy -Instance $x

## EXAMPLE 4

The commands used in Example 4 create a new PIN policy (site:Paris) that uses one of the property values found in the existing policy site:Redmond. To achieve this, the first command uses the **Get-CsPinPolicy** cmdlet to retrieve the PIN policy site:Redmond; the information retrieved for this policy is then stored in the variable $x.

In the second command, the **New-CsPinPolicy** cmdlet is used to create the policy site:Paris. In addition, the MinPasswordLength parameter is used to specify the value of the MinPasswordLength property. However, instead of using a hard-coded numeric value, the command uses $x.MinPasswordLength as the parameter value; this tells the **New-CsPinPolicy** cmdlet to set the minimum password length to the value of the MinPasswordLength property found in the policy site:Redmond. The net result is that the value of the MinPasswordLength property will be copied from the existing policy site:Redmond to the new policy site:Paris.

    $x = Get-CsPinPolicy -Identity "site:Redmond"
    New-CsPinPolicy -Identity "site:Paris" -MinPasswordLength $x.MinPasswordLength 

## Detailed Description

Lync Server enables users to connect to the system or to join public switched telephone network (PSTN) conferences via telephone. Users typically log on to the system or join a conference by entering a user name or password; however, entering a user name and password can be a problem if you are using a phone that does not have an alphanumeric keypad. Because of that, Lync Server enables you to supply users with numeric-only PINs; when prompted, users can then log on or join a conference by entering the PIN instead of a user name and password.

Lync Server uses PIN policies to manage PIN authentication properties; for example, you can specify the minimum length for a PIN as well as determine whether you will allow PINs that use "common patterns" such as consecutive digits (for example, a PIN like 123456). You can use the **New-CsPinPolicy** cmdlet to create new PIN authentication policies; these new policies can be configured at either the site or the per-user scope. (There is also a global PIN policy. However, you cannot create a second global PIN policy; all you can do is modify the existing global policy.)

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsPinPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPinPolicy"}

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
<td><p>Indicates the unique Identity to be assigned to the policy. PIN policies can be created at the site or per-user scope. To create a policy at the site scope, use syntax similar to this: -Identity site:Redmond. To create a policy at the per-user scope, use syntax similar to this: -Identity RedmondPinPolicy.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowCommonPatterns</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not &quot;common patterns&quot; are allowed in PINs. Common patterns include repeating digits (222222); four or more consecutive digits (123456); and PINs that match a user's phone number or extension number. If set to True common patterns (such as the PIN 456789, which includes consecutive digits) are allowed; if set to False common patterns are not allowed. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide explanatory text to accompany a PIN policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
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
<td><p><em>MaximumLogonAttempts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the number of sequential logon failures that are allowed before a user's PIN is automatically locked. Logon failures are counted in two different ways: local logon failures and global logon failures. When a user first tries to logon, a new 30 minute observation window starts; each failed logon during that 30 minute window is recorded as both a local logon failure and a global logon failure. If the user reaches the MaximumLogonAttempts during that 30 minute observation window then he or she will temporarily be locked out of the system for one hour; during this time they will not be able to logon using PIN authentication even if they supply the correct PIN.</p>
<p>After the lockout period has expired, the user’s local logon attempts will be reset to 0. However, the user’s global logon attempts will not be reset. If the user continually fails to logon, he or she will eventually reach the maximum number of allowed global logon attempts. Any user who reaches that point will have their PIN locked by the system, and will not be able to use PIN authentication until an administrator has unlocked the PIN.</p>
<p>The maximum number of allowed logon attempts also varies with PIN size; this is why the MaximumLogonAttempts property does not show a default value when you run Get-CsPinPolicy. By default, a PIN length of 4 allows users 10 local logon attempts and 100 global logon attempts. A PIN length of 5 allows 25 local and 1000 global logon attempts, and PIN lengths greater than 6 allow 25 local tries and 5000 global tries. If you specify a value for the MaximumLogonAttempts property that value will be used for the maximum allowed number of local logon tries; however, global logon values do not change regardless of the value assigned to MaximumLogonAttempts.</p>
<p>Each time a user successfully logs on using PIN authentication the local failed logon attempts is reset to 0. The global logon attempts are only reset when an administrator unlocks a user’s PIN.</p>
<p>MaximumLogonAttempts can be set to any whole number between 1 and 999, inclusive. However, it is recommended that you do not modify this property. When set to a null value (the default value) Lync Server 2013 will automatically calculate lockout policies. This typically provides the most security.</p></td>
</tr>
<tr class="even">
<td><p><em>MinPasswordLength</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The minimum allowed length (that is, the minimum number of digits) in a PIN. For example, if MinPasswordLength is set to 8 then a PIN of 1259 will be rejected because that PIN only has 4 digits. PIN lengths must have at least 4 digits but no more than 24 digits; the default value is 5.</p></td>
</tr>
<tr class="odd">
<td><p><em>PINHistoryCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Indicates how often users are allowed to reuse the same PIN. For example, if the PINHistoryCount is set to 3, then the first three times a user resets his or her PIN they must use a new PIN; on the fourth reset, they can reuse their first PIN. (And, on the fifth reset, they can reuse their second PIN, and so on.) The PIN history count can be any whole number between 0 and 20, inclusive; 0 means that users can use the same PIN number over and over again. By default, PINHistoryCount is set to 0.</p>
<p>If the PINLifetime is set to any value greater than 0 then the PINHistoryCount must also be greater than 0. For example, you cannot set PINLifetime to 30 and leave PINHistoryCount at 0.</p></td>
</tr>
<tr class="even">
<td><p><em>PINLifetime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Indicates the length of time (in days) that a PIN remains valid; after the PIN lifetime expires users must select a new PIN number before they will be allowed to use PIN authentication to gain access to the system. PINLifetime can be set to any whole number between 0 and 999, inclusive; 0 indicates that PIN numbers never expire. By default, the PIN lifetime is set to 0 days.</p>
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

None. The **New-CsPinPolicy** cmdlet does not accept pipelined input.

## Return Types

Creates a new instance of the Microsoft.Rtc.Management.WritableConfig.Policy.UserPin.UserPolicy object.

## 另请参阅

#### 其他资源

[Get-CsPinPolicy](get-cspinpolicy.md)  
[Grant-CsPinPolicy](grant-cspinpolicy.md)  
[Remove-CsPinPolicy](remove-cspinpolicy.md)  
[Set-CsPinPolicy](set-cspinpolicy.md)

