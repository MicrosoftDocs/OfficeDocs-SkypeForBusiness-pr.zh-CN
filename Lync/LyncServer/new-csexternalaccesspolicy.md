---
title: New-CsExternalAccessPolicy
TOCTitle: New-CsExternalAccessPolicy
ms:assetid: 624a878e-6bbf-4e8b-9a5e-e7b5521fa4c1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398441(v=OCS.15)
ms:contentKeyID: 49313041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsExternalAccessPolicy

 

_**上一次修改主题：** 2015-03-09_

Enables you to create a new external access policy. External access policies determine whether or not your users can: 1) communicate with users who have Session Initiation Protocol (SIP) accounts with a federated organization; 2) communicate with users who have SIP accounts with a public instant messaging (IM) provider such as MSN; and, 3) access Lync Server over the Internet, without having to log on to your internal network. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsExternalAccessPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnableFederationAccess <$true | $false>] [-EnableOutsideAccess <$true | $false>] [-EnablePublicCloudAccess <$true | $false>] [-EnablePublicCloudAudioVideoAccess <$true | $false>] [-EnableXmppAccess <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new external access policy that has the Identity site:Redmond; upon creation, this policy will automatically be assigned to the Redmond site. Note that this new policy sets both the EnableFederationAccess and the EnableOutsideAccess properties to True.

    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $True -EnableOutsideAccess $True

## EXAMPLE 2

Example 2 demonstrates the use of the InMemory parameter; this parameter enables you to create an in-memory-only instance of an external access policy. After it has been created, you can modify the in-memory-only instance, then use the **Set-CsExternalAccessPolicy** cmdlet to transform the virtual policy into a real external access policy.

To do this, the first command in the example uses the **New-CsExternalAccessPolicy** cmdlet and the InMemory parameter to create a virtual policy with the Identity RedmondAccessPolicy; this virtual policy is stored in a variable named $x. The next three commands are used to modify three properties of the virtual policy: EnableFederationAccess, EnablePublicCloudAccess, and the EnableOutsideAccess. Finally, the last command uses the **Set-CsExternalAccessPolicy** cmdlet to create an actual per-user external access policy with the Identity RedmondAccessPolicy. If you do not call the **Set-CsExternalAccessPolicy** cmdlet, then the virtual policy will disappear as soon as you end your Windows PowerShell session or delete the variable $x. Should that happen, an external access policy with the Identity RedmondAccessPolicy will never be created.

``` 
$x = New-CsExternalAccessPolicy -Identity RedmondAccessPolicy -InMemory
$x.EnableFederationAccess = $True
$x.EnablePublicCloudAccess = $True
$x.EnableOutsideAccess = $True
Set-CsExternalAccessPolicy -Instance $x  
```

## Detailed Description

When you install Lync Server your users are only allowed to exchange instant messages and presence information among themselves: by default, they can only communicate with other people who have SIP accounts in your Active Directory 域服务. In addition, users are not allowed to access Lync Server over the Internet; instead, they must be logged on to your internal network before they will be able to log on to Lync Server.

That might be sufficient to meet your communication needs. If it doesn’t meet your needs you can use external access policies to extend the ability of your users to communicate and collaborate. External access policies can grant (or revoke) the ability of your users to do any or all of the following:

1\. Communicate with people who have SIP accounts with a federated organization. Note that enabling federation alone will not provide users with this capability. Instead, you must enable federation and then assign users an external access policy that gives them the right to communicate with federated users.

2\. Communicate with people who have SIP accounts with a public instant messaging service such as MSN.

3\. Access Lync Server over the Internet, without having to first log on to your internal network. This enables your users to use Lync Server and log on to Lync Server from an Internet café or other remote location.

When you install Lync Server, a global external access policy is automatically created for you. In addition to the global policy, you can also create custom external access policies at either the site or the per-user scope. If you create an external access policy at the site scope, that policy will automatically be assigned to the site upon creation. If you create an external access policy at the per-user scope, that policy will be created but will not be assigned to any users. To assign the policy to a user or group of users, use the **Grant-CsExternalAccessPolicy** cmdlet.

New external access policies can be created by using the **New-CsExternalAccessPolicy** cmdlet. Note that these policies can only be created at the site or the per-user scope; you cannot create a new policy at the global scope. In addition, you can have only one external access policy per site: if the Redmond site already has been assigned an external access policy you cannot create a second policy for the site.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsExternalAccessPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

    Get-CsAdminRole | Where-Object  {$_.Cmdlets -match "New-CsExternalAccessPolicy"}

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
<td><p>Unique Identity to be assigned to the policy. New external access policies can be created at the site or per-user scope. To create a new site policy, use the prefix &quot;site:&quot; and the name of the site as your Identity. For example, use this syntax to create a new policy for the Redmond site: -Identity site:Redmond. To create a new per-user policy, use an Identity similar to this: -Identity SalesAccessPolicy.</p>
<p>Note that you cannot create a new global policy; if you want to make changes to the global policy, use the <strong>Set-CsExternalAccessPolicy</strong> cmdlet instead. Likewise, you cannot create a new site or per-user policy if a policy with that Identity already exists. If you need to make changes to an existing policy, use the <strong>Set-CsExternalAccessPolicy</strong> cmdlet.</p></td>
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
<td><p>Enables administrators to provide explanatory text to accompany the policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableFederationAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to communicate with people who have SIP accounts with a federated organization. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableOutsideAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to connect to Lync Server over the Internet, without logging on to the organization’s internal network. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePublicCloudAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to communicate with people who have SIP accounts with a public Internet connectivity provider such as MSN. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePublicCloudAudioVideoAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to conduct audio/video conversations with people who have SIP accounts with a public Internet connectivity provider such as MSN. When set to False, audio and video options in Lync Server will be disabled any time a user is communicating with a public Internet connectivity contact.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableXmppAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the user is allowed to communicate with users who have SIP accounts with a federated XMPP (Extensible Messaging and Presence Protocol ) partner. The default value is False.</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsExternalAccessPolicy** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ExternalAccess.ExternalAccessPolicy object.

## 另请参阅

#### 其他资源

[Get-CsExternalAccessPolicy](get-csexternalaccesspolicy.md)  
[Grant-CsExternalAccessPolicy](grant-csexternalaccesspolicy.md)  
[Remove-CsExternalAccessPolicy](remove-csexternalaccesspolicy.md)  
[Set-CsExternalAccessPolicy](set-csexternalaccesspolicy.md)

