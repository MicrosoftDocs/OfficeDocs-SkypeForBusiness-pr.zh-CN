﻿---
title: Get-CsEffectivePolicy
TOCTitle: Get-CsEffectivePolicy
ms:assetid: 03b2984f-3a24-4b8d-bcaf-5049de9e2556
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204636(v=OCS.15)
ms:contentKeyID: 49311841
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsEffectivePolicy

 

_**上一次修改主题：** 2015-03-09_

Returns the "effective policies" for the specified user or users. This simply means that, if a user has been a per-user policy, the Identity of that policy will be displayed. If a user has not been assigned a per-user policy, then the **Get-CsEffectivePolicy** cmdlet will indicate whether the user is managed by a service policy, a site policy, or the global policy. This enables you to determine exactly which policy is being used to manage a given user. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsEffectivePolicy -Identity <UserIdParameter> [-Credential <PSCredential>] [-DomainController <Fqdn>] [-ResultSize <Unlimited>]

## Examples

## Example 1

The command shown in Example 1 returns the effective policies for the user with the Active Directory display name Ken Myer.

    Get-CsEffectivePolicy - Identity "Ken Myer"

## Example 2

In the preceding command, effective policy information is returned for users with the display names Ken Myer and Pilar Ackerman. Policy information for multiple users can be returned by piping multiple user Identities to the **Get-CsEffectivePolicy** cmdlet.

    "Ken Myer","Pilar Ackerman" | Get-CsEffectivePolicy

## Example 3

In Example 3, effective policy information is returned for all the users who have been assigned the conferencing policy RedmondConferencingPolicy. To do this, the command first uses the **Get-CsUser** cmdlet to return a collection of users who have been assigned RedmondConferencingPolicy; the Filter parameter and the filter value {ConferencingPolicy –eq "RedmondConferencingPolicy"} limits the returned data to users who have been assigned the RedmondConferencingPolicy per-user conferencing policy. That collection of user accounts is then piped to the **Get-CsEffectivePolicy** cmdlet, which displays effective policy information for each user in the collection.

    Get-CsUser -Filter {ConferencingPolicy -eq "RedmondConferencingPolicy"} | Get-CsEffectivePolicy

## Example 4

Example 4 is a variation of the command shown in Example 3. In this example, effective policy information is again returned for all the users who have been assigned the conferencing policy RedmondConferencingPolicy; in this case, however, the returned information is limited to the user Identity and mobility policy. This is done by returning all the effective policy information and then piping that data to the **Select-Object** cmdlet, which, in turn, is used to limit the displayed data to the Identity and MobilityPolicy properties.

    Get-CsUser -Filter {ConferencingPolicy -eq "RedmondConferencingPolicy"} | Get-CsEffectivePolicy | Select-Object Identity, MobilityPolicy

## Example 5

In Example 5, effective policy information is displayed for all the users in the Finance department. This task is carried out by first using the **Get-CsUser** cmdlet and the LdapFilter property to return a collection of user accounts; the filter value "Department=Finance" limits those accounts to users who work in the Finance department. That collection is then piped to the **Get-CsEffectivePolicy** cmdlet, which displays effective policy information for each user in the collection.

    Get-CsUser -LdapFilter "Department=Finance" | Get-CsEffectivePolicy

## Detailed Description

Among other things, the **Get-CsUser** cmdlet returns information about the Microsoft Lync Server policies that are used to govern a user's behavior. For example:

DialPlan : RedmondDialPlan

LocationPolicy : RedmondLocationPolicy

ClientPolicy :

In the preceding output, it would appear that the user is being managed by a specific dial plan and location policy, but is not managed by a client. In truth, the user is managed by a client policy, either the global policy or a site policy. However, the **Get-CsUser** cmdlet only returns information about per-user policies that have been assigned to the user; of the user is managed by a global policy, a site policy, or a service policy, then the **Get-CsUser** cmdlet returns no information.

In troubleshooting scenarios, it can been very useful to know whether a user is managed by a global policy, a site policy, or a service policy. In cases such as that, you can use the **Get-CsEffectivePolicy** cmdlet to return exact information about the policies that are used to govern a user's behavior. For the preceding user, the **Get-CsEffectivePolicy** cmdlet might return information similar to this:

LocationProfile : RedmondDialPlan

LocationPolicy : RedmondLocationPolicy

ClientPolicy : Global

This output lets you know that the user is managed by the global client policy.

Note that, unlike the **Get-CsUser** cmdlet, the **Get-CsEffectivePolicy** cmdlet only returns information about policies; it does not return additional information such as the user's phone number or Registrar pool. Note, too that there are some differences in the terminology used in the **Get-CsUser** cmdlet to label policies names vs. the terminology used by the **Get-CsEffectivePolicy** cmdlet. For example, the **Get-CsUser** cmdlet uses the name DialPlan while the **Get-CsEffectivePolicy** cmdlet uses the name LocationProfile.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsEffectivePolicy"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsEffectivePolicy** cmdlet are not directly available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the user account whose effective policy settings are being calculated. User Identities are typically specified by using one of the following formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). You can also reference a user account by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the Get-CsEffectivePolicy cmdlet under alternate credentials. This might be required if the account you used to log on to Windows does not have the necessary privileges required to work with user objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object by using the <strong>Get-Credential</strong> cmdlet. For details, see the <strong>Get-Credential</strong> cmdlet help topic.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve user information. To connect to a particular domain controller, include the DomainController parameter followed by the fully qualified domain name (FQDN). For example:</p>
<p>-DomainController &quot;atl-dc-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven users (regardless of the number of users that are in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven users will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three users in your forest, the command will return those three users and then complete without error.</p></td>
</tr>
</tbody>
</table>


## Input Types

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Get-CsEffectivePolicy** cmdlet accepts a pipelined string value representing the display name of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

The **Get-CsEffectivePolicy** cmdlet returns instances of the Microsoft.Rtc.Management.AD.Cmdlets.EffectivePolicies object.

## 另请参阅

#### 其他资源

[Get-CsUser](get-csuser.md)

