﻿---
title: Get-CsSipResponseCodeTranslationRule
TOCTitle: Get-CsSipResponseCodeTranslationRule
ms:assetid: 075e9e85-8f85-402c-9256-4e73ec93f96b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398130(v=OCS.15)
ms:contentKeyID: 49311898
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsSipResponseCodeTranslationRule

 

_**上一次修改主题：** 2015-03-09_

Returns information about SIP response code translation rules. These rules enable administrators to map SIP response codes with values between 400 and 699 to the values used by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsSipResponseCodeTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsSipResponseCodeTranslationRule [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the response code translation rules configured for use in your organization. This is done by calling the **Get-CsSipResponseCodeTranslationRule** cmdlet without any parameters.

    Get-CsSipResponseCodeTranslationRule

## EXAMPLE 2

Example 2 returns a single response code translation rule: the rule with the Identity PstnGateway:192.168.0.240/Rule404.

    Get-CsSipResponseCodeTranslationRule -Identity "PstnGateway:192.168.0.240/Rule404"

## EXAMPLE 3

In Example 3, the Filter parameter is used to limit the returned data to all the response code translation rules configured at the site scope. The filter value "site:\*" limits the returned data to rules that have an Identity that begins with the string value "site:".

    Get-CsSipResponseCodeTranslationRule -Filter "site:*"

## EXAMPLE 4

The command shown in Example 4 returns a collection of all the response code translation rules where no value has been configured for the ReceivedISUPCauseValue property. To do this, the command first calls the **Get-CsSipResponseCodeTranslationRule** cmdlet without any parameters in order to return a collection of all the response code translation rules currently in use. That collection is then piped to the **Where-Object** cmdlet, which picks out only those rules where the ReceivedISUPCauseValue property is equal to -1.

    Get-CsSipResponseCodeTranslationRule | Where-Object {$_.ReceivedISUPCauseValue -eq -1}

## Detailed Description

SIP trunking provides a way to connect a Voice over Internet Protocol (VoIP) network (such as Enterprise Voice) with the public switched telephone network (PSTN). In Lync Server, the 中介服务器 uses trunking peers to interact with the PSTN network. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call. When a 中介服务器 trunking peer receives that ISUP cause code, it converts the code to a SIP response code, which is then sent to the 中介服务器 itself. In turn, Lync Server uses these response codes to make its outbound routing decisions. For example, a malfunctioning gateway might automatically be assigned a "less-preferred" status; this minimizes the use of the malfunctioning gateway, and thus maximizes the chance of a call being successfully completed.

However, not all gateways use the recommended ISUP cause code to SIP response code mapping used by Lync Server. For these gateways, administrators can use the **CsSipResponseCodeTranslationRule** cmdlets to map the gateway SIP response code (in combination with the ISUP cause code, if that code is available) to a SIP response code used by Lync Server. For example, a gateway might map ISUP cause code 34 ("No circuit/channel is available") to SIP response code 486 ("Busy here"). Based on a response code of 486, the outbound routing logic of Lync Server will not attempt to find a new gateway in order to complete the call.

For Lync Server, however, that SIP response code of 486 should instead be mapped to SIP response code 503. A response code of 503 triggers the retry mechanism in the outbound routing logic of Lync Server; that means that the system will try to find another gateway in order to complete the call. To handle this situation, you can create a translation rule that maps the combination of ISUP cause code 34 and SIP response code 486 to a SIP response code of 503.

The **Get-CsSipResponseCodeTranslationRule** cmdlet enables you to retrieve information about all the translation rules configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsSipResponseCodeTranslationRule** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsSipResponseCodeTranslationRule"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcards when specifying the translation rule (or rules) to be returned. For example, this syntax returns all the translation rules that have the string value &quot;404&quot; in their Identity:</p>
<p>-Filter &quot;*404*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the translation rule. The identity for a translation rule consists of two parts: the scope where the rule was configured, and the name given to the rule when it was created. For example, a translation rule named Rule404 that was created at the global scope would have an Identity that looked like this: global/Rule404.</p>
<p>In addition to the global scope, translation rules can also be created at the site scope or the service scope (albeit for the PstnGateway service only).</p>
<p>To return all the translation rules created for a particular site or service, you can simply specify the site or service Identity. For example:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>If this parameter is omitted, the <strong>Get-CsSipResponseCodeTranslationRule</strong> cmdlet returns a collection of all your SIP response code translation rules.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the SIP response code translation rule data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsSipResponseCodeTranslationRule** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsSipResponseCodeTranslationRule** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.SipResponseCodeTRanslationRule\#Decorated object.

## 另请参阅

#### 其他资源

[New-CsSipResponseCodeTranslationRule](new-cssipresponsecodetranslationrule.md)  
[Remove-CsSipResponseCodeTranslationRule](remove-cssipresponsecodetranslationrule.md)  
[Set-CsSipResponseCodeTranslationRule](set-cssipresponsecodetranslationrule.md)

