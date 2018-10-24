---
title: Enable-CsHostingProvider
TOCTitle: Enable-CsHostingProvider
ms:assetid: 0ba76785-6c6d-4ee6-9418-5c77b2cbaedf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398166(v=OCS.15)
ms:contentKeyID: 49311966
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsHostingProvider

 

_**上一次修改主题：** 2015-03-09_

Enables a hosting provider for use in your organization. A hosting provider is a third-party organization that provides instant messaging, presence, and related services for a domain that you would like to federate with. Hosting providers, such as Microsoft Lync Online 2010, differ from public providers (such as Yahoo\!, MSN, and AOL) in that their services are not offered to the general public. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsHostingProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Enable-CsHostingProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the hosting provider with the Identity Fabrikam.com is enabled for use. Note that this command will return an error if Fabrikam.com has already been enabled for use.

    Enable-CsHostingProvider -Identity Fabrikam.com

## EXAMPLE 2

Example 2 shows how you can enable all the hosting providers that are currently disabled. To do this, the command first calls the **Get-CsHostingProvider** cmdlet without any additional parameters in order to return a collection of all the hosting providers currently configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects any provider where the Enabled property is equal to False; by definition, that is any provider that is currently disabled. This filtered collection is then piped to the **Enable-CsHostingProvider** cmdlet, which enables each of the providers in the collection.

    Get-CsHostingProvider | Where-Object {$_.Enabled -eq $False} | Enable-CsHostingProvider

## EXAMPLE 3

In Example 3, all of the hosting providers used in a "split domain" setup are enabled for use. (Split domain means that some of your Lync Server accounts are maintained on-premises while other accounts are maintained by a hosting provider.) To carry out this task, the command first uses the **Get-CsHostingProvider** cmdlet to return a collection of all the currently-configured hosting providers. This collection is then piped to the **Where-Object** cmdlet, which selects only those providers that meet two criteria: 1) the EnabledSharedAddressSpace property is equal to True; and, 2) the Enabled property is equal to False. After that, the filtered collection is piped to the **Enable-CsHostingProvider** cmdlet, which enables each provider in the collection.

    Get-CsHostingProvider | Where-Object {$_.EnabledSharedAddressSpace -eq $True -and $_.Enabled -eq $False} | Enable-CsHostingProvider

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Lync 2013. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A hosting provider is an organization which provides SIP communication services for other organizations; for example, Fabrikam, Inc. might host users from Contoso, Northwind Traders and Wingtip Toys. When you establish a federation relationship with a hosting provider, you effectively establish federation with any organization hosted by that provider. For example, if you federate with Fabrikam, your users will be able to exchange instant messages and presence information with users from Contoso, Northwind Traders, and Wingtip Toys.

Hosting providers are also used in split domain scenarios. In a split domain scenario, some of your Lync Server users have accounts hosted on-premises (that is, hosted on your local implementation of Lync Server). Other users have their accounts maintained off-premises by the third-party hosting provider. Federating with the hosting provider enables on-premises and off-premises users to communicate with one another.

In order to federate with a third-party hosting provider, you need to create and enable a new hosting provider. (In addition, the third-party provider will need to create a federation relationship with you.) You can enable a hosting provider at the time that provider is created; alternatively, you can enable that provider after-the-fact by using the **Enable-CsHostingProvider** cmdlet

Note that you cannot federate with a hosting provider if your 边缘服务器 are configured to use default routing rather than Domain Name System (DNS) server routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Enable-CsHostingProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Enable-CsHostingProvider"}

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
<td><p>Unique identifier for the hosting provider to be enabled. The Identity is might be the fully qualified domain name (FQDN) of the hosting provider (for example, fabrikam.com) or perhaps the name of the company providing the services (Fabrikam, Inc.).</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object. The **Enable-CsHostingProvider** cmdlet accepts pipelined instances of the hosting provider object.

## Return Types

None. Instead, the cmdlet enables instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object.

## 另请参阅

#### 其他资源

[Disable-CsHostingProvider](disable-cshostingprovider.md)  
[Get-CsHostingProvider](get-cshostingprovider.md)  
[New-CsHostingProvider](new-cshostingprovider.md)  
[Remove-CsHostingProvider](remove-cshostingprovider.md)  
[Set-CsHostingProvider](set-cshostingprovider.md)

