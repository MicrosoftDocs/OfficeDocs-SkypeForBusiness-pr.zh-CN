---
title: Set-CsAudioTestServiceApplication
TOCTitle: Set-CsAudioTestServiceApplication
ms:assetid: d2c6880b-58df-43d1-9f26-d2b9f54d3f0b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398907(v=OCS.15)
ms:contentKeyID: 49314343
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAudioTestServiceApplication

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify the property values for any of the Audio Test service application contacts currently in use in your organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAudioTestServiceApplication -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DisplayNumber <String>] [-Enabled <$true | $false>] [-EnabledForFederation <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-PrimaryLanguage <String>] [-SecondaryLanguages <MultiValuedProperty>] [-SipAddress <String>] [-Type <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the primary language for the Audio Test service contact sip:RedmondAudioTest@litwareinc.com is set to U.S. English (en-US).

    Set-CsAudioTestServiceApplication -Identity "sip:RedmondAudioTest@litwareinc.com" -PrimaryLanguage "en-US" 

## EXAMPLE 2

Example 2 clears the value of the PrimaryLanguage property for the Audio Test service contact sip:RedmondAudioTest@litwareinc.com. This is done by including the PrimaryLanguage parameter and setting the parameter value to $Null.

    Set-CsAudioTestServiceApplication -Identity "sip:RedmondAudioTest@litwareinc.com" -PrimaryLanguage $Null 

## EXAMPLE 3

In Example 3, all the Audio Test service contacts in use in the organization are configured to use U.S. English as their primary language. To do this, the **Get-CsAudioTestServiceApplication** cmdlet is first called without any parameters in order to return a collection of the Audio Test service contacts. This collection is then piped to the **Set-CsAudioTestServiceApplication**, which assigns U.S. English (en-Us) to the PrimaryLanguage property for each contact in the collection.

    Get-CsAudioTestServiceApplication | Set-CsAudioTestServiceApplication -PrimaryLanguage "en-US"

## Detailed Description

The Audio Test service enables Lync Server users to test their voice connections before they make a voice call. To do this, users click the Check call quality button found on the Audio Device tab of the Lync Options dialog box. When a user clicks this button, a call will be made to the automated Audio Test service. The call will be answered and, after an introductory prompt is played, the caller will be asked to record a brief message (10 seconds maximum). That recording will then be replayed, enabling the caller to hear what he or she sounds like over the current connection.

The Audio Test service relies, in part, on Active Directory contact objects. These objects are automatically created for you when you install 音频自动程序; there is no way to manually create these objects. However, administrators can use the **Get-CsAudioTestServiceApplication** cmdlet to retrieve information about the various test service contacts currently in use in the organization. Administrators can also use the **Set-CsAudioTestServiceApplication** cmdlet to modify the properties of these contacts.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAudioTestServiceApplication** cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAudioTestServiceApplication"}

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
<td><p>SIP address of the audio test service contact to be modified.</p></td>
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
<td><p>Active Directory display name of the contact object.</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Although a valid property, DisplayNumber is not actually used with the Audio Test service.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the contact object has been enabled for Lync Server. If you set this value to False ($False), the contact will no longer be able to log on to Lync Server; setting this value to True ($True) re-enables the contact’s logon privileges.</p></td>
</tr>
<tr class="even">
<td><p><em>EnabledForFederation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether this contact is available to users from a federated domain. If set to False, only users within your organization will have access to the contact.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the contact object has been enabled for Enterprise Voice, which is the Microsoft implementation of Voice over Internet Protocol (VoIP). With Enterprise Voice, users can use make telephone calls by using the Internet rather than by using the standard telephone network.</p></td>
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
<td><p>Although a valid property, LineUri is not actually used with the Audio Test service.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user being assigned the policy. By default, the <strong>Set-CsAudioTestServiceApplication</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrimaryLanguage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Primary language used for the audio test service. The language must be configured using one of the allowed language codes; for example, en-US for U.S. English; fr-FR for French; etc. To return a list of the available language codes, type the following command at the Windows PowerShell prompt:</p>
<p>Get-CsDialInConferencingLanguageList | Select-Object -ExpandProperty Languages.</p></td>
</tr>
<tr class="even">
<td><p><em>SecondaryLanguages</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>Although a valid property, SecondaryLanguages is not actually used with the Audio Test service.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is currently disabled. You cannot change the SIP address using Set-CsAudioTestServiceApplication.</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the type of test contact being deployed. By default, contacts are listed as Automaton, which means they can interact with callers.</p></td>
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

The **Set-CsAudioTestServiceApplication** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADApplicationContact object.

## Return Types

The **Set-CsAudioTestServiceApplication** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Get-CsAudioTestServiceApplication](get-csaudiotestserviceapplication.md)

