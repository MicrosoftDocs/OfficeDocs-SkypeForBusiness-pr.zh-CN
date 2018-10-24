---
title: New-CsVoiceRoute
TOCTitle: New-CsVoiceRoute
ms:assetid: 1118f74f-b06c-41d2-8b1b-5cc1e1957b77
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398197(v=OCS.15)
ms:contentKeyID: 49312036
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsVoiceRoute

 

_**上一次修改主题：** 2015-03-09_

Creates a new voice route. Voice routes contain instructions that tell Lync Server how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsVoiceRoute -Name <String> <COMMON PARAMETERS>

    New-CsVoiceRoute -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AlternateCallerId <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-NumberPattern <String>] [-Priority <Int32>] [-PstnGatewayList <PSListModifier>] [-PstnUsages <PSListModifier>] [-SuppressCallerId <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command in this example creates a new voice route with an Identity of Route1. All other properties will be set to the default values.

    New-CsVoiceRoute -Identity Route1

## EXAMPLE 2

The command in this example creates a new voice route with an Identity of Route1. It also adds the PSTN usage Long Distance to the list of usages and the service ID PstnGateway:redmondpool.litwareinc.com to the list of PSTN gateways.

    New-CsVoiceRoute -Identity Route1 -PstnUsages @{add="Long Distance"} -PstnGatewayList @{add="PstnGateway:redmondpool.litwareinc.com"}

## EXAMPLE 3

This example creates a new voice route named Route1 and populates that route’s list of PSTN usages with all the existing usages for the organization. The first command in this example retrieves the list of global PSTN usages. Notice that the call to the **Get-CsPstnUsage** cmdlet is in parentheses; this means that we first retrieve an object containing PSTN usage information. (Because there is only one, global, PSTN usage, only one object will be retrieved.) The command then retrieves the Usage property of this object. That property, which contains a list of usages, is assigned to the variable $x. In the second line of this example, the **New-CsVoiceRoute** cmdlet is called to create a new voice route. This voice route will have an identity of Route1. Notice the value passed to the PstnUsages parameter: @{add=$x}. This value says to add the contents of $x, which contain the phone usages list retrieved in line 1, to the list of PSTN usages for this route.

    $x = (Get-CsPstnUsage).Usage
    New-CsVoiceRoute -Identity Route1 -PstnUsages @{add=$x}

## Detailed Description

Use this cmdlet to create a new voice route. All voice routes are created at the Global scope. However, multiple global voice routes can be defined. This is accomplished through the Identity parameter, which requires a unique route name.

Voice routes are associated with voice policies through PSTN usages. A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route: phone numbers matching the regular expression will be routed through this route.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsVoiceRoute** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsVoiceRoute"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>A name that uniquely identifies the voice route. Voice routes can be defined only at the global scope, so the identity is simply the name you want to give the route. (You can have spaces in the route name, for instance Test Route, but you must enclose the full string in double quotes in the call to the <strong>New-CsVoiceRoute</strong> cmdlet.)</p>
<p>If Identity is specified, the Name must be left blank. The value of the Identity will be assigned to the Name.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The unique name of the voice route. If this parameter is set, the value will be automatically applied to the voice route Identity. You cannot specify both an Identity and a Name.</p></td>
</tr>
<tr class="odd">
<td><p><em>AlternateCallerId</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>If the SuppressCallerId parameter is set to True, the value of the AlternateCallerId parameter will be displayed to receiving parties rather than the caller’s actual number. This number should be a valid number and could be used to represent a division within an organization, such as Support or Human Resources.</p>
<p>If the SuppressCallerId parameter is set to False, the AlternateCallerId parameter is ignored.</p>
<p>This value must match the regular expression (\+)?[1-9]\d*(;ext=[1-9]\d*)?. In other words, the value can begin with a plus sign (+) but doesn’t need to; must consist of any number of digits; and may be followed by an extension that begins with ;ext= followed by any number of digits. (Note that if you include an extension the string must be placed within double quotes.)</p></td>
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
<td><p>A description of what this voice route is for.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>NumberPattern</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A regular expression that specifies the phone numbers to which this route applies. Numbers matching this pattern will be routed according to the rest of the routing settings.</p>
<p>Default: [0-9]{10}</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>A number could resolve to multiple voice routes. The priority determines the order in which the routes will be applied if more than one route is possible.</p></td>
</tr>
<tr class="even">
<td><p><em>PstnGatewayList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>In Lync Server a 中介服务器 can be associated with multiple gateways. This parameter contains a list of gateways associated with this voice route. Each member of this list must be the service Identity of the PSTN gateway or 中介服务器. The value can refer to a 中介服务器 only if the 中介服务器 is configured for Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2. For Lync Server, a PSTN gateway must be used. The service Identity is a string in the format &lt;ServiceRole&gt;:&lt;FQDN&gt;, where ServiceRole is the name of the service role (PSTNGateway), and FQDN is the fully qualified domain name (FQDN) of the pool or the IP address of the server. For example, PSTNGateway:redmondpool.litwareinc.com. Service identities can be retrieved by calling the command Get-CsService | Select-Object Identity.</p>
<p>By default this list is empty. However, if you leave this parameter blank when creating a new voice route, you’ll receive a warning message.</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnUsages</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>A list of PSTN usages (such as Local, Long Distance, etc.) that can be applied to this voice route. The PSTN usage must be an existing usage. (PSTN usages can be retrieved by calling the <strong>Get-CsPstnUsage</strong> cmdlet.)</p>
<p>By default this list is empty. However, if you leave this parameter blank when creating a new voice route, you’ll receive a warning message.</p></td>
</tr>
<tr class="even">
<td><p><em>SuppressCallerId</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether a caller’s ID will be revealed on outbound calls. If this parameter is set to True, caller ID will be suppressed. In place of the actual ID, the value of the AlternateCallerId will be displayed. When SuppressCallerId is set to True, a value for AlternateCallerId must be supplied.</p></td>
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

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route.

## 另请参阅

#### 其他资源

[Remove-CsVoiceRoute](remove-csvoiceroute.md)  
[Set-CsVoiceRoute](set-csvoiceroute.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)  
[Test-CsVoiceRoute](test-csvoiceroute.md)  
[Get-CsPstnUsage](get-cspstnusage.md)  
[Get-CsService](get-csservice.md)

