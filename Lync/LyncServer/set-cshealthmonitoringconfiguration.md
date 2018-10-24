---
title: Set-CsHealthMonitoringConfiguration
TOCTitle: Set-CsHealthMonitoringConfiguration
ms:assetid: 375af06c-70c8-4775-8c7b-3b3f8fd9afcc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425847(v=OCS.15)
ms:contentKeyID: 49312488
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsHealthMonitoringConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of health monitoring configuration settings. These settings enable administrators to run quality assurance tests without having to supply the user names and passwords for the required test accounts. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsHealthMonitoringConfiguration [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsHealthMonitoringConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-FirstTestSamAccountName <String>] [-FirstTestUserSipUri <String>] [-Force <SwitchParameter>] [-SecondTestSamAccountName <String>] [-SecondTestUserSipUri <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 configures the first test user assigned to the health monitoring configuration settings for the pool atl-cs-001.litwareinc.com. In this example, the SIP address for the new test user is set to sip:kenmyer@litwareinc.com and the SamAccountName for the test user is set to kenmyer.

    Set-CsHealthMonitoringConfiguration -Identity atl-cs-001.litwareinc.com -FirstTestUserSipUri "sip:kenmyer@litwareinc.com" -FirstTestSamAccountName "litwareinc\kenmyer"

## EXAMPLE 2

Example 2 is a variation of the command shown in Example 1. In this case, however, the same test user is assigned to each collection of health monitoring configuration settings in use in the organization. To carry out this task, the command first uses the **Get-CsHealthMonitoringConfiguration** cmdlet to return a collection of all the health monitoring configuration settings. This collection is then piped to the **Set-CsHealthMonitoringConfiguration** cmdlet, which assigns the same first test user SIP address and SamAccountName to each item in the collection.

    Get-CsHealthMonitoringConfiguration | Set-CsHealthMonitoringConfiguration -FirstTestUserSipUri "sip:kenmyer@litwareinc.com" -FirstTestSamAccountName "litwareinc\kenmyer"

## EXAMPLE 3

Example 3 shows how you can do a search-and-replace for the first test user assigned to a collection of health configuration settings; in this example, the user with the SIP address sip:pilar@litwareinc.com is replaced any time that user appears as the first test user in a collection.

To do this, the command first calls the **Get-CsHealthMonitoringConfiguration** cmdlet without any additional parameters; that returns a collection of all the health monitoring configuration settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those items where the FirstTestUserSipUri property is equal to (-eq) sip:pilar@litwareinc.com. That filtered collection is then piped to the **Set-CsHealthMonitoringConfiguration** cmdlet, which takes each item in the collection and sets the value of the FirstTestUserSipUri property to sip:kenmyer@litwareinc.com and the value of the FirstTestSamAccountName property to kenmyer.

    Get-CsHealthMonitoringConfiguration | Where-Object {$_.FirstTestUserSipUri -eq "sip:pilar@litwareinc.com"} | Set-CsHealthMonitoringConfiguration -FirstTestUserSipUri "sip:kenmyer@litwareinc.com" -FirstTestSamAccountName "litwareinc\kenmyer"

## Detailed Description

Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN). These tests can be conducted manually by an administrator, or they can be automatically run by an application such as Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager）.

Synthetic transactions can be conducted in two different ways. Many administrators will use the **CsHealthMonitoringConfiguration** cmdlets to set up test accounts for each of their Registrar pools. These test accounts are a pair of user accounts that have been preconfigured for use with synthetic transactions. (Typically these are test accounts and not accounts that belong to actual users.) When test accounts are configured for a pool, administrators can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test. Instead, the synthetic transaction will automatically use the preconfigured test accounts when performing its checks.

Alternatively, administrators can run a synthetic transaction using actual user accounts. For example, if two users are unable to exchange instant messages, an administrator can run a synthetic transaction using the two user accounts in question (as opposed to a pair of test accounts). If you decide to conduct a synthetic transaction using actual user accounts that you will have to supply the credentials for each user.

After you have configured health monitoring configuration settings, you can modify those settings at any time by using the **Set-CsHealthMonitoringConfiguration** cmdlet. This cmdlet provides a way for you to change either (or both) of the test accounts configured for use with a pool .

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsHealthMonitoringConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsHealthMonitoringConfiguration"}

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
<td><p><em>FirstTestSamAccountName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SamAccountName of the first test user. The FirstTestSamAccountName must be entered using the format domain\username; for example:</p>
<p>-FirstTestSamAccountName litwareinc\kenmyer</p></td>
</tr>
<tr class="odd">
<td><p><em>FirstTestUserSipUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the first test user to be configured for use by this collection of health monitoring settings. Note that the SIP address must include the sip: prefix. For example: -FirstTestUserSipUri &quot;sip:kenmyer@litwareinc.com&quot;.</p></td>
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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool where the health monitoring configuration settings to be modified have been assigned. For example: -Identity atl-cs-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>HealthMonitoringSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>SecondTestSamAccountName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SamAccountName of the second test user. The SecondTestSamAccountName must be entered using the format domain\username; for example:</p>
<p>-SecondTestSamAccountName litwareinc\pilar</p></td>
</tr>
<tr class="even">
<td><p><em>SecondTestUserSipUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the second test user to be configured for use by this collection of health monitoring settings. Note that the SIP address must include the sip: prefix. For example: -FirstTestUserSipUri &quot;sip:pilar@litwareinc.com&quot;.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.HealthMonitoring.HealthMonitoringSettings object. The **Set-CsHealthMonitoringConfiguration** cmdlet accepts pipelined instances of the health monitoring configuration object.

## Return Types

None. Instead, the **Set-CsHealthMonitoringConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.HealthMonitoring.HealthMonitoringSettings object.

## 另请参阅

#### 其他资源

[Get-CsHealthMonitoringConfiguration](get-cshealthmonitoringconfiguration.md)  
[New-CsHealthMonitoringConfiguration](new-cshealthmonitoringconfiguration.md)  
[Remove-CsHealthMonitoringConfiguration](remove-cshealthmonitoringconfiguration.md)

