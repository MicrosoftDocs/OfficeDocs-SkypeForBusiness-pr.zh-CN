---
title: New-CsHealthMonitoringConfiguration
TOCTitle: New-CsHealthMonitoringConfiguration
ms:assetid: 8ed1da01-f7db-482d-b99a-777f239908e7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398718(v=OCS.15)
ms:contentKeyID: 49313563
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsHealthMonitoringConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of health monitoring configuration settings for use in your organization. These settings enable administrators to run quality assurance tests without having to supply the user names and passwords for the required test accounts. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsHealthMonitoringConfiguration -TargetFqdn <String> <COMMON PARAMETERS>

    New-CsHealthMonitoringConfiguration -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -FirstTestUserSipUri <String> -SecondTestUserSipUri <String> [-Confirm [<SwitchParameter>]] [-FirstTestSamAccountName <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-SecondTestSamAccountName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of health monitoring configuration settings for the pool atl-cs-001.litwareinc.com. These new settings will use sip:kenmyer@litwareinc.com and sip:pilar@litwareinc.com as the preconfigured test accounts.

    New-CsHealthMonitoringConfiguration -Identity atl-cs-001.litwareinc.com -FirstTestUserSipUri "sip:kenmyer@litwareinc.com" -SecondTestUserSipUri "sip:pilar@litwareinc.com"

## EXAMPLE 2

Example 2 creates a new collection of health monitoring configuration settings for all the Registrar pools in the organization. To do that, the first command in the example uses the **Get-Service** cmdlet and the Registrar parameter to return a collection of all the Registrar pools. This collection is then piped to the **Select-Object** cmdlet, which picks out only the PoolFqdn property. (This property returns the FQDN of a Registrar pool.) These FQDNs are stored in a variable named $x.

In the second command, a foreach loop is created to loop through each Registrar pool FQDN. For each FQDN, the **New-CsHealthMonitoringConfiguration** cmdlet is called to create a new collection of configuration settings, with the FQDN stored in $x used as the Identity for the new collection. Each collection is also assigned the same two test accounts: sip:kenmyer@litwareinc.com and sip:pilar@litwareinc.com.

    $x = Get-CsService -Registrar | Select-Object PoolFqdn
    foreach ($i in $x)
       {New-CsHealthMonitoringConfiguration -Identity $i.PoolFqdn -FirstTestUserSipUri "sip:kenmyer@litwareinc.com" -SecondTestUserSipUri "sip:pilar@litwareinc.com"}

## Detailed Description

Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN). These tests can be conducted "manually" by an administrator, or they can be automatically run by an application such as Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager）.

Synthetic transactions can be conducted in two different ways. Many administrators will use the **CsHealthMonitoringConfiguration** cmdlets to set up test accounts for each of their Registrar pools. These test accounts are a pair of user accounts that have been preconfigured for use with synthetic transactions. (Typically these are test accounts and not accounts that belong to actual users.) When these test accounts are configured for a pool, administrators can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test. Instead, the synthetic transaction will automatically use the preconfigured test accounts when performing its checks.

Alternatively, administrators can run a synthetic transaction using actual user accounts. For example, if two users are unable to exchange instant messages, an administrator can run a synthetic transaction using the two user accounts in question (as opposed to a pair of test accounts). If you decide to conduct a synthetic transaction using actual user accounts you will have to supply the credentials for each user.

The **New-CsHealthMonitoringConfiguration** cmdlet provides a way for you to create a new health monitoring configuration settings for a Registrar or Director pool. When creating a new collection of health monitoring configuration settings, you must specify the fully qualified domain name (FQDN) of the pool, as well as the SIP addresses of the two accounts that will serve as the pool test accounts. (However, you do not need to provide the passwords for those test accounts.) Note that each pool can host, at most, a single collection of health monitoring configuration settings. If you try to create a new collection for the pool atl-cs-001.litwareinc.com and this pool has already been assigned a Registrar, then your command will fail.

When you run the **New-CsHealthMonitoringConfiguration** cmdlet you might receive a warning if you have pools that have not been assigned test users; this might include Director pools as well as Office Communications Server pools. These warnings can be ignored. If you prefer, you can assign test users homed on other pools to your Director pools; that would enable you to run the **Test-CsRegistration** cmdlet against the Director. However, test users cannot be assigned to Office Communications Server pools.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsHealthMonitoringConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsHealthMonitoringConfiguration"}

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
<td><p><em>FirstTestUserSipUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the first test user to be configured for use by this collection of health monitoring settings. Note that the SIP address must include the sip: prefix. For example: -FirstTestUserSipUri &quot;sip:kenmyer@litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>FQDN of the pool where the health monitoring configuration settings are to be assigned (for example: -Identity atl-cs-001.litwareinc.com). Your command will fail if the specified pool already hosts a collection of health monitoring configuration settings.</p>
<p>The Identity is equivalent to the TargetFqdn parameter. When creating a new collection of settings, you can use either parameter. If you leave out both parameters, the <strong>New-CsHealthMonitoringConfiguration</strong> cmdlet will prompt you to enter the Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>SecondTestUserSipUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the second test user to be configured for use by this collection of health monitoring settings. Note that the SIP address must include the sip: prefix. For example: -SecondTestUserSipUri &quot;sip:pilar@litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>FQDN of the pool where the health monitoring configuration settings are to be assigned (for example: -TargetFqdn atl-cs-001.litwareinc.com). Your command will fail if the specified pool already hosts a collection of health monitoring configuration settings.</p>
<p>The TargetFqdn is equivalent to the Identity parameter. When creating a new collection of settings, you can use either parameter. If you leave out both parameters, the <strong>New-CsHealthMonitoringConfiguration</strong> cmdlet will prompt you to enter the Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>FirstTestSamAccountName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SamAccountName of the first test user. The FirstTestSamAccountName must be entered by using the format domain\username; for example:</p>
<p>-FirstTestSamAccountName litwareinc\kenmyer</p></td>
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
<td><p><em>SecondTestSamAccountName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SamAccountName of the second test user. The SecondTestSamAccountName must be entered by using the format domain\username; for example:</p>
<p>-SecondTestSamAccountName litwareinc\pilar</p></td>
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

None. The **New-CsHealthMonitoringConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsHealthMonitoringConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.HealthMonitoring.HealthMonitoringSettings object.

## 另请参阅

#### 其他资源

[Get-CsHealthMonitoringConfiguration](get-cshealthmonitoringconfiguration.md)  
[Remove-CsHealthMonitoringConfiguration](remove-cshealthmonitoringconfiguration.md)  
[Set-CsHealthMonitoringConfiguration](set-cshealthmonitoringconfiguration.md)

