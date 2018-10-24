---
title: New-CsTrustedApplication
TOCTitle: New-CsTrustedApplication
ms:assetid: 1c804a97-f9b5-4c3e-adc6-a120b26c1f51
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398259(v=OCS.15)
ms:contentKeyID: 49312175
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsTrustedApplication

 

_**上一次修改主题：** 2015-03-09_

Adds a trusted application to a pool. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsTrustedApplication -ApplicationId <String> -TrustedApplicationPoolFqdn <String> <COMMON PARAMETERS>

    New-CsTrustedApplication [-Identity <ExternalApplicationIdentity>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -Port <Int32> [-Confirm [<SwitchParameter>]] [-EnableTcp <SwitchParameter>] [-Force <SwitchParameter>] [-LegacyApplicationName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates a trusted application with the Application ID tapp1. We use the TrustedApplicationPoolFqdn parameter to designate the trusted application pool this application will be on, in this case the pool with the FQDN TrustPool.litwareinc.com. We also must specify a port for the application; in this example we used port 6000. Note that running this cmdlet by specifying an ApplicationId and a TrustedApplicationPoolFqdn will automatically generate an Identity that can later be used to retrieve, modify, or remove this application.

    New-CsTrustedApplication -ApplicationId tapp1 -TrustedApplicationPoolFqdn TrustPool.litwareinc.com -Port 6000

## EXAMPLE 2

This example creates a trusted application with the Identity TrustPool.litwareinc.com/tapp2 on Port 6100. Notice the format of the Identity. This value must be in the format \<trusted pool FQDN\>/\<Application ID\>.

    New-CsTrustedApplication -Identity TrustPool.litwareinc.com/tapp2 -Port 6100

## Detailed Description

A trusted application is an application developed by a third party that is given trusted status to run as part of Lync Server but that is not a built-in part of the product. This cmdlet adds a trusted application to a trusted application pool and assigns a port to the external service that runs the application.

Trusted applications need to be associated with Globally Routable User Agent URIs (GRUUs), both service GRUUs and computer GRUUs. This cmdlet automatically generates these values based on the computers and services associated with the pool on which this application is homed.

When you use this cmdlet to create a trusted application, you must supply values either for the Identity parameter or for the ApplicationID and TrustedApplicationPoolFqdn parameters. The Identity is the TrustedApplicationPoolFqdn followed by a slash (/) followed by the ApplicationID. For example, TrustPool.litwareinc.com/tapp2, where TrustPool.litwareinc.com is the TrustedApplicationPoolFqdn and tapp2 is the ApplicationID.

Note that when you enter an application ID (either as part of the Identity parameter or in the ApplicationID parameter) you need to enter only the name of the application. However, the full application ID will be automatically prefixed with the string urn:application:. For example, if you enter the value tapp2 for the ApplicationID, that ID will be stored as urn:application:tapp2. Similarly, if you enter an Identity of TrustPool.litwareinc.com/tapp2, the Identity will be stored in the system as TrustPool.litwareinc.com/urn:application:tapp2.

When you specify the Port value with this cmdlet, the cmdlet does not open the port. You must open the port in the Windows firewall and any corporate firewalls in order for the trusted application to make contact with networks outside the firewall.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsTrustedApplication** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsTrustedApplication\\b"}

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
<td><p><em>ApplicationId</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name of the application. This must be a string that is unique within the pool that is specified in the TrustedApplicationPoolFqdn parameter. The string cannot contain spaces. If you supply a value for ApplicationId, you must also supply a value for the TrustedApplicationPoolFqdn parameter. You cannot specify an ApplicationId and an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Port</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>The port number on which the application will run. The port must be unique within a given pool. In other words, no other applications that use this same port can be defined on the specified pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>TrustedApplicationPoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The FQDN of the trusted application pool on which the application will reside. If you supply a value for TrustedApplicationPoolFqdn you must also supply a value for ApplicationId, but you cannot supply a value for the Identity parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableTcp</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Specifies that the trusted application will use Transmission Control Protocol (TCP). Use this parameter only if the trusted application is not a Microsoft 统一通信托管 API (UCMA) application. This is because UCMA applications support only the mutual Transport Layer Security (MTLS) protocol. If you do not specify the Force parameter with the EnableTcp parameter, you’ll receive a confirmation prompt before the new trusted application will be created.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.ExternalApplicationIdentity</p></td>
<td><p>A unique identifier for the trusted application on the pool. Identity values must be entered in the format &lt;pool FQDN&gt;/&lt;application ID&gt;, where pool FQDN is the fully qualified domain name (FQDN) of the pool on which the application resides, and application ID is the name of the application. The application ID must be unique for a given pool.</p>
<p>If you enter an Identity, you cannot specify values for the ApplicationId or TrustedApplicationPoolFqdn parameters.</p></td>
</tr>
<tr class="even">
<td><p><em>LegacyApplicationName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Use this parameter only if the application is being migrated from a Microsoft Office Communications Server 2007 R2 deployment. This value must be the same as the GRUU type of the Office Communications Server 2007 R2 version of the application in order for the two to work together.</p>
<p>Note that in most cases, setting the ApplicationId parameter equal to the GRUU type will be enough for the applications to work together. However, if the GRUU type from the Office Communications Server 2007 R2 application contains characters that are not valid in an ApplicationId, that value must be provided in the LegacyApplicationName parameter.</p>
<p>If you don’t specify a value for this parameter, the value of the Application ID will automatically be inserted (without the urn:application: prefix).</p></td>
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

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.Xds.DisplayTrustedApplication.

## 另请参阅

#### 其他资源

[Remove-CsTrustedApplication](remove-cstrustedapplication.md)  
[Set-CsTrustedApplication](set-cstrustedapplication.md)  
[Get-CsTrustedApplication](get-cstrustedapplication.md)

