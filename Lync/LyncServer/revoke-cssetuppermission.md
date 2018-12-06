---
title: Revoke-CsSetupPermission
TOCTitle: Revoke-CsSetupPermission
ms:assetid: 3486d164-b1a2-4d4c-9150-cef802674682
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425834(v=OCS.15)
ms:contentKeyID: 49312464
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Revoke-CsSetupPermission

 

_**上一次修改主题：** 2015-03-09_

Revokes the Lync Server setup rights that have been granted on an Active Directory organizational unit (OU). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Revoke-CsSetupPermission -ComputerOU <String> [-Confirm [<SwitchParameter>]] [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 revokes the setup rights applied to the CsServers OU in the domain litwareinc.com.

    Revoke-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

## Detailed Description

The domain preparation that takes place when you install Lync Server does not automatically add the rights that enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** cmdlet. That means that, by default, you must be a domain administrator in order to enable a topology. To give members of the RTCUniversalServerAdmins group the right to enable a topology, you must run the **Grant-CsSetupPermissions** cmdlet. In addition, you will need to run this cmdlet against each Active Directory container that hosts computers running Lync Server.

Rights granted by using the **Grant-CsSetupPermission** cmdlet can later be removed by using the **Revoke-CsSetupPermission** cmdlet. If you run that cmdlet, the RTCUniversalServerAdmins group will no longer have Lync Server setup rights for the specified Active Directory container. In that case, you will need to be an enterprise administrator or a domain administrator in order to enable a Lync Server topology.

Who can run this cmdlet: You must be a domain administrator in order to run the **Revoke-CsSetupPermission** cmdlet locally. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Revoke-CsSetupPermission"}

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
<td><p><em>ComputerOU</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Distinguished name (DN) of the OU that contains the accounts for the computers where Lync Server will be (or has been) installed. For example: -ComputerOU &quot;ou=CsServers,dc=litwareinc,dc=com&quot;.</p>
<p>If you prefer you can leave off the domain portion of the distinguished name when specifying the OU. For example:</p>
<p>-ComputerOU &quot;ou=CsServers&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Domain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Name of the domain where the OU is located. If this parameter is not included, then the <strong>Revoke-CsSetupPermission</strong> cmdlet will look for the OU in the current domain.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified name of the domain controller to be contacted when assigning the policy. For example: -DomainController atl-dc-001.litwareinc.com.</p>
<p>If not specified, the <strong>Revoke-CsSetupPermission</strong> cmdlet will contact the nearest available domain controller when assigning the policy.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified name of the global catalog server to be contacted when assigning the policy. For example: -GlobalCatalog atl-dc-001.litwareinc.com.</p>
<p>If not specified, the <strong>Revoke-CsSetupPermission</strong> cmdlet will contact the nearest available global catalog server when assigning the policy.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\OUPermissions.html&quot;</p></td>
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

None. The **Revoke-CsSetupPermission** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Grant-CsSetupPermission](grant-cssetuppermission.md)  
[Test-CsSetupPermission](test-cssetuppermission.md)

