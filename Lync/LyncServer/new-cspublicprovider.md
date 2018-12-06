---
title: New-CsPublicProvider
TOCTitle: New-CsPublicProvider
ms:assetid: 0b2dcb40-13f8-4ce6-b537-527d34895ceb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398161(v=OCS.15)
ms:contentKeyID: 49311956
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPublicProvider

 

_**上一次修改主题：** 2015-03-09_

Creates a federation relationship with a new public provider. A public provider is an organization that provides instant messaging, presence, and related services to the general public. Lync Server ships with three public providers configured but not enabled: Yahoo; AIM (AOL); and Messenger (MSN). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsPublicProvider -Identity <XdsGlobalRelativeIdentity> -Enabled <$true | $false> -ProxyFqdn <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-IconUrl <String>] [-InMemory <SwitchParameter>] [-VerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new federation relationship with a public provider that has the Identity Fabrikam. In addition to specifying the Identity, two other property values (and their corresponding parameters) must be set: ProxyFqdn (set to proxyserver.fabrikam.com) and Enabled (which, in this case, is set to True).

    New-CsPublicProvider -Identity "Fabrikam" -ProxyFqdn "proxyserver.fabrikam.com" -Enabled $True

## EXAMPLE 2

Example 2 demonstrates how you can create a new public provider in memory only, modify the properties of that provider, then turn the virtual provider into a real provider that can be used in your organization. To do this, the first command in the example creates a public provider with the Identity Fabrikam. In addition to including the required parameters (Identity, ProxyFqdn, and Enabled), the command adds the InMemory parameter; this creates an in-memory-only instance of the provider that is then stored in a variable named $x.

After the in-memory instance of the provider has been created the second command in the example modifies the VerificationLevel of the virtual provider. The final command then uses the **Set-CsPublicProvider** cmdlet to turn the virtual provider (stored in $x) into an actual public provider. If you do not call the **Set-CsPublicProvider** cmdlet the real provider will not be created. In turn, the virtual provider will disappear the moment you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsPublicProvider -Identity "Fabrikam" -ProxyFqdn "proxyserver.fabrikam.com" -Enabled $True -InMemory
    $x.VerificationLevel = "AlwaysUnverifiable"
    Set-CsPublicProvider -Instance $x

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When a federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Lync 2013. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A public provider is an organization which provides SIP communication services for the general public. When you establish a federation relationship with a public provider, you effectively establish federation with any user who has an account hosted by that provider. For example, if you federate with Messenger (MSN), then your users will be able to exchange instant messages and presence information with anyone who has a Messenger instant messaging account.

In order to federate with a public provider you need to create and enable a new public provider. (In addition, the public provider will need to create a federation relationship with you.) The **Set-CsPublicProvider** enables you to modify property values for any of the public providers that have been configured for use in your organization.

Note that you cannot federate with a public provider if your Edge servers are configured to use default routing rather than DNS server routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsPublicProvider** cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPublicProvider"}

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
<td><p><em>Enabled</em></p></td>
<td><p>Required</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the federation relationship between your organization and the public provider is active. If set to True, users in your organization will be able to exchange instant messages and presence information with users who have accounts hosted on the public provider. If set to False, users in your organization will not be able to exchange instant messages and presence information with users who have accounts hosted on the public provider. You can enable and disable federation relationships at any time by using the <strong>Enable-CsPublicProvider</strong> cmdlet and the <strong>Disable-CsPublicProvider</strong> cmdlet, respectively.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the public provider to be created. The Identity typically the name of the website providing the services (for example, Yahoo!, AOL, or MSN.).</p>
<p>Identities must be unique not only among public providers, but also among hosting providers. Suppose you try to create a new public provider with the Identity Fabrikam. Your command will fail if a public provider or a hosting provider with that Identity already exists.</p></td>
</tr>
<tr class="odd">
<td><p><em>ProxyFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Specifies the fully qualified domain name (FQDN) (for example, proxyserver.fabrikam.com) of the proxy server used by the public provider.</p>
<p>Proxy FQDNs must be unique not only among public providers, but also among hosting providers. For example, suppose you try to create a new public provider with the proxy FQDN proxyserver.fabrikam.com. This command will fail if a public provider or a hosting provider with that proxy FQDN already exists.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>IconUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the icon used to indicate a Microsoft Skype contact.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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

None. The **New-CsPublicProvider** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider object.

## 另请参阅

#### 其他资源

[Disable-CsPublicProvider](disable-cspublicprovider.md)  
[Enable-CsPublicProvider](enable-cspublicprovider.md)  
[Get-CsPublicProvider](get-cspublicprovider.md)  
[Remove-CsPublicProvider](remove-cspublicprovider.md)  
[Set-CsPublicProvider](set-cspublicprovider.md)

