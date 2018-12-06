﻿---
title: New-CsStaticRoute
TOCTitle: New-CsStaticRoute
ms:assetid: 1df0c537-f24f-4a63-be6d-70d016f985a5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398265(v=OCS.15)
ms:contentKeyID: 49312191
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsStaticRoute

 

_**上一次修改主题：** 2015-03-09_

Creates a new static phone route. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsStaticRoute -Destination <String> -MatchUri <String> -Port <UInt16> -TLSRoute <SwitchParameter> [-Enabled <$true | $false>] [-MatchOnlyPhoneUri <$true | $false>] [-ReplaceHostInRequestUri <$true | $false>] [-TLSCertIssuer <String>] [-TLSCertSerialNumber <Byte[]>] [-UseDefaultCertificate <$true | $false>] <COMMON PARAMETERS>

    New-CsStaticRoute -Destination <String> -MatchUri <String> -Port <UInt16> -TCPRoute <SwitchParameter> [-Enabled <$true | $false>] [-MatchOnlyPhoneUri <$true | $false>] [-ReplaceHostInRequestUri <$true | $false>] <COMMON PARAMETERS>

    COMMON PARAMETERS:

## Examples

## EXAMPLE 1

The commands shown in Example 1 create a new static route and then add that route to the global static routing configuration collection. To carry out this task, the first command uses the **New-CsStaticRoute** cmdlet to create an in-memory-only route that uses TCP as its transport protocol. The route points to the next hop IP address 192.168.0.100, uses port 8025, and matches any URI from the domain litwareinc.com. The resulting route object is stored in a variable named $x.

The second command in the example then adds the new route to the global static routing configuration collection. This is done by calling the **Set-CsStaticRoutingConfiguration** cmdlet along with the Route parameter. The parameter value @{Add=$x} adds the route object stored in $x to the existing set of routes already in the global collection.

    $x = New-CsStaticRoute -TCPRoute -Destination "192.168.0.100" -Port 8025 -MatchUri "litwareinc.com" 
    
    Set-CsStaticRoutingConfiguration -Identity global -Route @{Add=$x}

## EXAMPLE 2

Example 2 shows how you can create a new static route that uses TLS as its transport protocol, and then add that route to the global static routing configuration collection. To do this, the first command in the example uses the **New-CsStaticRoute** cmdlet to create an in-memory-only route that uses TLS as its transport protocol. The route points to the "atl-proxy-001.litwareinc.com" as its destination, uses port 8025, and matches any URI that uses the domain suffix "litwareinc.com". In addition, the new route object, which is stored in a variable named $x, uses the default certificate for authentication purposes (-UseDefaultCertificate $True).

After the route object has been created, the second command in the example then adds the new route to the global static routing configuration collection.

    $x = New-CsStaticRoute -TLSRoute -Destination "atl-proxy-001.litwareinc.com" -Port 8025 -MatchUri "*.litwareinc.com" -UseDefaultCertificate $True
    
    Set-CsStaticRoutingConfiguration -Identity global -Route @{Add=$x}

## EXAMPLE 3

Example 3 creates a new static route using TLS and a specific certificate; this is indicated by included the required TLS parameters.

After the route object has been created, the second command in the example then adds the new route to the global static routing configuration collection.

    $x = New-CsStaticRoute -TLSRoute -Destination "atl-proxy.litwareinc.com" -Port 5061 -MatchUri "litwareinc.com" -UseDefaultCertificate $False -TLSCertIssuer "CN=CertificateAuthority, DC=litwareinc, DC=com" -TLSCertSerialNumber 0x8f,0x33,0x70,0x93,0x70,0x05,0x33,0x00,0x02,0x33
    
    Set-CsStaticRoutingConfiguration -Identity global -Route @{Add=$x}

## Detailed Description

When you send a SIP message to someone that message might need to traverse multiple subnets and networks before it is delivered; the path traveled by the message is often referred to as a route. In networking, there are two types of routes: dynamic and static. With dynamic routing, servers use algorithms to determine the next location (the next hop) where the message should be forwarded. With static routing, message paths are predetermined by system administrators. When a message is received by a server, the server checks the message address and then forwards the message to the next hop server that has been preconfigured by an administrator. If configured correctly, static routes help ensure timely, and accurate, delivery of messages, and with minimal overheard placed on servers. The downside to static routes is that messages are not dynamically rerouted in the event of a network failure.

New static routes are created by using the **New-CsStaticRoute** cmdlet. After a route has been created by using the **New-CsStaticRoute** cmdlet, you must then add the route to a collection of routing configuration settings by using the **Set-CsStaticRoutingConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsStaticRoute** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsStaticRoute"}

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
<td><p><em>Destination</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>If the route uses Transport Layer Security (TLS) as the transport protocol, then the Destination is the fully qualified domain name (FQDN) of the next hop server. For example: -Destination &quot;atl-proxy-001.litwareinc.com&quot;.</p>
<p>If the route uses Transmission Control Protocol (TCP) as the transport protocol, then the Destination is the IP address of the next hop router. For example: -Destination &quot;192.168.0.240&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>MatchUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>FQDN or domain suffix used to determine if the message is being sent to a user handled by this route. For example, you might use the FQDN &quot;litwareinc.com&quot;. This pattern matches any user who has a SIP address that ends with the domain name &quot;litwareinc.com&quot;.</p>
<p>To match child domains of a domain, you can use a wildcard value like &quot;*.litwareinc.com&quot;. That value matches any domain that ends with the suffix &quot;litwareinc.com&quot;. For example: northamerica.litwareinc.com; asia.litwareinc.com; and europe.litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Port</em></p></td>
<td><p>Required</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port number used for SIP routing. For example: -Port 7742.</p></td>
</tr>
<tr class="even">
<td><p><em>TCPRoute</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Configures TCP as the transport protocol for the new route.</p></td>
</tr>
<tr class="odd">
<td><p><em>TLSRoute</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Configures TLS as the transport protocol for the new route.</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True then the route is enabled, and any messages matching the MatchURI pattern will be routed to the next hop server. If set to False, the route is disabled and will not be used in routing messages. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>MatchOnlyPhoneUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, only messages addressed to phone Uniform Resource identifiers (URIs) (for example, sip:kenmmyer@litwareinc.com;user=phone) will be matched and, potentially, routed. If set to False (the default value) then all messages will be matched.</p></td>
</tr>
<tr class="even">
<td><p><em>ReplaceHostInRequestUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True ($True) then the host portion of a Request-URI will be replaced by the address of the next hop server. If set the False then the Request-URI will be used as-is. The Request-URI represents the URI of the user or service that the request (message) is addressed to. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>TLSCertIssuer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the certification authority (CA) that issued the certificate to be used in the static route. This parameter is not used if you have configured TCP as the transport protocol.</p>
<p>If you include the TLSCertIssuer parameter then you must also use the TLSCertSerialNumber parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>TLSCertSerialNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Byte[]</p></td>
<td><p>Serial number of the TLS certificate to be used in the static route. Serial numbers must be passed as a byte array; this means you must pass the serial number as an array of two-character values. For example: -TLSCertSerialNumber 0x01, 0xA4, 0xD5, 0x67, 0x89.</p>
<p>This parameter is not used if you have configured TCP as the transport protocol.</p>
<p>If you include the TLSCertSerialNumber parameter then you must also use the TLSCertIssuer parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseDefaultCertificate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Configures the route to use your default Lync Server certificate as its authentication certificate. If you do not want to use the default certificate then you must specify a different certificate by using the TLSCertIssuer and TLSCertSerialNumber parameters.</p>
<p>To view the default certificate, use the following command:</p>
<p>Get-CsCertificate | Where-Object {$_.Use –eq &quot;urn:certref:Default&quot;}</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsStaticRoute** cmdlet does not accept pipelined input.

## Return Types

The **New-CsStaticRoute** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.Route object.

## 另请参阅

#### 其他资源

[New-CsStaticRoutingConfiguration](new-csstaticroutingconfiguration.md)  
[Set-CsStaticRoutingConfiguration](set-csstaticroutingconfiguration.md)

