---
title: Grant-CsOUPermission
TOCTitle: Grant-CsOUPermission
ms:assetid: 26d8bdbf-abf0-4ca3-b9ab-fbb355fbcca1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425739(v=OCS.15)
ms:contentKeyID: 49312294
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsOUPermission

 

_**上一次修改主题：** 2015-03-09_

Grants Lync Server management rights on an Active Directory organizational unit (OU). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsOUPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <String> [-Confirm [<SwitchParameter>]] [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 grants user management rights (-ObjectType "user") to the Redmond OU in the domain litwareinc.com.

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

## EXAMPLE 2

In Example 2, management rights are granted for three different objects (user, contact, inetOrgPerson) for the Redmond OU in the domain litwareinc.com.

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user","contact","inetOrgPerson"

## EXAMPLE 3

In Example 3, user management rights are simultaneously granted for three different OUs: Redmond, Dublin, and Tokyo. To carry out this task, the first command in the example creates an array variable named $x; this variable holds the distinguished names of the three Active Directory OUs where rights will be granted. In the second command, a foreach loop is created that takes each OU stored in the array and runs the **Grant-CsOUPermission** cmdlet against that organizational unit. In turn, that command grants user management rights for each OU in the array.

    $x = "ou=Redmond,dc=litwareinc,dc=com", "ou=Dublin,dc=litwareinc,dc=com", "ou=Tokyo,dc=litwareinc,dc=com"
    
    foreach ($i in $x) {Grant-CsOUPermission -OU $i -ObjectType "user"}

## Detailed Description

If you have locked down your Active Directory domain (that is, if you have disabled permission inheritance) then the domain preparation that takes place when you install Lync Server will not be able to add the rights needed to manage users, computers, contacts, application contacts, and InetOrg persons. (Domain administrators will still be able to manage these objects, but no one else, including members of the RTCUniversalUserAdmins group, will have management rights.) In that case, you will need to use the **Grant-CsOUPermission** cmdlet to give the required security groups the required rights. This must be done on a container-by-container basis.

Note that this cmdlet only grants rights to a set of predefined security groups; the cmdlet cannot be used to grant rights to arbitrary security groups or to individual users.

Rights granted by using the **Grant-CsOUPermission** cmdlet can later be removed by using the **Revoke-CsOUPermission** cmdlet. If you run that cmdlet, then the groups initially granted the OU rights will no longer have those Lync Server management rights for the specified Active Directory container. In that case, you will need to be an enterprise administrator or a domain administrator in order to manage Lync Server or one of its components.

Who can run this cmdlet: You must be a domain administrator in order to run the **Grant-CsOUPermission** cmdlet locally. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsOUPermission"}

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
<td><p>Type of object covered by these rights. Valid values are:</p>
<p>User</p>
<p>Computer</p>
<p>Contact</p>
<p>AppContact</p>
<p>InetOrgPerson</p>
<p>Device (required for creating common area phones)</p>
<p>To assign multiple object types in the same command, separate the object types by using commas: -ObjectType &quot;user&quot;,&quot;computer&quot;,&quot;contact&quot;. Note, however, that you can only specify a maximum of three object types per command.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Distinguished name of the OU where rights are to be granted. For example: -OU &quot;ou=Redmond,dc=litwareinc,dc=com&quot;.Note that you can only grant rights to a single OU per command.</p></td>
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
<td><p>Name of the domain where the OU is located. If this parameter is not included, then the <strong>Grant-CsOUPermission</strong> cmdlet will look for the OU on the current domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the fully qualified domain name (FQDN) of the domain controller to be used when running the <strong>Grant-CsOUPermission</strong> cmdlet. If not specified, the cmdlet will use the first available domain controller.</p></td>
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
<td><p>FQDN of a global catalog server in your domain. This parameter is not required if you are running the <strong>Grant-CsOUPermission</strong> cmdlet on a computer with an account in your domain.</p></td>
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

None. The **Grant-CsOUPermission** cmdlet does not accept pipelined input.

## Return Types

The **Grant-CsOUPermission** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Revoke-CsOUPermission](revoke-csoupermission.md)  
[Test-CsOUPermission](test-csoupermission.md)

