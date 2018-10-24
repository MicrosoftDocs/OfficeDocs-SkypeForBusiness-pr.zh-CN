---
title: Get-CsApplicationEndpoint
TOCTitle: Get-CsApplicationEndpoint
ms:assetid: 820d3bbd-0348-4272-bdb3-c3d612d0836a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398655(v=OCS.15)
ms:contentKeyID: 49313439
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsApplicationEndpoint

 

_**上一次修改主题：** 2015-03-09_

Retrieves endpoints for the 应用程序服务. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsApplicationEndpoint [-Identity <UserIdParameter>] [-ApplicationId <String>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-OU <OUIdParameter>] [-PoolFqdn <Fqdn>] [-ResultSize <Unlimited>]

## Examples

## EXAMPLE 1

This example retrieves information about all application endpoints defined within the Lync Server deployment.

    Get-CsApplicationEndpoint

## EXAMPLE 2

Example 2 retrieves all application endpoints that have the string “endpoint” anywhere within their display name. To do this, the command uses the Filter parameter. The value of the parameter filters to find endpoint objects that have a display name (DisplayName) that contains (-like) the string endpoint (\*endpoint\* - the wildcard characters indicate that any characters can come before or after the string endpoint, meaning endpoint can be anywhere within the display name).

    Get-CsApplicationEndpoint -Filter {DisplayName -like "*endpoint*"}

## EXAMPLE 3

Example 3 returns all application endpoints associated with the application urn:application:tapp2. This is accomplished by passing the ID tapp2 to the ApplicationId parameter. Notice that we didn’t supply a pool FQDN; this means that if an application with the ID tapp2 exists on more than one pool, endpoints for all those applications will be retrieved. The next part of this command pipes the returned object or objects to the **Select-Object** cmdlet, which displays only the Identity, SipAddress, DisplayName, and OwnerUrn properties of those objects.

    Get-CsApplicationEndpoint -ApplicationId tapp2 | Select-Object Identity, SipAddress, DisplayName, OwnerUrn

## Detailed Description

This cmdlet retrieves one or more application contacts from Active Directory 域服务. These objects are stored in Active Directory in the Application Contacts container of the RTC service.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsApplicationEndpoint** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsApplicationEndpoint"}

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
<td><p>The application ID of the application endpoint you want to retrieve. The application ID is the value of the endpoint’s OwnerUrn property. For example, if the OwnerUrn property has a value of urn:application:Caa, the application ID is urn:application:Caa. However, you can enter only the suffix, in this case Caa, to retrieve the endpoint. For example: -ApplicationId Caa</p></td>
</tr>
<tr class="even">
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Alternate credentials under which the Get operation will proceed. You can retrieve a PSCredential object by calling the Windows PowerShell cmdlet <strong>Get-Credential</strong>.</p></td>
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
<td><p>The Identity, SIP address, or display name of the application endpoint to retrieve. The Identity consists of the distinguished name of the endpoint. This will typically contain a globally unique identifier (GUID) as part of the CN, for example: CN={8811fefe-e0bb-4fab-ae39-7aaeddd423dc},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=Vdomain,DC=com.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>The organizational unit (OU) in which the endpoint resides.</p></td>
</tr>
<tr class="odd">
<td><p><em>PoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The fully qualified domain name (FQDN) of the pool on which the application endpoint resides.</p></td>
</tr>
<tr class="even">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>The maximum number of endpoint records to retrieve.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. Accepts a pipelined string value representing the Identity of the application endpoint.

## Return Types

Retrieves an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADApplicationContact.

## 另请参阅

#### 其他资源

[Move-CsApplicationEndpoint](move-csapplicationendpoint.md)

