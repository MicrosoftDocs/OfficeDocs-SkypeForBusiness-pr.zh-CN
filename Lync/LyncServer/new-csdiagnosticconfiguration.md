---
title: New-CsDiagnosticConfiguration
TOCTitle: New-CsDiagnosticConfiguration
ms:assetid: 9028d9c1-e812-4055-bdf0-59cb83c6f50f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398733(v=OCS.15)
ms:contentKeyID: 49313593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDiagnosticConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates new diagnostic configuration settings. Diagnostic configuration settings are used to determine whether traffic to or from a given domain or Uniform Resource Identifier (URI) is recorded in your Lync Server log files. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDiagnosticConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Filter <Filter>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LogAllSipHeaders <$true | $false>] [-LoggingShare <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new collection of diagnostic configuration settings for the Redmond site.

    New-CsDiagnosticConfiguration -Identity site:Redmond

## EXAMPLE 2

The commands shown in Example 2 create a new diagnostics filter and then assign that filter to a new collection of diagnostic settings. To carry out this task, the first command calls the **New-CsDiagnosticsFilter** cmdlet to create an in-memory-only diagnostics filter; this command adds the FQDN fabrikam.com and the URI sip:user@fabrikam.com to the filter. The command also sets the Enabled property to True ($True) in order to activate the filter. The resulting virtual filter is then stored in the variable $x.

In command 2, the **New-CsDiagnosticConfiguration** cmdlet is used to create a new diagnostic configuration settings collection for the Redmond site. These new settings will use the diagnostic filter stored in the variable $x.

    $x = New-CsDiagnosticsFilter -Fqdn fabrikam.com -Uri "sip:user@fabrikam.com" -Enabled $False 
    
    New-CsDiagnosticConfiguration -Identity site:Redmond -Filter $x

## EXAMPLE 3

The commands shown in Example 3 demonstrate how you can create diagnostic configuration settings that initially exist only in memory. To do this, the first command calls the **New-CsDiagnosticConfiguration** cmdlet along with two parameters: Identity (which specifies the Identity for the settings) and InMemory, which indicates that the new settings should be created in memory only. The resulting object is stored in the variable $x.

After the virtual settings have been created, the second command is used to configure the LoggingShare property to the UNC path \\\\atl-fs-001\\logs. The final command is then used to transform the virtual diagnostic configuration settings into an actual collection of settings applied to the Redmond site. Note that this final command is mandatory. If you do not call the **Set-CsDiagnosticConfiguration** cmdlet, no settings will be applied to the Redmond site, and the virtual settings will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsDiagnosticConfiguration -Identity site:Redmond -InMemory
    $x.LoggingShare = "\\atl-fs-001\logs"
    Set-CsDiagnosticConfiguration -Instance $x

## Detailed Description

If you enable logging for Lync Server then, by default, traffic traveling to or from any domain or URI is included in those log files. This ensures that as much information as possible is recorded in the log files.

However, this can occasionally result in too much information. For example, if you are experiencing connectivity problems with a particular domain, you might want to limit logging to traffic between your network and that domain; that makes it easier for you to identify the relevant records and, in turn, might make it easier for you to diagnose and correct the problem.

Diagnostic configuration settings make it possible for you to specify the domains or URIs that will be recorded in the log files; for example, you can log only the traffic to or from specified domains. Lync Server enables you to create diagnostic configuration settings at the site scope. In turn, this enables you to apply different settings to, say, the Redmond site than you do on your other sites.

Note that you cannot create diagnostic configuration settings at the global scope; that’s because the global scope already hosts these settings. Likewise, you cannot create a new settings collection at the site scope if the specified site already contains diagnostic configuration settings. For example, your command will fail if you try to create a new collection for the Redmond site and that site already hosts diagnostic configuration settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsDiagnosticConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDiagnosticConfiguration"}

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
<td><p>Unique identifier for the diagnostics configuration settings to be created. Because new settings can only be created at the site scope you must use syntax similar to this: -Identity &quot;site:Redmond&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.Filter</p></td>
<td><p>Collection of domains and URIs whose traffic will be logged if diagnostic filtering is enabled. The Filter property consists of three separate items:</p>
<p>Fqdn – Collection of domains to be included in the filter. (More technically, this is the host portion of a SIP address.) For example a fully qualified domain name (FQDN) might look like this: fabrikam.com. Alternatively, you can use wildcards to represent multiple domains: *.fabrikam.com. You can include more than one domain in a single filter.</p>
<p>Uri – Collection of URIs to be included in the filter. (The Uri is the user@host portion of a SIP address.) A Uri can consist of any of the following patterns: user@fabrikam.com; user@*; *@fabrikam.com. You can include multiple URIs in a single filter.</p>
<p>Enabled – Indicates whether or not the filter should be activated.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>LogAllSipHeaders</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to False, only the core SIP headers are recorded in the logs. Setting this value to False can help reduce the size of the log files. When set to True, all SIP headers are logged.</p></td>
</tr>
<tr class="odd">
<td><p><em>LoggingShare</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Shared folder where the diagnostic logs can be uploaded.</p></td>
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

None. The **New-CsDiagnosticConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsDiagnosticConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticFilterSettings.

## 另请参阅

#### 其他资源

[Get-CsDiagnosticConfiguration](get-csdiagnosticconfiguration.md)  
[New-CsDiagnosticsFilter](new-csdiagnosticsfilter.md)  
[Remove-CsDiagnosticConfiguration](remove-csdiagnosticconfiguration.md)  
[Set-CsDiagnosticConfiguration](set-csdiagnosticconfiguration.md)

