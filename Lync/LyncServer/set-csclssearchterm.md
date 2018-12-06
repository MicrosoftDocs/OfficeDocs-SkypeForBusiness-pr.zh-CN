---
title: Set-CsClsSearchTerm
TOCTitle: Set-CsClsSearchTerm
ms:assetid: 57ccaf25-31ab-4059-8dc4-144f29f3af68
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204911(v=OCS.15)
ms:contentKeyID: 49312919
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClsSearchTerm

 

_**上一次修改主题：** 2015-03-09_

Modifies one or more centralized logging search terms. Search terms help define the personally identifiable information available to technical support personnel who are searching the centralized trace logs. Search terms are intended for use with Skype for Business Online.

此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsClsSearchTerm [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClsSearchTerm [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Inserts <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in sets the Inserts property for the search term "site:Redmond/IP". In this example, a single Insert is configured: ItemURI.

    Set-CsClsSearchTerm -Identity "site:Redmond/IP" -Inserts "ItemURI"

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

In Skype for Business Online, administrators can use search terms to mask personally identifiable information from support personnel who are viewing the log files. For example, a user’s name, such as Ken Myer, would not appear when viewed using the support console; instead, the name might appear as FIRST1 LAST1. Likewise, the phone number +12065551219 might be displayed as PHONE1.

The **Set-CsClsSearchTerm** cmdlet enables you to modify any of the search terms currently assigned to a collection of centralized logging configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClsSearchTerm"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsClsSearchTerm** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Prompts you for confirmation before executing the command.</p></td>
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
<td><p>Unique identifier of the search term to be modified. A search term consists of two parts: the scope where the term is configured (that is, the collection of centralized logging configuration settings where the term can be found) and the term name. For example:</p>
<p>-Identity &quot;site:Redmond/CallID&quot;</p>
<p>You cannot use wildcards when specifying the Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Inserts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Specify how personally identifiable information is masked when viewing the log files. For example, the Insert &quot;ItemURI&quot; indicates that user URI information should be masked. As a result, a user URI such as sip:kenmyer@litwareinc.com will appear as a generic URI that hides the user name but preserve the domain name:</p>
<p>Sip:USER1@litwareinc.com</p>
<p>Inserts mask such things as user names and computer names; phone numbers; and IP addresses.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object rather than set individual parameter values.</p></td>
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

The **Set-CsClsSearchTerm** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.SearchTerm\#Decorated object.

## Return Types

None. Instead, the **Set-CsClsSearchTerm** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.SearchTerm\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsClsSearchTerm](get-csclssearchterm.md)

