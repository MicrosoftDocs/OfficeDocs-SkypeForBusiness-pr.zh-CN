---
title: Get-CsTrustedApplicationEndpoint
TOCTitle: Get-CsTrustedApplicationEndpoint
ms:assetid: f66ac464-31ef-4aa3-9b79-f9e67ebc1475
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413035(v=OCS.15)
ms:contentKeyID: 49314763
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTrustedApplicationEndpoint

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about one or more trusted application endpoints. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsTrustedApplicationEndpoint [-Identity <UserIdParameter>] [-ApplicationId <String>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-OU <OUIdParameter>] [-ResultSize <Unlimited>] [-TrustedApplicationPoolFqdn <Fqdn>]

## Examples

## EXAMPLE 1

This example retrieves information about all trusted application endpoints defined within the Lync Server deployment.

    Get-CsTrustedApplicationEndpoint

## EXAMPLE 2

Example 2 retrieves information about the application endpoint contact with the SIP address endpoint1@litwareinc.com. Note that the sip: prefix is required when using a SIP address as the Identity.

    Get-CsTrustedApplicationEndpoint -Identity "sip:endpoint1@litwareinc.com"

## EXAMPLE 3

Example 3 retrieves all trusted application endpoints that have the string “endpoint” anywhere within their display name. To do this, the command uses the Filter parameter. The value of the parameter filters to find endpoint objects that have a display name (DisplayName) that contains (-like) the string endpoint (\*endpoint\* - the wildcard characters indicate that any characters can come before or after the string endpoint, meaning endpoint can be anywhere within the display name).

    Get-CsTrustedApplicationEndpoint -Filter {DisplayName -like "*endpoint*"}

## EXAMPLE 4

Example 4 will return all trusted application endpoints associated with the application tapp2. This is accomplished by passing the ID tapp2 to the ApplicationId parameter. Notice that we didn’t supply a pool FQDN; this means that if an application with the ID tapp2 exists on more than one pool, endpoints for all those applications will be retrieved. The next part of this command pipes the returned object or objects to the **Select-Object** cmdlet, which displays only the SipAddress, DisplayName, and OwnerUrn properties of those objects.

    Get-CsTrustedApplicationEndpoint -ApplicationId tapp2 | Select-Object SipAddress, DisplayName, OwnerUrn

## Detailed Description

A trusted application endpoint is an Active Directory contact object that enables routing of calls to a trusted application. This cmdlet retrieves one or more existing endpoint contact objects in Active Directory 域服务.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsTrustedApplicationEndpoint** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsTrustedApplicationEndpoint"}

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
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The application ID of the trusted application for the endpoint you want to retrieve.</p></td>
</tr>
<tr class="even">
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Alternate credentials to be used to retrieve the endpoint. You can retrieve a PSCredential object by calling the <strong>Get-Credential</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Allows you to specify a domain controller. If no domain controller is specified, the first available will be used.</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on specific attributes for Lync Server. For example, you can limit returned data to contacts whose display names or SIP addresses match a certain wildcard pattern.</p>
<p>The Filter parameter uses the same Windows PowerShell filtering syntax that is used by the <strong>Where-Object</strong> cmdlet. For example, a filter that returns only contacts that have been enabled for Enterprise Voice would look like this: {EnterpriseVoiceEnabled -eq $True}, with EnterpriseVoiceEnabled representing the Active Directory attribute, -eq representing the comparison operator (equal to), and $True (a built-in Windows PowerShell variable) representing the filter value.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>The Identity (distinguished name), SIP address, or display name of the application endpoint to be modified.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>The OU in which the endpoint resides.</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>The maximum number of endpoint records to retrieve.</p></td>
</tr>
<tr class="even">
<td><p><em>TrustedApplicationPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The fully qualified domain name (FQDN) of the trusted application pool associated with the application for the endpoint you want to retrieve.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. Accepts a pipelined string value representing the Identity of a user account.

## Return Types

Retrieves an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADApplicationContact.

## 另请参阅

#### 其他资源

[New-CsTrustedApplicationEndpoint](new-cstrustedapplicationendpoint.md)  
[Remove-CsTrustedApplicationEndpoint](remove-cstrustedapplicationendpoint.md)  
[Set-CsTrustedApplicationEndpoint](set-cstrustedapplicationendpoint.md)

