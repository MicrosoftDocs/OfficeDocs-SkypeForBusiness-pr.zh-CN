---
title: Set-CsSipResponseCodeTranslationRule
TOCTitle: Set-CsSipResponseCodeTranslationRule
ms:assetid: 3ce2fafe-9c79-4462-9f24-c2a30502e641
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425895(v=OCS.15)
ms:contentKeyID: 49312570
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsSipResponseCodeTranslationRule

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing SIP response code translation rule. These rules enable administrators to map SIP response codes with values between 400 and 699 to the values used by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsSipResponseCodeTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsSipResponseCodeTranslationRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Priority <Int32>] [-ReceivedISUPCauseValue <Int32>] [-ReceivedResponseCode <Int32>] [-TranslatedResponseCode <Int32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the ReceivedISUPCauseValue property for the translation rule with the Identity PstnGateway:192.168.0.240/Rule404.

    Set-CsSipResponseCodeTranslationRule -Identity "PstnGateway:192.168.0.240/Rule404" -ReceivedISUPCauseValue 477

## EXAMPLE 2

In Example 2, the translation rule with the Identity PstnGateway:192.168.0.240/Rule404 is marked as the highest priority rule; that is, the rule that will be processed first. This is done by setting the Priority to 0.

    Set-CsSipResponseCodeTranslationRule -Identity "PstnGateway:192.168.0.240/Rule404" -Priority 0

## EXAMPLE 3

Example 3 shows how you can set the ReceivedISUPCauseValue property of all the translation rules configured for use in your organization to -1; that will cause the ISUP cause code to be ignored when translating rules. To do this the command first calls the **Get-CsSipResponseCodeTranslationRule** cmdlet without any parameters in order to return a collection of all the SIP response code translation rules currently in use. That collection is then piped to the **Set-CsSipResponseCodeTranslationRule** cmdlet, which modifies the ReceivedISUPCauseValue property for each item in the collection.

    Get-CsSipResponseCodeTranslationRule | Set-CsSipResponseCodeTranslationRule -ReceivedISUPCauseValue -1

## Detailed Description

SIP trunking provides a way to connect a Voice over Internet Protocol (VoIP) network (such as Enterprise Voice) with the public switched telephone network (PSTN). In Lync Server, the 中介服务器 uses trunking peers to interact with the PSTN network. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call. When a 中介服务器 trunking peer receives that ISUP cause code, it converts that code to a SIP response code, which is then sent to the 中介服务器 itself. In turn, Lync Server uses these response codes to make its outbound routing decisions. For example, a malfunctioning gateway might automatically be assigned a "less-preferred" status; this minimizes the use of the malfunctioning gateway, and thus maximizes the chance of a call being successfully completed.

However, not all gateways use the recommended ISUP cause code to SIP response code mapping used by Lync Server. For these gateways, administrators can use the **CsSipResponseCodeTranslationRule** cmdlets to map the gateway SIP response code (in combination with the ISUP cause code, if that code is available) to a SIP response code used by Lync Server. For example, a gateway might map ISUP cause code 34 ("No circuit/channel is available") to SIP response code 486 ("Busy here"). Based on a response code of 486, the outbound routing logic of Lync Server will not attempt to find a new gateway in order to complete the call.

For Lync Server, however, that SIP response code of 486 should instead be mapped to SIP response code 503. A response code of 503 triggers the retry mechanism in the outbound routing logic of Lync Server; that means that the system will try to find another gateway in order to complete the call. To handle this situation, you can create a translation rule that maps the combination of ISUP cause code 34 and SIP response code 486 to a SIP response code of 503.

The **Set-CsSipResponseCodeTranslationRule** cmdlet provides a way for you to modify any of the translation rules previously configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsSipResponseCodeTranslationRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsSipResponseCodeTranslationRule"}

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
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the translation rule to be modified. The Identity for a translation rule consists of two parts: the scope where the rule was configured, and the name given to the rule when it was created. For example, a translation rule named Rule404 that was created at the global scope would have an Identity that looked like this: global/Rule404.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Integer</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Relative priority of the translation rule. Rules are processed in order of their assigned priority; the first rule to be processed has a priority of 0; the second rule to be processed has a priority of 1; and so on.</p></td>
</tr>
<tr class="even">
<td><p><em>ReceivedISUPCauseValue</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Value of the ISDN User Part (ISUP) code that must be present in the SIP response message used by a gateway when responding to an INVITE message. A value of -1 indicates that only the SIP response code will be used when executing the translation rule; the ISUP cause code will be ignored.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReceivedResponseCode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Value of the SIP response code used by a gateway when responding to an INVITE message. A response code can be any integer value between 400 and 699, inclusive. Although the cmdlet will accept integer values less than 400, these are not recognized as final responses. As a result, the translation rule will never be used. A value of 0 means that only the ISUP cause code will be used when executing the translation rule; the SIP response code will be ignored.</p></td>
</tr>
<tr class="even">
<td><p><em>TranslatedResponseCode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Value of SIP response code that the ReceivedResponseCode and/or the ReceivedISUPCauseCode should be translated to. Translated response codes can be any integer value between 400 and 699, inclusive.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.SipResponseCodeTranslationRule\#Decorated object. The **Set-CsSipResponseCodeTranslationRule** cmdlet accepts pipelined instances of the SIP response code translation rule object.

## Return Types

The **Set-CsSipResponseCodeTranslationRule** cmdlet does not return any objects or values. Instead, the cmdlet modifies instances of the Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.SipResponseCodeTranslationRule\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsSipResponseCodeTranslationRule](get-cssipresponsecodetranslationrule.md)  
[New-CsSipResponseCodeTranslationRule](new-cssipresponsecodetranslationrule.md)  
[Remove-CsSipResponseCodeTranslationRule](remove-cssipresponsecodetranslationrule.md)

