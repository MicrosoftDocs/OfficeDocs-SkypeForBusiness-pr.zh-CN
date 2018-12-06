---
title: Set-CsTrustedApplicationEndpoint
TOCTitle: Set-CsTrustedApplicationEndpoint
ms:assetid: 6c2713f4-8e2c-48fc-9f27-07c1d6b87a18
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398509(v=OCS.15)
ms:contentKeyID: 49313154
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTrustedApplicationEndpoint

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing endpoint contact for a trusted application. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsTrustedApplicationEndpoint -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DisplayNumber <String>] [-Enabled <$true | $false>] [-EnabledForFederation <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-PrimaryLanguage <String>] [-SecondaryLanguages <MultiValuedProperty>] [-SipAddress <String>] [-Type <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example modifies the application endpoint contact object with the SIP address endpoint1@litwareinc.com. Notice that the Identity value begins with the string sip: followed by the SIP address. The next parameter, DisplayName, is given a value of “Endpoint 1”, which changes the display name of the contact to that value.

    Set-CsTrustedApplicationEndpoint -Identity "sip:endpoint1@litwareinc.com" -DisplayName "Endpoint 1"

## EXAMPLE 2

This example modifies the display number of the endpoint application with the display name Endpoint 1. The command begins with a call to the **Get-CsTrustedApplicationEndpoint** cmdlet with an Identity of Endpoint 1. This retrieves the endpoint contact object with that display name. This object is then piped to the **Set-CsTrustedApplicationEndpoint** cmdlet, which modifies the DisplayNumber to the value, in this case, (425)555-1212.

    Get-CsTrustedApplicationEndpoint -Identity "Endpoint 1" | Set-CsTrustedApplicationEndpoint -DisplayNumber "(425)555-1212"

## Detailed Description

A trusted application endpoint is an Active Directory contact object that enables routing of calls to a trusted application. This cmdlet modifies an existing endpoint contact object in Active Directory 域服务.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsTrustedApplicationEndpoint** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsTrustedApplicationEndpoint"}

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>The Identity (the distinguished name) or the SIP address of the application endpoint to be modified.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The display name of the endpoint contact object.</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The telephone number of the contact as it will appear in the Address Book.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether the contact is enabled for Lync Server.</p>
<p>Default: True</p></td>
</tr>
<tr class="even">
<td><p><em>EnabledForFederation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether federated users have access to this contact.</p>
<p>Default: False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether the contact is enabled for Enterprise Voice.</p>
<p>Default: True</p></td>
</tr>
<tr class="even">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>Indicates where the contact's instant messaging sessions are archived. Allowed values are:</p>
<p>* Uninitialized</p>
<p>* UseLyncArchivingPolicy</p>
<p>* ArchivingToExchange</p>
<p>* NoArchiving</p></td>
</tr>
<tr class="odd">
<td><p><em>LineURI</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The phone number of the contact. Must be in the format TEL:&lt;number&gt;, for example TEL:+14255551212.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Including this parameter will cause the cmdlet to not only modify the contact object but will return the new object as output.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrimaryLanguage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The primary language used for the trusted application. The language must be configured using a valid language code, such as en-US (U.S. English), fr-FR (French), etc.</p></td>
</tr>
<tr class="even">
<td><p><em>SecondaryLanguages</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>A collection of languages that can also be used for trusted applications. Values must be configured as a comma-separated values list of language codes. For example, the following syntax sets French Canadian and French as secondary languages: -SecondaryLanguages &quot;fr-CA&quot;,&quot;fr-FR&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>You cannot modify the SIP address of a contact. The SIP address is assigned when the application endpoint is created.</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is not used with this cmdlet.</p></td>
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

Microsoft.Rtc.Management.ADConnect.Schema.OCSADApplicationContact object. Accepts pipelined input of trusted application endpoint objects.

## Return Types

This cmdlet does not return a value. It modifies an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADApplicationContact.

## 另请参阅

#### 其他资源

[New-CsTrustedApplicationEndpoint](new-cstrustedapplicationendpoint.md)  
[Remove-CsTrustedApplicationEndpoint](remove-cstrustedapplicationendpoint.md)  
[Get-CsTrustedApplicationEndpoint](get-cstrustedapplicationendpoint.md)

