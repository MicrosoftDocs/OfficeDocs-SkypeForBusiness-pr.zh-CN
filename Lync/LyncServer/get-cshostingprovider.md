---
title: Get-CsHostingProvider
TOCTitle: Get-CsHostingProvider
ms:assetid: fd493022-eb53-4084-aa81-213cb5e959fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413078(v=OCS.15)
ms:contentKeyID: 49314842
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsHostingProvider

 

_**上一次修改主题：** 2015-03-09_

Returns information about the hosting providers configured for use in your organization. A hosting provider is a third-party organization that provides instant messaging, presence, and related services for a domain that you would like to federate with. Hosting providers, such as Microsoft Lync Online 2010, differ from public providers (such as Yahoo\!, MSN, and AOL) in that their services are not offered to the general public. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsHostingProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsHostingProvider [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns a collection of all the hosting providers configured for use in the organization. Calling the **Get-CsHostingProvider** cmdlet without any additional parameters returns the complete collection of hosting providers.

    Get-CsHostingProvider

## EXAMPLE 2

Example 2 returns the hosting provider that has the Identity Fabrikam.com. Because Identities must be unique among hosting providers, this command will never return more than a single item.

    Get-CsHostingProvider -Identity Fabrikam.com

## EXAMPLE 3

The command shown in Example 3 returns a collection of all the hosting providers that have an Identity that ends with the string value ".org" (for example, fabrikam.org and contoso.org).

    Get-CsHostingProvider -Filter *.org

## EXAMPLE 4

In Example 4, all the hosting providers that are currently enabled for use are returned. To do this, the **Get-CsHostingProvider** cmdlet is first called in order to return a collection of all the hosting providers currently configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those providers where the Enabled property is equal to True.

    Get-CsHostingProvider | Where-Object {$_.Enabled -eq $True}

## EXAMPLE 5

Example 5 returns all the hosting providers that have a shared address space and that host Lync Server users; by definition, that means that the command returns all the hosting providers that are part of a "split-domain" setup. (Split domain simply means that some of your Lync Server accounts are maintained on-premises while other accounts are maintained by a hosting provider.) To carry out this task, the command first uses the **Get-CsHostingProvider** cmdlet to return a collection of all the currently configured hosting providers. This collection is then piped to the **Where-Object** cmdlet, which selects only those providers that meet two criteria: 1) the Enabled property is equal to True; and, 2) the EnabledSharedAddressSpace property is equal to True.

    Get-CsHostingProvider | Where-Object {$_.Enabled -eq $True -and $_.EnabledSharedAddressSpace -eq $True}

## EXAMPLE 6

The command shown in Example 6 displays all the property values for all the hosting providers configured for use in your organization. By default, the property values for EnabledSharedAddressSpace and HostsOCSUsers are not displayed when you run the **Get-CsHostingProvider** cmdlet. To see the values for these properties, the information returned by the **Get-CsHostingProvider** cmdlet is piped to the **Select-Object** cmdlet; the wildcard character (\*) instructs the **Select-Object** cmdlet to display all the properties and property values for the returned items.

    Get-CsHostingProvider | Select-Object *

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Lync. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A hosting provider is an organization that provides SIP communication services for other organizations; for example, Fabrikam, Inc. might host users from Contoso, Northwind Traders, and Wingtip Toys. When you establish a federation relationship with a hosting provider, you effectively establish federation with any organization hosted by that provider. For example, if you federate with Fabrikam, your users will be able to exchange instant messages and presence information with users from Contoso, Northwind Traders, and Wingtip Toys.

Hosting providers are also used in split domain scenarios. In a split domain scenario, some of your Lync Server users have accounts hosted on-premises (that is, hosted on your local implementation of Lync Server). Other users have their accounts maintained off-premises by the third-party hosting provider. Federating with the hosting provider enables on-premises and off-premises users to communicate with one another.

The **Get-CsHostingProvider** cmdlet provides a way for you to return information about all the hosting providers that have been configured for use in your organization.

Note that you cannot federate with a hosting provider if your 边缘服务器 are configured to use default routing rather than Domain Name System (DNS) server routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsHostingProvider** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsHostingProvider"}

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
<td><p>Enables you to use wildcard values to return one or more hosting providers. For example, to return all the hosting providers that have an identity that ends with the string value &quot;.com&quot; use this syntax: -Filter &quot;*.com&quot;. To return all the hosting providers that have an Identity that begins with the string &quot;Fabri&quot; use this syntax: -Filter &quot;Fabri*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the hosting provider to be returned. The Identity might be the fully qualified domain name (FQDN) of the hosting provider (for example, fabrikam.com) or perhaps the name of the company providing the services (Fabrikam, Inc.).</p>
<p>If this parameter is not specified, the <strong>Get-CsHostingProvider</strong> cmdlet will return a collection of all the hosting providers configured for use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the hosting provider data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsHostingProvider** cmdlet does not accept pipelined input.

## Return Types

Returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object.

## 另请参阅

#### 其他资源

[Disable-CsHostingProvider](disable-cshostingprovider.md)  
[Enable-CsHostingProvider](enable-cshostingprovider.md)  
[New-CsHostingProvider](new-cshostingprovider.md)  
[Remove-CsHostingProvider](remove-cshostingprovider.md)  
[Set-CsHostingProvider](set-cshostingprovider.md)

