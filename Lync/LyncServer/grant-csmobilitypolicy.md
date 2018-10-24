---
title: Grant-CsMobilityPolicy
TOCTitle: Grant-CsMobilityPolicy
ms:assetid: c5ca6d6c-e442-4375-b8fd-1016a0aef33b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690038(v=OCS.15)
ms:contentKeyID: 49314183
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsMobilityPolicy

 

_**上一次修改主题：** 2015-03-09_

Grants a per-user mobility policy to a user or group of users. Mobility policies determine whether or not a user can use Lync Mobile. These policies also manage a user's ability to employ Call via Work, a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Grant-CsMobilityPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 assigns the per-user mobility policy RedmondMobilityPolicy to a single user: Ken Myer.

    Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## EXAMPLE 2

In Example 2, the mobility policy RedmondMobilityPolicy is assigned to users currently managed by the policy NorthAmericaMobilityPolicy. To do this, the command first uses the **Get-CsUser** cmdlet and the Filter parameter to retrieve all those users assigned the policy NorthAmericaMobilityPolicy; this is done by using the filter value {MobilityPolicy –eq "NorthAmericaMobilityPolicy"}. After retrieving the collection of user accounts, those accounts are then piped to the **Grant-CsMobilityPolicy** cmdlet, which assigns each user the policy RedmondMobilityPolicy.

    Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## EXAMPLE 3

Example 3 assigns the mobility policy RedmondMobilityPolicy to all the users located in the city of Redmond. To perform this task, the command first calls the **Get-CsUser** cmdlet along with the LdapFilter parameter; the filter value "l=Redmond" returns all the users located in Redmond. (The "l" represents the Active Directory attribute "locality".) After the user accounts have been retrieved, those accounts are piped to the **Grant-CsMobilityPolicy** cmdlet; in turn, the **Grant-CsMobilityPolicy** cmdlet assigns each user the policy RedmondMobilityPolicy.

    Get-CsUser -LdapFilter "l=Redmond" | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## EXAMPLE 4

In Example 4, RedmondMobilityPolicy is assigned to users who have Lync Server accounts homed on atl-cs-001.litwareinc.com. To do this, the command first uses the **Get-CsUser** cmdlet and the Filter parameter to retrieve all the user accounts homed on the specified Registrar pool; this can be done by using the filter value {RegistrarPool –eq "atl-cs-001.litwareinc.com"}. After retrieving the collection of user accounts, those accounts are then piped to the **Grant-CsMobilityPolicy** cmdlet, which assigns each user the policy RedmondMobilityPolicy.

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## Detailed Description

Lync Mobile is a client application that enables users to run Lync on their mobile phones. Call via Work provides a way for users to make calls on their mobile phone and yet have it appear as though the call originated from their work phone number instead of their mobile phone number. Users who have been enabled for Call via Work can achieve this either by dialing directly from their mobile phone or by using the dial-out conferencing option. With dial-out conferencing, a user effectively asks the Mobility Service server to make a call for them. The server will set up the call, and then call the user back on their mobile phone. After the user has answered, the server will then dial the party being called. Both of these capabilities can be managed by using mobility policies.

With Lync Server 2013 mobile devices can make or receive phone calls by using either the standard cellular phone network. or by using Wi-Fi connections. Mobility policies can be used to require Wi-Fi connections and to prevent calls over the cellular network.

When you install Lync Server, you will have a single, global mobility policy that applies to all your users. However, administrators can use the **New-CsMobilityPolicy** cmdlet to create custom policies at either the site or the per-user scope.

If you create a new policy at the site scope that policy will automatically be assigned to the appropriate site. However, if you create a mobility policy at the per-user scope, that policy will exist but will not automatically be assigned to any users. Instead, you must use the **Grant-CsMobilityPolicy** cmdlet to specifically assign a per-user policy to one or more users.

Note that mobility policies do not appear by default when you run the **Get-CsUser** cmdlet. Because of that, you cannot see the per-user mobility policy assigned to a user by running a command similar to this:

Get-CsUser "Ken Myer"

Instead, you will need to use a command like this to see all the property values (including the mobility policy) for a user:

Get-CsUser "Ken Myer" | Select-Object \*

Alternatively, you can use a command similar to this one to view just the display name and mobility policy for the user:

Get-CsUser "Ken Myer" | Select-Object DisplayName, MobilityPolicy

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsMobilityPolicy** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Indicates the Identity of the user account to be assigned the per-user mobility policy. User Identities are typically specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be specified by using the user’s Active Directory distinguished name.</p>
<p>In addition, you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; will assign the policy to all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to specify the fully qualified domain name (FQDN) of a domain controller to be contacted when assigning the new policy. If this parameter is not specified then the <strong>Grant-CsMobilityPolicy</strong> cmdlet will contact the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user being assigned the policy. By default, the <strong>Grant-CsMobilityPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (the &quot;tag:&quot; prefix). For example, a policy with the Identity tag:Redmond has a PolicyName equal to Redmond; a policy with the Identity tag:RedmondUsersMobilityPolicy has a PolicyName equal to RedmondUsersMobilityPolicy. To assign a per-user policy use syntax like this:</p>
<p>-PolicyName RedmondUsersMobilityPolicy</p>
<p>To unassign a per-user policy previously assigned to a user, set the PolicyName to a null value ($Null):</p>
<p>-PolicyName $Null</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Grant-CsMobilityPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsMobilityPolicy** cmdlet does not return any objects or values. However, if you include the PassThru parameter, the cmdlet will be able to pipeline instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact object.

