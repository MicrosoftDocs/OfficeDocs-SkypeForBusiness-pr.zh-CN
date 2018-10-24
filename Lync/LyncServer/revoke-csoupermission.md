---
title: Revoke-CsOUPermission
TOCTitle: Revoke-CsOUPermission
ms:assetid: de0542c9-6d11-4038-9b4a-757338d61fae
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398977(v=OCS.15)
ms:contentKeyID: 49314465
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Revoke-CsOUPermission

 

_**上一次修改主题：** 2015-03-09_

Revokes the Lync Server management permissions that have been granted on an Active Directory organizational unit (OU). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Revoke-CsOUPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <String> [-Confirm [<SwitchParameter>]] [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 revokes user management permissions (-ObjectType "user") for the Redmond OU in the domain litwareinc.com.

    Revoke-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

## EXAMPLE 2

In Example 2, three different management permissions (user, contact, and inetOrgPerson objects) are removed from the Redmond OU in the domain litwareinc.com.

    Revoke-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user","contact","inetOrgPerson"

## Detailed Description

If you have locked down your Active Directory domain (that is, if you have disabled permission inheritance) then the domain preparation that takes place when you install Lync Server will not be able to add the permissions needed to manage users, computers, contacts, application contacts, and InetOrg persons. (Enterprise administrators and domain administrators will still be able to manage these objects, but no one else, including members of the RTCUniversalServerAdmins group, will have management permissions.) In that case, you will need to use the **Grant-CsOUPermission** cmdlet to grant the required security groups the required permissions. This must be done on a container-by-container basis for each Active Directory container that includes Lync Server user accounts.

Permissions granted by using the **Grant-CsOUPermission** cmdlet can later be removed by using **Revoke-CsOUPermission**. If you run the **Revoke-CsOUPermission** cmdlet against an OU you will then need to be an enterprise administrator or a domain administrator in order to manage Lync Server users in that OU.

Who can run this cmdlet: You must be a domain administrator in order to run the **Revoke-CsOUPermission** cmdlet locally. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Revoke-CsOUPermission"}

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
<td><p><em>ObjectType</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.ObjectType</p></td>
<td><p>Type of object covered by these permissions. Valid values are:</p>
<p>User</p>
<p>Computer</p>
<p>Contact</p>
<p>AppContact</p>
<p>InetOrgPerson</p>
<p>To revoke permissions to multiple object types in the same command, separate the object types by using commas: -ObjectType &quot;user&quot;,&quot;computer&quot;,&quot;contact&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Distinguished name of the OU where permissions are to be removed. For example: -OU &quot;ou=Redmond,dc=litwareinc,dc=com&quot;.You can only remove permissions from a single OU per command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Domain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Name of the domain where the OU is located. If this parameter is not included the <strong>Revoke-CsOUPermission</strong> cmdlet will look for the OU in the current domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the fully qualified domain name (FQDN) of the domain controller to be used when running the <strong>Revoke-CsOUPermission</strong> cmdlet. If not specified, the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of a global catalog server in your domain. This parameter is not required if you are running the <strong>Revoke-CsOUPermission</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\OUPermissions.html&quot;</p></td>
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

None. The **Revoke-CsOUPermission** cmdlet does not accept pipelined input.

## Return Types

The **Revoke-CsOUPermission** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Grant-CsOUPermission](grant-csoupermission.md)  
[Test-CsOUPermission](test-csoupermission.md)

