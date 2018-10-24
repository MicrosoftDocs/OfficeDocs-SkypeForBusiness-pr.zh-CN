﻿---
title: Get-CsStaticRoutingConfiguration
TOCTitle: Get-CsStaticRoutingConfiguration
ms:assetid: 94f126b4-b714-42ba-b9b6-81269634875f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398754(v=OCS.15)
ms:contentKeyID: 49313626
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsStaticRoutingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the static routing configuration settings used in your organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsStaticRoutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsStaticRoutingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the static routing configuration collections in use in your organization.

    Get-CsStaticRoutingConfiguration

## EXAMPLE 2

In Example 2, information about a single static routing configuration collection is returned: the collection with the Identity service:Registrar:atl-cs-001.litwareinc.com.

    Get-CsStaticRoutingConfiguration -Identity "service:Registrar:atl-cs-001.litwareinc.com"

## EXAMPLE 3

Example 3 uses the Filter parameter to return information about the static routing configuration collections assigned to the service scope. The filter value "service:\*" limits the returned data to collections that have an identity that begins with the string value "service:".

    Get-CsStaticRoutingConfiguration -Filter "service:*"

## EXAMPLE 4

Example 4 returns detailed route information for all the static routing configuration collections in use in the organization. To do this, the command first calls the **Get-CsStaticRoutingConfiguration** cmdlet without any parameters in order to return complete information for each static routing collection. This information is then piped to the **Select-Object** cmdlet, which uses the ExpandProperty parameter to "expand" the value of the Route property. When you expand a property, all the objects and values contained within that property are displayed on the screen in easy-to-read fashion.

    Get-CsStaticRoutingConfiguration | Select-Object -ExpandProperty Route

## EXAMPLE 5

The command shown in Example 5 returns information about all the static routes that are configured to only match telephone Uniform Resource Identifiers (URIs). To carry out this task, the command first calls the **Get-CsStaticRoutingConfiguration** cmdlet without any parameters; this returns all the static routing configuration collections and their associated routes. This collection is then piped to the **Select-Object**, cmdlet which uses the ExpandProperty to expand all the objects stored in the Route property. These route objects are then piped to the **Where-Object** cmdlet, which picks out only those routes where the MatchOnlyPhoneUri property is equal to True.

    Get-CsStaticRoutingConfiguration | Select-Object -ExpandProperty Route | Where-Object {$_.MatchOnlyPhoneUri -eq $True}

## Detailed Description

When you send a SIP message to someone that message might need to traverse multiple subnets and networks before it is delivered; the path traveled by the message is often referred to as a route. In networking, there are two types of routes: dynamic and static. With dynamic routing, servers use algorithms to determine the next location (the next hop) where a message should be forwarded. With static routing, message paths are predetermined by system administrators. When a message is received by a server, the server checks the message address and then forwards the message to the next hop server that has been preconfigured by an administrator. If configured correctly, static routes help ensure timely, and accurate, delivery of messages, and with minimal overheard placed on servers. The downside to static routes is that messages are not dynamically rerouted in the event of a network failure.

When you install Lync Server, a global collection of static routes is automatically created for you. (The collection is created, but there are no routes assigned to that collection.) In addition, the software enables you to create additional collections applied to the service scope (these new collections can only be assigned to the Registrar service). The **Get-CsStaticRoutingConfiguration** cmdlet provides a way for you to return information about all the static routing configuration collections in use in your organization. This includes the ability to return detailed information about each route assigned to a collection.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsStaticRoutingConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsStaticRoutingConfiguration"}

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
<td><p>Enables you to use wildcards when specifying the static routing configuration collection (or collections) to be returned. For example, this syntax returns all the static routing collections configured at the service scope: -Filter &quot;service:*&quot;.</p>
<p>Note that you cannot use both the Identity and the Filter parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the static routing configuration collection. To return information about the global collection, use this syntax: -Identity global. To retrieve information about a collection configured at the service scope, use syntax similar to this: -Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;. Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards, use the Filter parameter instead.</p>
<p>If you do not include either the Identity or the Filter parameters then the <strong>Get-CsStaticRoutingConfiguration</strong> cmdlet returns information about all your static routing configuration collections.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the static routing configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsStaticRoutingConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsStaticRoutingConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.RoutingSettings object.

## 另请参阅

#### 其他资源

[New-CsStaticRoutingConfiguration](new-csstaticroutingconfiguration.md)  
[Remove-CsStaticRoutingConfiguration](remove-csstaticroutingconfiguration.md)  
[Set-CsStaticRoutingConfiguration](set-csstaticroutingconfiguration.md)

