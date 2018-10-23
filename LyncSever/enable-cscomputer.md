---
title: Enable-CsComputer
TOCTitle: Enable-CsComputer
ms:assetid: ac014030-4cd0-4503-b70e-12ab5b0ec34b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412815(v=OCS.15)
ms:contentKeyID: 49313928
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsComputer

 

_**上一次修改主题：** 2015-03-09_

Enables new or newly-updated services or server roles on a computer running Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsComputer [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 activates any new Lync Server services or server roles that have been installed on the local computer.

    Enable-CsComputer

## EXAMPLE 2

Example 2 also activates any new Lync Server services or server roles that have been installed on the local computer. In this case, however, the addition of the Verbose parameter ensures that a step-by-step account of the tasks being carried out by the **Enable-CsComputer** cmdlet will be reported on the screen.

    Enable-CsComputer -Verbose

## Detailed Description

Installing the required software does not automatically cause a computer to adopt a new service role; instead, that computer must be enabled before it actually begins to function in its new role. The **Enable-CsComputer** cmdlet provides a way for administrators to enable newly updated services or server roles on the local computer.

Who can run this cmdlet: You must be a local administrator and a member of the domain in order to run the **Enable-CsComputer** cmdlet locally.

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
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of a global catalog server in your domain. This parameter is not required if you are running the <strong>Enable-CsComputer</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\EnableComputer.html&quot;</p></td>
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

None. The **Enable-CsComputer** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Enable-CsComputer** cmdlet enables instances of the Microsoft.Rtc.Management.Deploy.Internal.Machine object.

## 另请参阅

#### 其他资源

[Disable-CsComputer](disable-cscomputer.md)  
[Get-CsComputer](get-cscomputer.md)  
[Test-CsComputer](test-cscomputer.md)

