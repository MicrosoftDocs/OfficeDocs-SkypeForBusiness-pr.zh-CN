﻿---
title: Set-CsPublicProvider
TOCTitle: Set-CsPublicProvider
ms:assetid: ff7c1a5a-823c-41f7-80dc-1f5842609ccb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413087(v=OCS.15)
ms:contentKeyID: 49314866
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPublicProvider

 

_**上一次修改主题：** 2015-03-09_

Modifies a public provider currently configured for use in your organization. A public provider is an organization that provides instant messaging (IM), presence, and related services to the general public. Lync Server ships with three public providers configured but not enabled: Yahoo\!; AIM (AOL); and Messenger (MSN). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsPublicProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsPublicProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-VerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 sets the VerificationLevel for the public provider with the Identity Messenger. This is done by including the VerificationLevel parameter and the parameter value AlwaysVerifiable.

    Set-CsPublicProvider -Identity "Messenger" -VerificationLevel "AlwaysVerifiable"

## EXAMPLE 2

In Example 2, the verification level is modified for all the public providers currently in use in the organization. To do this, the command first calls the **Get-CsPublicProvider** cmdlet without any parameters in order to return a collection of all the public providers currently configured for use. This collection is then piped to the **Set-CsPublicProvider** cmdlet, which takes each provider in the collection and changes the value of the VerificationLevel property to AlwaysVerifiable.

    Get-CsPublicProvider | Set-CsPublicProvider -VerificationLevel "AlwaysVerifiable"

## EXAMPLE 3

The command shown in Example 3 modifies the verification level for any public provider where that level is currently set to AlwaysUnverifiable. To accomplish this task, the command first calls the **Get-CsPublicProvider** cmdlet in order to return a collection of all the public providers configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those providers where the VerificationLevel property is equal to AlwaysUnverifiable. In turn, this filtered collection is piped to the **Set-CsPublicProvider** cmdlet, which changes the VerificationLevel for each provider in the collection to AlwaysVerifiable.

    Get-CsPublicProvider | Where-Object {$_.VerificationLevel -eq "AlwaysUnverifiable"} | Set-CsPublicProvider -VerificationLevel "AlwaysVerifiable"

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Microsoft Lync 2010. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A public provider is an organization which provides SIP communication services for the general public. When you establish a federation relationship with a public provider, you effectively establish federation with any user who has an account hosted by that provider. For example, if you federate with Messenger (MSN), then (depending on how you have configured your system) your users will be able to exchange instant messages and presence information with anyone who have a Messenger instant messaging account.

In order to federate with a public provider you will need to create and enable a new public provider. (In addition, the public provider will need to create a federation relationship with you.) Lync Server includes three public providers - Yahoo\!; AOL; and MSN - that are preconfigured for you. As additional public providers become available, you can create federation relationships with these new providers by using the **New-CsPublicProvider** cmdlet. After federated relationships have been established, you can then use the **Set-CsPublicProvider** cmdlet to modify two important property values -- Enabled and VerificationLevel -- of these relationships.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsPublicProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPublicProvider"}

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
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the federation relationship between your organization and the public provider is active. If set to True, users in your organization will be able to exchange instant messages and presence information with users who have accounts hosted on the public provider. If set to False, users in your organization will not be able to exchange instant messages and presence information with users who have accounts hosted on the public provider.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts or non-fatal error messages that might occur when you run the cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the public provider to be modified. The Identity is typically the name of the website providing the services (for example, Yahoo!; AOL; MSN; etc.).</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DisplayPublicProvider object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>VerificationLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.VerificationLevelType</p></td>
<td><p>Indicates how (or if) messages sent from a public provider are verified to ensure that they were sent from that provider. The VerificationLevel must be set to one of the following values:</p>
<p>AlwaysVerifiable. All messages purportedly sent from this provider will be accepted. If a verification header is not found in the message it will be added by Lync Server. This is the default value.</p>
<p>AlwaysUnverifiable. All messages purportedly sent from a public provider are considered unverified. They will be delivered only if they were sent from a person who is on the recipient’s Contacts list. For example, if Ken Myer is on your Contacts list you will be able to receive messages from him. If Pilar Ackerman is not on your Contacts list then you will not be able to receive messages from her. Note that Lync 2013 users can manually override this setting, thereby allowing themselves to receive messages people not on their Contacts list.</p>
<p>UseSourceVerification. Uses the verification header added to the message by the public provider. If the verification information is missing the message will be rejected. This value has been deprecated for use in Lync Server 2013.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider object. The **Set-CsPublicProvider** cmdlet accepts pipelined instances of the public provider object.

## Return Types

The **Set-CsPublicProvider** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider object.

## 另请参阅

#### 其他资源

[Disable-CsPublicProvider](disable-cspublicprovider.md)  
[Enable-CsPublicProvider](enable-cspublicprovider.md)  
[Get-CsPublicProvider](get-cspublicprovider.md)  
[New-CsPublicProvider](new-cspublicprovider.md)  
[Remove-CsPublicProvider](remove-cspublicprovider.md)

