---
title: Set-CsExternalAccessPolicy
TOCTitle: Set-CsExternalAccessPolicy
ms:assetid: d3e45fbb-357f-4ff2-b52d-58b94e8f2241
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398916(v=OCS.15)
ms:contentKeyID: 49314348
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsExternalAccessPolicy

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify the properties of an existing external access policy. External access policies determine whether or not your users can: 1) communicate with users who have Session Initiation Protocol (SIP) accounts with a federated organization; 2) communicate with users who have SIP accounts with a public instant messaging (IM) provider such as MSN; and, 3) access Lync Server over the Internet, without having to log on to your internal network. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsExternalAccessPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsExternalAccessPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnableFederationAccess <$true | $false>] [-EnableOutsideAccess <$true | $false>] [-EnablePublicCloudAccess <$true | $false>] [-EnablePublicCloudAudioVideoAccess <$true | $false>] [-EnableXmppAccess <$true | $false>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the per-user external access policy that has the Identity RedmondExternalAccessPolicy. In this example, the command changes the value of the EnableFederationAccess property to True.

    Set-CsExternalAccessPolicy -Identity RedmondExternalAccessPolicy -EnableFederationAccess $True

## EXAMPLE 2

In Example 2, federation access is enabled for all the external access policies configured for use in the organization. To do this, the command first calls the **Get-CsExternalAccessPolicy** cmdlet without any parameters; this returns a collection of all the external policies currently configured for use. That collection is then piped to the **Set-CsExternalAccessPolicy** cmdlet, which changes the value of the EnableFederationAccess property for each policy in the collection.

    Get-CsExternalAccessPolicy | Set-CsExternalAccessPolicy -EnableFederationAccess $True

## EXAMPLE 3

Example 3 enables federation access for all the external access policies that have been configured at the per-user scope. To carry out this task, the first thing the command does is use the **Get-CsExternalAcessPolicy** cmdlet and the Filter parameter to return a collection of all the policies that have been configured at the per-user scope. (The filter value "tag:\*" limits returned data to policies that have an Identity that begins with the string value "tag:". Any policy with an Identity that begins with "tag:" has been configured at the per-user scope.) The filtered collection is then piped to the **Set-CsExternalAccessPolicy** cmdlet, which modifies the EnableFederationAccess property for each policy in the collection.

    Get-CsExternalAccessPolicy -Filter tag:* | Set-CsExternalAccessPolicy -EnableFederationAccess $True

## EXAMPLE 4

In Example 4, federation access is enabled for all the external access policies that allow public cloud access. To do this, the command first uses the **Get-CsExternalAccessPolicy** cmdlet to return a collection of all the external access policies currently configured for use in the organization. This collection is piped to the **Where-Object** cmdlet, which picks out only those policies where the EnablePublicCloudAccess property is equal to True. The filtered collection is then piped to the **Set-CsExternalAccessPolicy** cmdlet, which takes each policy and sets the EnableFederationAccess property to True. The net result: all external access policies that allow public cloud access will also allow federation access.

    Get-CsExternalAccessPolicy | Where-Object {$_.EnablePublicCloudAccess -eq $True} | Set-CsExternalAccessPolicy -EnableFederationAccess $True

## Detailed Description

When you install Lync Server your users are only allowed to exchange instant messages and presence information among themselves: by default, they can only communicate with people who have SIP accounts in your Active Directory 域服务. In addition, users are not allowed to access Lync Server over the Internet; instead, they must be logged on to your internal network before they will be able to log on to Lync Server.

That might be sufficient to meet your communication needs. If it doesn’t meet your needs, you can use external access policies to extend the ability of your users to communicate and collaborate. External access policies can grant (or revoke) the ability of your users to do any or all of the following:

1\. Communicate with people who have SIP accounts with a federated organization. Note that enabling federation alone will not provide users with this capability. Instead, you must enable federation and then assign users an external access policy that gives them the right to communicate with federated users.

2\. Communicate with people who have SIP accounts with a public instant messaging service such as MSN.

3.Access Lync Server over the Internet, without having to first log on to your internal network. This enables your users to use Lync and log on to Lync Server from an Internet café or other remote location.

After an external access policy has been created, you can use the **Set-CsExternalAccessPolicy** cmdlet to change the property values of that policy. For example, by default the global policy does not allow users to communicate with people who have accounts with a federated organization. If you would like to grant this capability to all of your users you can call the **Set-CsExternalAccessPolicy** cmdlet and set the value of the global policy’s EnableFederationAccess property to True.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsExternalAccessPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsExternalAccessPolicy"}

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
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional text to accompany the policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableFederationAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to communicate with people who have SIP accounts with a federated organization. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableOutsideAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to connect to Lync Server over the Internet, without logging on to the organization’s internal network. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePublicCloudAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to communicate with people who have SIP accounts with a public Internet connectivity provider such as MSN. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePublicCloudAudioVideoAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to conduct audio/video conversations with people who have SIP accounts with a public Internet connectivity provider such as MSN. When set to False, audio and video options in Lync will be disabled any time a user is communicating with a public Internet connectivity contact. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableXmppAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to communicate with users who have SIP accounts with a federated XMPP (Extensible Messaging and Presence Protocol ) partner. The default value is False.</p></td>
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
<td><p>Unique identifier for the external access policy to be modified. External access policies can be configured at the global, site, or per-user scopes. To modify the global policy, use this syntax: -Identity global. To modify a site policy, use syntax similar to this: -Identity site:Redmond. To modify a per-user policy, use syntax similar to this: -Identity SalesAccessPolicy. If this parameter is not specified then the global policy will be modified.</p>
<p>Note that wildcards are not allowed when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>ExternalAccessPolicyObject</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.ExternalAccess.ExternalAccessPolicy object. The **Set-CsExternalAccessPolicy** cmdlet accepts pipelined input of the external access policy object.

## Return Types

The **Set-CsExternalAccessPolicy** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ExternalAccess.ExternalAccessPolicy object.

## 另请参阅

#### 其他资源

[Get-CsExternalAccessPolicy](get-csexternalaccesspolicy.md)  
[Grant-CsExternalAccessPolicy](grant-csexternalaccesspolicy.md)  
[New-CsExternalAccessPolicy](new-csexternalaccesspolicy.md)  
[Remove-CsExternalAccessPolicy](remove-csexternalaccesspolicy.md)

