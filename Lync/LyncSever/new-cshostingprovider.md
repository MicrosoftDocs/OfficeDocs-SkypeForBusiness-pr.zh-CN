---
title: New-CsHostingProvider
TOCTitle: New-CsHostingProvider
ms:assetid: 6874cc14-d250-43d4-8868-43cd8d202e9c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398490(v=OCS.15)
ms:contentKeyID: 49313128
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsHostingProvider

 

_**上一次修改主题：** 2015-03-09_

Creates a new hosting provider for use in your organization. A hosting provider is a private third-party organization that provides instant messaging, presence, and related services for a domain that you would like to federate with. Hosting providers, such as Microsoft Lync Online 2010, differ from public providers (such as Yahoo\!, MSN, and AOL) in that their services are not offered to the general public. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsHostingProvider -Enabled <$true | $false> -Identity <XdsGlobalRelativeIdentity> -ProxyFqdn <String> [-AutodiscoverUrl <String>] [-IsLocal <$true | $false>] [-SipClientPort <UInt64>] [-VerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] <COMMON PARAMETERS>

    New-CsHostingProvider -Enabled <$true | $false> -EnabledSharedAddressSpace <$true | $false> -HostsOCSUsers <$true | $false> -Identity <XdsGlobalRelativeIdentity> -ProxyFqdn <String> [-AutodiscoverUrl <String>] [-IsLocal <$true | $false>] [-SipClientPort <UInt64>] [-VerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, a new hosting provider with the Identity Fabrikam.com is created. In addition to specifying the Identity, the command also includes the other two required parameters: ProxyFqdn (which specifies the proxy server used by Fabrikam.com); and Enabled, which indicates whether or not the new hosting provider is enabled for use. If you leave out any of the required parameters, the **New-CsHostingProvider** cmdlet will prompt you to enter those values before continuing.

    New-CsHostingProvider -Identity Fabrikam.com -ProxyFqdn "proxyserver.fabrikam.com" -Enabled $True

## EXAMPLE 2

Example 2 demonstrates how you can create a new hosting provider for use in a split domain scenario. (Split domain means that some of your Lync Server accounts are maintained on-premises while other accounts are maintained by a hosting provider.) To create this type of hosting provider, you must include the three required parameters (Identity; ProxyFqdn; and Enabled). In addition, you must include, and set to True, both the HostsOCSUsers and the EnabledSharedAddressSpace parameters. To create a split domain provider that hosts non-Lync Server services (such as Microsoft Exchange), include these same two parameters but set HostsOCSUsers to False.

    New-CsHostingProvider -Identity Fabrikam.com -ProxyFqdn "proxyserver.fabrikam.com" -Enabled $True -HostsOCSUsers $True -EnabledSharedAddressSpace $True

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Lync 2013. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A hosting provider is an organization which provides SIP communication services for other organizations; for example, Fabrikam, Inc. might host users from Contoso, Northwind Traders, and Wingtip Toys. When you establish a federation relationship with a hosting provider, you effectively establish federation with any organization hosted by that provider. For example, if you federate with Fabrikam, your users will be able to exchange instant messages and presence information with users from Contoso, Northwind Traders, and Wingtip Toys.

Hosting providers are also used in split domain scenarios. In a split domain scenario, some of your Lync Server users have accounts hosted on-premises (that is, hosted on your local implementation of Lync Server). Other users have their accounts maintained off-premises by the third-party hosting provider. Federating with the hosting provider enables on-premises and off-premises users to communicate with one another.

In order to federate with a third-party hosting provider, you need to create and enable a new hosting provider. (In addition, the third-party provider will need to create a federation relationship with you.) The **New-CsHostingProvider** cmdlet enables you to set up three types of hosting provider relationships:

Direct federation with the hosting provider. To create this type of relationship you must include the three required parameters: Identity; ProxyFqdn; and Enabled.

Split domain, with Lync Server services being hosted. To create this type of relationship you need to include the three required parameters. In addition, you must set both the EnabledSharedAddressSpace and HostsOCSUsers properties to True.

Split domain, with non-Lync Server services (such as Microsoft Exchange) being hosted. To create this type of relationship, you need to include the three required parameters. In addition, you must set the EnabledSharedAddressSpace to True and HostsOCSUsers to False.

When you create a new hosting provider, both the Identity and the proxy fully qualified domain name (FQDN) for that provider must be unique: you cannot have two hosting providers (or even one hosting provider and one public provider) that share an identity and/or a proxy FQDN.

Note, too that you cannot federate with a hosting provider if your 边缘服务器 are configured to use default routing rather than Domain Name System (DNS) server routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsHostingProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsHostingProvider"}

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
<td><p>Indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to True. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnabledSharedAddressSpace</em></p></td>
<td><p>Required</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, indicates that the hosting provider is being used in a split domain scenario. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>HostsOCSUsers</em></p></td>
<td><p>Required</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, indicates that the hosting provider is used to host Lync Server accounts. If False, that indicates that the provider hosts other account types, such as Microsoft Exchange accounts. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the hosting provider to be created. The Identity is a string value; the Identity might be the FQDN of the hosting provider (for example, fabrikam.com) or perhaps the name of the company providing the services (Fabrikam, Inc.).</p>
<p>Hosting provider Identities must be unique. Your command will fail if you try to create a new hosting provider with the same Identity as an existing provider.</p></td>
</tr>
<tr class="odd">
<td><p><em>ProxyFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The FQDN for the proxy server used by the hosting provider. Note that this value cannot be modified. If the hosting provider later changes its proxy server or if you make a mistake when you first specify the proxy FQDN you will need to delete and then recreate the entry for that provider.</p></td>
</tr>
<tr class="even">
<td><p><em>AutodiscoverUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the autodiscover service used by a hosting provider that hosts Lync Server accounts. The autodiscover service enables client applications to determine how to access resources such as a user’s home pool.</p></td>
</tr>
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
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>IsLocal</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, indicates that the proxy server used by the hosting provider is contained within your Lync Server topology. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipClientPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Port used by the provider for communicating with SIP clients; the default value is 443. Note that, by default, the SipClientPort is not displayed when you run the <strong>Get-CsHostingProvider</strong> cmdlet. To see the SipClientPort, use a command similar to this:</p>
<p>Get-CsHostingProvider | Select-Object *</p></td>
</tr>
<tr class="even">
<td><p><em>VerificationLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.VerificationLevelType</p></td>
<td><p>Indicates the allowed verification level for messages sent to and from the hosted provider. The VerificationLevel must be set to one of the following values:</p>
<p>AlwaysVerifiable. Indicates that all messages sent from the hosting provider are considered verifiable. That means that no messages from the hosting provider will be rejected.</p>
<p>AlwaysUnverifiable. Indicates that all messages sent from the hosting provider are considered unverifiable. As a result, messages are passed only if the user on the hosting provider is also in your Contacts list.</p>
<p>UseSourceVerification. Relies on the verification level included in messages sent from the hosting provider. If this level is not specified, then the message will be rejected as being unverifiable.</p>
<p>The default value is AlwayVerifiable.</p></td>
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

None. The **New-CsHostingProvider** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object.

## 另请参阅

#### 其他资源

[Disable-CsHostingProvider](disable-cshostingprovider.md)  
[Enable-CsHostingProvider](enable-cshostingprovider.md)  
[Get-CsHostingProvider](get-cshostingprovider.md)  
[Remove-CsHostingProvider](remove-cshostingprovider.md)  
[Set-CsHostingProvider](set-cshostingprovider.md)

