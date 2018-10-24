---
title: Get-CsExternalAccessPolicy
TOCTitle: Get-CsExternalAccessPolicy
ms:assetid: 301403c8-aeb2-4501-a2ae-96eaa6ad68a4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425805(v=OCS.15)
ms:contentKeyID: 49312389
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsExternalAccessPolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about the external access policies that have been configured for use in your organization. External access policies determine whether or not your users can: 1) communicate with users who have Session Initiation Protocol (SIP) accounts with a federated organization; 2) communicate with users who have SIP accounts with a public instant messaging (IM) provider such as Windows Live; and, 3) access Lync Server over the Internet, without having to log on to your internal network. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsExternalAccessPolicy [-Identity <XdsIdentity>] [[-ApplicableTo] <Object>] <COMMON PARAMETERS>

    Get-CsExternalAccessPolicy [-Filter <String>] [[-ApplicableTo] <Object>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns a collection of all the external access policies configured for use in your organization. Calling the **Get-CsExternalAccessPolicy** cmdlet without any additional parameters always returns the complete collection of external access policies.

    Get-CsExternalAccessPolicy

## EXAMPLE 2

Example 2 uses the Identity parameter to return the external access policy that has the Identity site:Redmond. Because access policy Identities must be unique, this command will never return more than one item.

    Get-CsExternalAccessPolicy -Identity site:Redmond

## EXAMPLE 3

The command shown in Example 3 uses the Filter parameter to return all of the external access policies that have been configured at the per-user scope; the parameter value "tag:\*" limits returned data to those policies that have an Identity that begins with the string value "tag:". By definition, any policy that has an Identity beginning with "tag:" is a policy that has been configured at the per-user scope.

    Get-CsExternalAccessPolicy -Filter tag:*

## EXAMPLE 4

In Example 4, the **Get-CsExternalAccessPolicy** cmdlet and the **Where-Object** cmdlet are used to return all the external access policies that grant users federation access. To do this, the **Get-CsExternalAccessPolicy** cmdlet is first used to return a collection of all the external access policies currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those policies where the EnableFederationAccess property is equal to True.

    Get-CsExternalAccessPolicy | Where-Object {$_.EnableFederationAccess -eq $True}

## EXAMPLE 5

The command shown in Example 5 returns the external access policies that meet two criteria: both federation access and public cloud access are allowed. In order to perform this task, the command first uses the **Get-CsExternalAccessPolicy** cmdlet to return a collection of all the access policies in use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those policies that meet two criteria: the EnableFederationAccess property must be equal to True and the EnablePublicCloudAccess property must also be equal to True. Only policies in which both EnableFederationAccess and EnablePublicCloudAccess are True will be returned and displayed on the screen.

To return a list of policies where either EnableFederationAccess or EnablePublicCloudAccess are True use the –or operator:

Where-Object {$\_.EnableFederationAccess -eq $True -or $\_.EnablePublicCloudAccess -eq $True}

    Get-CsExternalAccessPolicy | Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $True} 

## Detailed Description

When you install Lync Server your users are only allowed to exchange instant messages and presence information among themselves: by default, they can only communicate with other people who have SIP accounts in your Active Directory 域服务. In addition, users are not allowed to access Lync Server over the Internet; instead, they must be logged on to your internal network before they will be able to log on to Lync Server.

That might be sufficient to meet your communication needs. If it doesn’t meet your needs, you can use external access policies to extend the ability of your users to communicate and collaborate. External access policies can grant (or revoke) the ability of your users to do any or all of the following:

1\. Communicate with people who have SIP accounts with a federated organization. Note that enabling federation alone will not provide users with this capability. Instead, you must enable federation and then assign users an external access policy that gives them the right to communicate with federated users.

2\. Communicate with people who have SIP accounts with a public instant messaging service such as Windows Live.

3\. Access Lync Server over the Internet, without having to first log on to your internal network. This enables your users to use Lync and log on to Lync Server from an Internet café or other remote location.

The **Get-CsExternalAccessPolicy** cmdlet provides a way for you to return information about all of the external access policies that have been configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsExternalAccessPolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsExternalAccessPolicy"}

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
<td><p>Enables you to do a wildcard search for external access policies. For example, to find all the policies configured at the site scope, use this Filter: site:*. To find the per-user policies Seattle, Seville, and Saskatoon (all of which start with the letter &quot;S&quot;) use this Filter: &quot;S*&quot;. Note that the Filter parameter can only be applied to the policy Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique Identity assigned to the policy when it was created. External access policies can be assigned at the global, site, or per-user scope. To refer to the global instance use this syntax: -Identity global. To refer to a policy at the site scope, use this syntax: -Identity site:Redmond. To refer to a policy at the per-user scope, use syntax similar to this: -Identity RedmondPolicy.</p>
<p>Note that wildcard characters such as the asterisk (*) cannot be used with the Identity parameter. To do a wildcard search for policies, use the Filter parameter instead.</p>
<p>If neither the Identity nor Filter parameters are specified, then the <strong>Get-CsExternalAccessPolicy</strong> cmdlet will bring back a collection of all the external access policies configured for use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the external access policy data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsExternalAccessPolicy** cmdlet does not accept pipelined input.

## Return Types

Returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ExternalAccess.ExternalAccessPolicy object.

## 另请参阅

#### 其他资源

[Grant-CsExternalAccessPolicy](grant-csexternalaccesspolicy.md)  
[New-CsExternalAccessPolicy](new-csexternalaccesspolicy.md)  
[Remove-CsExternalAccessPolicy](remove-csexternalaccesspolicy.md)  
[Set-CsExternalAccessPolicy](set-csexternalaccesspolicy.md)

