---
title: Grant-CsSetupPermission
TOCTitle: Grant-CsSetupPermission
ms:assetid: 753bccc1-edb4-48c9-bd0a-2db5d86f8c5e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398569(v=OCS.15)
ms:contentKeyID: 49313271
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsSetupPermission

 

_**上一次修改主题：** 2015-03-09_

Grants Lync Server setup permissions on an Active Directory organizational unit (OU). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsSetupPermission -ComputerOU <String> [-Confirm [<SwitchParameter>]] [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 grants setup permissions for the CsServers OU in the domain litwareinc.com.

    Grant-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

## Detailed Description

The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** cmdlet. That means that, by default, you must be a domain administrator in order to enable a topology. To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the **Grant-CsSetupPermissions** cmdlet. In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.

Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.

Who can run this cmdlet: You must be a domain administrator in order to run the **Grant-CsSetupPermission** cmdlet locally. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsSetupPermission"}

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
<td><p>Distinguished name of the OU containing the accounts for the computers where Lync Server will be (or has been) installed. For example: &quot;ou=CsServers,dc=litwareinc,dc=com&quot;.</p>
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
<td><p>Name of the domain where the OU is located. If this parameter is not included, then the <strong>Grant-CsSetupPermission</strong> cmdlet will look for the OU in the current domain.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified name of the domain controller to be contacted when assigning the policy. For example: -DomainController atl-dc-001.litwareinc.com.</p>
<p>If not specified, the <strong>Grant-CsSetupPermission</strong> cmdlet will contact the nearest available domain controller when assigning the policy.</p></td>
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
<p>If not specified, the <strong>Grant-CsSetupPermission</strong> cmdlet will contact the nearest available global catalog server when assigning the policy.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\SetupPermissions.html&quot;</p></td>
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

None. The **Grant-CsSetupPermission** cmdlet does not accept pipelined input.

## Return Types

None. The **Grant-CsSetupPermission** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Revoke-CsSetupPermission](revoke-cssetuppermission.md)  
[Test-CsSetupPermission](test-cssetuppermission.md)

