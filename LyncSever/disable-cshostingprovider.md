---
title: Disable-CsHostingProvider
TOCTitle: Disable-CsHostingProvider
ms:assetid: 67d67111-aa04-4241-8f41-e8059fd1649c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398481(v=OCS.15)
ms:contentKeyID: 49313116
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsHostingProvider

 

_**上一次修改主题：** 2015-03-09_

Disables a hosting provider currently in use in your organization. A hosting provider is a third-party organization that provides instant messaging, presence, and related services for a domain that you would like to federate with. Hosting providers, such as Microsoft Lync Online 2010, differ from public providers (such as Yahoo\!, MSN, and AOL) in that their services are not offered to the general public. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Disable-CsHostingProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Disable-CsHostingProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 disables the hosting provider Fabrikam.com. Note that this command will return an error message if Fabrikam.com is already disabled.

    Disable-CsHostingProvider -Identity "Fabrikam.com"

## EXAMPLE 2

Example 2 disables all the hosting providers that are currently enabled. To do this, the command first calls the **Get-CsHostingProvider** cmdlet to return a collection of all the hosting providers configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those providers where the Enabled property is equal to True. The filtered collection is then piped to the **Disable-CsHostingProvider** cmdlet, which disables each provider in the collection.

    Get-CsHostingProvider | Where-Object {$_.Enabled -eq $True} | Disable-CsHostingProvider

## EXAMPLE 3

In Example 3, all the enabled hosting providers where the verification level is not equal to AlwaysVerifiable are disabled. To carry out this task, the command first uses the **Get-CsHostingProvider** cmdlet to return a collection of all the hosting providers configured for use in the organization. This collection is piped to the **Where-Object** cmdlet, which selects only those providers that meet two criteria: 1) the VerificationLevel property is not equal to AlwaysVerifiable; and, 2) the Enabled property is equal to True. The filtered collection is then piped to the **Disable-CsHostingProvider** cmdlet, which disables each provider in the collection.

    Get-CsHostingProvider | Where-Object {$_.VerificationLevel -ne "AlwaysVerifiable" -and $_.Enabled -eq $True} | Disable-CsHostingProvider

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Lync 2013. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A hosting provider is an organization that provides SIP communication services for other organizations; for example, Fabrikam, Inc. might host users from Contoso, Northwind Traders, and Wingtip Toys. When you establish a federation relationship with a hosting provider, you effectively establish federation with any organization hosted by that provider. For example, if you federate with Fabrikam, your users will be able to exchange instant messages and presence information with users from Contoso, Northwind Traders, and Wingtip Toys.

Hosting providers are also used in split domain scenarios. In a split domain scenario, some of your Lync Server users have accounts hosted on-premises (that is, hosted on your local implementation of Lync Server). Other users have their accounts maintained off-premises by the third-party hosting provider. Federating with the hosting provider enables on-premises and off-premises users to communicate with one another.

In order to federate with a third-party hosting provider you need to create and enable a new hosting provider. (In addition, the third-party provider will need to create a federation relationship with you.) You can enable a hosting provider at the time that provider is created; alternatively, you can enable the provider after-the-fact by using the **Enable-CsHostingProvider** cmdlet. In addition, you can use the **Disable-CsHostingProvider** cmdlet to disable the relationship at any time. When you disable a hosting provider that provider remains a valid federation partner; however, all communication activity between your organization and the provider will be suspended until the provider has been re-enabled.

Note that you cannot federate with a hosting provider if your 边缘服务器 are configured to use default routing rather than Domain Name System (DNS) server routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Disable-CsHostingProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Disable-CsHostingProvider"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the hosting provider to be disabled. The Identity might be the fully qualified domain (FQDN) name of the hosting provider (for example, fabrikam.com) or perhaps the name of the company providing the services (Fabrikam, Inc.).</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DisplayHostingProvider object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object. The **Disable-CsHostingProvider** cmdlet accepts pipelined instances of the hosting provider object.

## Return Types

None. Instead, the cmdlet disables instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object.

## 另请参阅

#### 其他资源

[Enable-CsHostingProvider](enable-cshostingprovider.md)  
[Get-CsHostingProvider](get-cshostingprovider.md)  
[New-CsHostingProvider](new-cshostingprovider.md)  
[Remove-CsHostingProvider](remove-cshostingprovider.md)  
[Set-CsHostingProvider](set-cshostingprovider.md)

