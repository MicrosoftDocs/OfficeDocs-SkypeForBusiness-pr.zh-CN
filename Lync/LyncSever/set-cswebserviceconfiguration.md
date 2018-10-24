---
title: Set-CsWebServiceConfiguration
TOCTitle: Set-CsWebServiceConfiguration
ms:assetid: 5aa0316d-afd8-4cc2-b606-0e720e6ab021
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398396(v=OCS.15)
ms:contentKeyID: 49312953
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsWebServiceConfiguration

 

_**上一次修改主题：** 2014-06-05_

Modifies an existing collection of Web 服务 configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsWebServiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsWebServiceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AllowAnonymousAccessToLWAConference <$true | $false>] [-AllowExternalAuthentication <$true | $false>] [-AutoLaunchLyncWebAccess <$true | $false>] [-CASigningKeyLength <UInt64>] [-Confirm [<SwitchParameter>]] [-CrossDomainAuthorizationList <PSListModifier>] [-DefaultValidityPeriodHours <UInt64>] [-EnableCertChainDownload <$true | $false>] [-EnableGroupExpansion <$true | $false>] [-Force <SwitchParameter>] [-InferCertChainFromSSL <$true | $false>] [-MACResolverUrl <String>] [-MaxCSRKeySize <UInt64>] [-MaxGroupSizeToExpand <UInt32>] [-MaxValidityPeriodHours <UInt64>] [-MinCSRKeySize <UInt64>] [-MinValidityPeriodHours <UInt64>] [-SecondaryLocationSourceUrl <String>] [-ShowAlternateJoinOptionsExpanded <$true | $false>] [-ShowDownloadCommunicatorAttendeeLink <$true | $false>] [-ShowJoinUsingLegacyClientLink <$true | $false>] [-TrustedCACerts <PSListModifier>] [-UseCertificateAuth <$true | $false>] [-UseDomainAuthInLWA <$true | $false>] [-UsePinAuth <$true | $false>] [-UseWindowsAuth <None | Negotiate | NTLM>] [-UseWsFedPassiveAuth <$true | $false>] [-WhatIf [<SwitchParameter>]] [-WsFedPassiveMetadataUri <String>]

## Examples

## EXAMPLE 1

Example 1 enables group expansion for the Web 服务 configuration settings applied to the Redmond site (-Identity site:Redmond). This is done by including the EnableGroupExpansion property and setting the parameter value to True.

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

## EXAMPLE 2

In Example 2, the maximum validity period for all the Web 服务 configuration settings applied at the site scope is changed to 16 hours. To carry out this task, the **Get-CsWebServiceConfiguration** cmdlet is called along with the Filter parameter; the filter value "site:\*" limits the returned data to settings where the Identity begins with the characters "site:". This collection is then piped to the **Set-CsWebServiceConfiguration** cmdlet, which takes each item in the collection and changes the MaxValidityPeriodHours property to 16.

    Get-CsWebServiceConfiguration -Filter "site:*" | Set-CsWebServiceConfiguration -MaxValidityPeriodHours 16

## EXAMPLE 3

In Example 3, the group expansion size is set to 400 for each collection of Web 服务 configuration settings that allow group expansion. To do this, the **Get-CsWebServiceConfiguration** cmdlet is called without any parameters; this returns a collection of all the Web 服务 configuration settings used in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableGroupExpansion property is equal to True. In turn, this filtered collection is piped to the **Set-CsWebServiceConfiguration** cmdlet, which takes each item in the collection and sets the value of the MaxGroupSizeToExpand property to 400.

    Get-CsWebServiceConfiguration | Where-Object {$_.EnableGroupExpansion -eq $True} | Set-CsWebServiceConfiguration -MaxGroupSizeToExpand 400

## EXAMPLE 4

The command shown in Example 4 shows how the global Web 服务 settings can be configured so that any person joining a meeting using a client application other than Lync will first be shown a link to a site where he or she can download Lync Web App. This is done by including the ShowDownloadCommunicatorAttendeeLink parameter and setting the parameter value to $True.

    Set-CsWebServiceConfiguration -Identity global -ShowDownloadCommunicatorAttendeeLink $True 

## EXAMPLE 5

The commands shown in Example 5 add the domain http://fabrikam.com to an existing collection of Web service configuration settings. To carry out this task, the first command in the example uses the **New-CsWebOrigin** cmdlet to create a domain object for fabrikam.com. The resulting domain object is stored in a variable named $x.

The second command in the example uses the **Set-CsWebServiceConfiguration** cmdlet to add http://fabrikam.com to the Web service configuration settings applied to the Redmond site. The syntax @{Add=$x} adds the domain to any domains already in the collection of domains authorized for cross-domain scripting. To replace the existing collection with just http://fabrikam.com use the syntax @{Replace=$x}.

    $x = New-CsWebOrigin -Url "http://fabrikam.com"
    Set-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList @{Add=$x}

## EXAMPLE 6

In Example 6, the first domain listed in the collection of domains authorized for cross-domain scripting is removed from the web service configuration settings for the Redmond site. To carry out this task, the first command in the example uses the **Get-CsWebServiceConfiguration** cmdlet to return the current settings for the Redmond site. Those values are stored in a variable named $x.

In the second command, the RemoveAt method is used to remove the first domain from the CrossDomainAuthorizationList property. Domains are stored in this property as arrays, with the first domain having an index number of 0, the second domain having an index number of 1, and so on. To remove the second domain (index number 1) from the CrossDomainAuthorizationList property you would use this syntax:

$x.CrossDomainAuthorizationList.RemoveAt(1)

Note that command 2 removes the domain from the copy of the Redmond site stored in the variable $x, and not from the site itself. To actually remove the domain from the Redmond site, the third command in the example uses the **Set-CsWebServiceConfiguration** cmdlet and the Instance parameter to overwrite settings for the Redmond site with the settings stored in $x.

    $x = Get-CsWebServiceConfiguration -Identity "site:Redmond"
    $x.CrossDomainAuthorizationList.RemoveAt(0)
    Set-CsWebServiceConfguration -Instance $x

## EXAMPLE 7

The command shown in Example 7 modifies the web service configuration settings for the Redmond site by removing all the domains that are authorized for cross-domain scripting. This is done by setting the CrossDomainAuthorizationList property to a null value ($Null).

    Set-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList $Null

## Detailed Description

Many Lync Server components are web-based: these components either use Web 服务 or webpages to carry out their tasks. For example, users employ a web service when searching for new contacts in the Address Book or when using group expansion to view the individual members of a distribution group. Likewise, components ranging from dial-in conferencing to Lync Server 控制面板 use webpages as the interface between Lync Server and users.

The **CsWebServiceConfiguration** cmdlets enable administrators to manage Web 服务 configuration settings throughout the organization. This includes managing group expansion, certificate settings, and allowed authentication methods. Because you can configure different settings at the global, site, and service scope (albeit for the only the Web Services service), you can customize Web 服务 capabilities for different users and different locations. The **CsWebServiceConfiguration** cmdlets enable administrators to manage Web 服务 configuration settings throughout the organization. This includes managing group expansion; certificate settings; and allowed authentication methods. Because you can configure different settings at the global, site, and service scope (Web Services service only) you can customize Web 服务 capabilities for different users and different locations.

Custom settings (for example, custom validity periods for certificates) can be specified at the time you create a new Web 服务 configuration setting collection. Alternatively, you can modify the property values for an existing collection by using the **Set-CsWebServiceConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsWebServiceConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsWebServiceConfiguration"}

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
<td><p><em>AllowAnonymousAccessToLWAConference</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, anonymous users will be allowed to attend Lync Web App conferences.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowExternalAuthentication</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), OAuth authentication can be used to authenticate external users.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>AutoLaunchLyncWebAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter has been deprecated for use with the on-premises version of Lync Server 2013.</p>
<p>When set to True, Lync Web App will automatically be used as the default web popup for joining an online conference, provided that the prerequisites for using Lync Web App (for example, Silverlight has been installed, and Internet Explorer is not blocking pop-up windows) have been met.</p>
<p>The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>CASigningKeyLength</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Sets the size of the CA signing key, the private key used by a certification authority (CA) to sign digital certificates. The signing key length can be set to any integer value between 2048 and 16384 bytes; the default value is 2048.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>CrossDomainAuthorizationList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of domains allowed to host web applications that send cross-domain scripting requests to the Lync Server 2013 deployment.</p>
<p>Domains to be added to the list must be created using the New-CsWebOrigin cmdlet and then added to the new collection of Web service configuration settings. Note, too that domain names must be prefaced using the http: or the https: prefix. See Examples 5, 6, and 7 of this help topic for more information.</p>
<p>This parameter was introduced in the February, 2013 release of Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultValidityPeriodHours</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>When using certificate authentication, clients can request the period of time (in hours) that the certificate remains valid. DefaultValidityPeriodHours represents the amount of time a certificate will remain valid if the client does not request a custom validity period.</p>
<p>DefaultValidityPeriodHours can be any integer value between 8 hours and 8760 hours (365 days). The default value is 4320 (180 days).</p></td>
</tr>
<tr class="even">
<td><p><em>EnableCertChainDownload</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, servers presented with an authentication certificate will download the certificate chain for that certificate. The certificate chain traces an individual certificate back to the issuing CA. Certificates will not be accepted for authentication unless the certificate’s CA is trusted.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableGroupExpansion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, group expansion will be enabled in Lync. With group expansion, users can configure a distribution group as a contact, then &quot;expand&quot; that group. When a group has been expanded, users can see the individual members of a group and their current presence information.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts or non-fatal error messages that might occur when you run the cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Web 服务 configuration settings to be modified. To modify settings configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To modify settings configured at the service scope, use syntax similar to this: -Identity &quot;service:WebServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>To modify settings configured at the global scope, you can use this syntax: -identity global.</p>
<p>If the Identity parameter is not used then the <strong>Set-CsWebServiceConfiguration</strong> cmdlet will automatically modify the global collection.</p></td>
</tr>
<tr class="even">
<td><p><em>InferCertChainFromSSL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, servers will use the certificate information included in the Secure Sockets Layer (SSL) protocol to determine the issuing CA. Certificates will not be accepted for authentication unless the certificate’s CA is trusted.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>WebServiceSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>MACResolverUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for a Web service capable of performing Media Access Control (MAC) resolution. MAC resolution involves taking the MAC address of a connected client and returning the chassis and port IDs of the network switch that client is connected to. MAC resolution is used by the Enhanced 9-1-1 service.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxCSRKeySize</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Sets the maximum size of the Certificate Signing Request (CSR) key. (A CSR is a message sent from an applicant to a CA in order to apply for a digital certificate.) The maximum size for a CSR key can be set to any integer value between 1024 and 16384 bytes. The default value is 16384.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxGroupSizeToExpand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Represents the maximum number of people that will be displayed when a group is expanded. For example, if MaxGroupSizeToExpand is set to 75 only the first 75 members of the group will be displayed any time the group is expanded.</p>
<p>MaxGroupSizeToExpand can be set to any integer value between 1 and 1000, inclusive. The default value is 100.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxValidityPeriodHours</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>When using certificate authentication, clients can request the period of time (in hours) that the certificate remains valid. MaxValidityPeriodHours represents the maximum amount of time a client can request.</p>
<p>MaxValidityPeriodHours can be any integer value between 8 hours and 8760 hours (365 days). The default value is 8760.</p></td>
</tr>
<tr class="even">
<td><p><em>MinCSRKeySize</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Sets the minimum size of the Certificate Signing Request (CSR) key. The minimum size can be set to any integer value between 1024 and 16384 bytes. The default value is 16384.</p></td>
</tr>
<tr class="odd">
<td><p><em>MinValidityPeriodHours</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>When using certificate authentication, clients can request the period of time (in hours) that the certificate remains valid. MinValidityPeriodHours represents the minimum amount of time a client can request.</p>
<p>MinValidityPeriodHours can be any integer value between 8 hours and 4320 hours (180 days). The default value is 8.</p></td>
</tr>
<tr class="even">
<td><p><em>SecondaryLocationSourceUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for a web service that can process a location request. This service is only used when location requests cannot be resolved locally.</p></td>
</tr>
<tr class="odd">
<td><p><em>ShowAlternateJoinOptionsExpanded</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter has been deprecated for use with the on-premises version of Lync Server 2013.</p>
<p>When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</p></td>
</tr>
<tr class="even">
<td><p><em>ShowDownloadCommunicatorAttendeeLink</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter has been deprecated for use with the on-premises version of Lync Server 2013.</p>
<p>If set to True (the default value), users joining a meeting by using a client application other than Lync will see a link that points them to a download for Lync Web App.</p></td>
</tr>
<tr class="odd">
<td><p><em>ShowJoinUsingLegacyClientLink</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter has been deprecated for use with the on-premises version of Lync Server 2013.</p>
<p>If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using their current client application. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>TrustedCACerts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of certificates representing certificate chains trusted by the Web Server. New certificates added to the collection must be created by using the <strong>New-CsWebTrustedCACertificate</strong> cmdlet.</p>
<p>This collection is not used if the InferCertChainFromSSL property is set to True.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseCertificateAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), clients can be authenticated using certificates. Set this value to False to disable certificate authentication.</p></td>
</tr>
<tr class="even">
<td><p><em>UseDomainAuthInLWA</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, domain authentication can be employed as a way to authenticate Lync Web App users.</p></td>
</tr>
<tr class="odd">
<td><p><em>UsePinAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), clients can be authenticated using personal identification numbers (PINs). Set this value to False to disable PIN authentication.</p></td>
</tr>
<tr class="even">
<td><p><em>UseWindowsAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Web.UseWindowsAuth</p></td>
<td><p>Determines how (and if) users will be authenticated using Windows authentication; that is, using the same credentials they used when they logged on to Windows. Valid values are:</p>
<p>Negotiate – The client and server will work together to determine the proper authentication protocol (either Kerberos or NTLM).</p>
<p>NTLM – Windows authentication will be allowed, but only using the NTLM protocol.</p>
<p>None – Windows authentication will not be allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseWsFedPassiveAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, allows for passive authentication: authentication of users by using URL redirection or smart linking. The default value is False ($False).</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
<tr class="odd">
<td><p><em>WsFedPassiveMetadataUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URI used by the WS-federation Web requestor protocol.</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.Web.WebServiceSettings object. The **Set-CsWebServiceConfiguration** cmdlet accepts pipelined input of the Web 服务 settings object.

## Return Types

The **Set-CsWebServiceConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Web.WebServiceSettings object.

## 另请参阅

#### 其他资源

[Get-CsWebServiceConfiguration](get-cswebserviceconfiguration.md)  
[New-CsWebServiceConfiguration](New-CsWebServiceConfiguration.md)  
[Remove-CsWebServiceConfiguration](remove-cswebserviceconfiguration.md)

