---
title: New-CsWebServiceConfiguration
TOCTitle: New-CsWebServiceConfiguration
ms:assetid: 6225cf8d-b669-464e-9848-a292953e3a3a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398440(v=OCS.15)
ms:contentKeyID: 49313028
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsWebServiceConfiguration

 

_**上一次修改主题：** 2014-06-05_

Creates a new collection of Web 服务 configuration settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsWebServiceConfiguration -Identity <XdsIdentity> [-AllowAnonymousAccessToLWAConference <$true | $false>] [-AllowExternalAuthentication <$true | $false>] [-AutoLaunchLyncWebAccess <$true | $false>] [-CASigningKeyLength <UInt64>] [-Confirm [<SwitchParameter>]] [-CrossDomainAuthorizationList <PSListModifier>] [-DefaultValidityPeriodHours <UInt64>] [-EnableCertChainDownload <$true | $false>] [-EnableGroupExpansion <$true | $false>] [-Force <SwitchParameter>] [-InferCertChainFromSSL <$true | $false>] [-InMemory <SwitchParameter>] [-MACResolverUrl <String>] [-MaxCSRKeySize <UInt64>] [-MaxGroupSizeToExpand <UInt32>] [-MaxValidityPeriodHours <UInt64>] [-MinCSRKeySize <UInt64>] [-MinValidityPeriodHours <UInt64>] [-SecondaryLocationSourceUrl <String>] [-ShowAlternateJoinOptionsExpanded <$true | $false>] [-ShowDownloadCommunicatorAttendeeLink <$true | $false>] [-ShowJoinUsingLegacyClientLink <$true | $false>] [-TrustedCACerts <PSListModifier>] [-UseCertificateAuth <$true | $false>] [-UseDomainAuthInLWA <$true | $false>] [-UsePinAuth <$true | $false>] [-UseWindowsAuth <None | Negotiate | NTLM>] [-UseWsFedPassiveAuth <$true | $false>] [-WhatIf [<SwitchParameter>]] [-WsFedPassiveMetadataUri <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of Web 服务 configuration settings for the Redmond site (-Identity site:Redmond). This example includes two optional parameters: EnableGroupExpansion, which is set to False ($False); and UseCertificateAuth, which is set to True ($True). These two parameters are used to disable group expansion and enable the use of certificates for authentication, respectively.

Note that this command will fail if a collection of Web 服务 configuration settings has already been created for the Redmond site. That’s because sites are limited to a single collection of Web 服务 configuration settings.

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

## EXAMPLE 2

Example 2 is a variation of the command shown in Example 1; in this case, however, the new collection of Web 服务 configuration settings is initially created in memory only, and is only later applied to the Redmond site. In order to do this, the first command in the example uses the **New-CsWebServiceConfiguration** cmdlet to create a collection of settings for the Redmond site; the InMemory parameter is included to ensure that this collection is created in memory only and is not immediately applied to the Redmond site. (Because the settings exist only in memory, they must be stored in a variable. In this case, that’s a variable named $x.)

Commands 2 and 3 in the example take these virtual configuration settings and modify the values of the EnableGroupExpansion and UseCertificateAuth properties. After these changes have been made, the final command uses the **Set-CsWebServiceConfiguration** cmdlet to take the virtual settings and apply them to the Redmond site. If you do not call the **Set-CsWebServiceConfiguration** cmdlet, no new settings will be assigned to the site. Instead, your virtual Web 服务 configuration settings will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsWebServiceConfiguration -Identity site:Redmond -InMemory
    $x.EnableGroupExpansion = $False 
    $x.UseCertificateAuth = $True
    Set-CsWebServiceConfiguration -Instance $x

## EXAMPLE 3

The commands shown in Example 3 add the domain http://fabrikam.com to the authorized domains list for a new collection of Web service configuration settings being created for the Redmond site. To do this, the first command in the example uses the **New-CsWebOrigin** cmdlet to create a domain object for fabrikam.com. The resulting domain object is stored in a variable named $x.

The second command in the example uses the **New-CsWebServiceConfiguration** cmdlet to create the Web service configuration settings for the Redmond site. The syntax – CrossDomainAuthorizationList $x adds http://fabrikam.com to the collection of domains authorized for cross-domain scripting.

    $x = New-CsWebOrigin -Url "http://fabrikam.com"
    New-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList $x

## EXAMPLE 4

Example 4 shows how you can add multiple authorized domains to a new collection of Web service configuration settings. To add multiple domains, you must create multiple domain objects, storing each in a separate variable. In Example 4, the domain object for http://fabrikam.com is stored in a variable named $x, while the domain object for http://contoso.com is stored in a variable named $y.

After all the domain objects have been created, all you need to do is include each variable name in the parameter value for the CrossDomainAuthorizationList parameter. For example:

–CrossDomainAuthorizationList $x, $y

    $x = New-CsWebOrigin -Url "http://fabrikam.com"
    $y = New-CsWebOrigin -Url "http://contoso.com"
    New-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList $x, $y

## Detailed Description

Many Lync Server components are web-based: these components either use Web 服务 or webpages to carry out their tasks. For example, users employ a Web service when searching for new contacts in the Address Book or when using group expansion to view the individual members of a distribution group. Likewise, components ranging from dial-in conferencing to Lync Server use webpages as the interface between Lync Server and users.

The **CsWebServiceConfiguration** cmdlets enable administrators to manage Web 服务 configuration settings throughout the organization. This includes managing group expansion, certificate settings, and allowed authentication methods. Because you can configure different settings at the global, site, and service scope (albeit for only the Web Services service), you can customize Web 服务 capabilities for different users and different locations.

New Web 服务 configuration settings are created by using the **New-CsWebServiceConfiguration** cmdlet. Note that these settings can only be created at the site or service scope (and only for the Web Services service); your command will fail if you try to create a new collection at the global scope. Likewise, your command will fail if you try to create a new collection at, for instance, the Redmond site, and that site already hosts a collection of Web service settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsWebServiceConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsWebServiceConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Web 服务 configuration settings to be created. To create settings configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To create settings configured at the service scope, use syntax similar to this: -Identity &quot;service:WebServer:atl-cs-001.litwareinc.com&quot;. Note that any settings created at the service scope must be assigned to the Web Server service.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowAnonymousAccessToLWAConference</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), anonymous users will be allowed to attend Lync Web App conferences.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowExternalAuthentication</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), OAuth authentication can be used to authenticate external users.</p></td>
</tr>
<tr class="even">
<td><p><em>AutoLaunchLyncWebAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>This parameter has been deprecated for use with the on-premises version of Lync Server 2013.</p>
<p>When set to True, Lync Web App will automatically be used as the default web popup for joining an online conference, provided that the prerequisites for using Lync Web App (for example, Silverlight has been installed, and Internet Explorer is not blocking pop-up windows) have been met.</p>
<p>The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>CASigningKeyLength</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Sets the size of the certification authority (CA) signing key, the private key used by a CA to sign digital certificates. The signing key length can be set to any integer value between 2048 and 16384 bytes; the default value is 2048.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>CrossDomainAuthorizationList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of domains allowed to host web applications that send cross-domain scripting requests to the Lync Server 2013 deployment.</p>
<p>Domains to be added to the list must be created using the New-CsWebOrigin cmdlet and then added to the new collection of Web service configuration settings. Note, too that domain names must be prefaced using the http: or the https: prefix. See Example 3 of this help topic for more information.</p>
<p>This parameter was introduced in the February, 2013 release of Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><em>DefaultValidityPeriodHours</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>When using certificate authentication, clients can request the period of time (in hours) that the certificate remains valid. DefaultValidityPeriodHours represents the amount of time a certificate will remain valid if the client does not request a custom validity period.</p>
<p>DefaultValidityPeriodHours can be any integer value between 8 hours and 8760 hours (365 days). The default value is 4320 (180 days).</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableCertChainDownload</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, servers presented with an authentication certificate will download the certificate chain for that certificate. The certificate chain traces an individual certificate back to the issuing CA. Certificates will not be accepted for authentication unless the certificate’s CA is trusted.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableGroupExpansion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, group expansion will be enabled in Lync Server. With group expansion, users can configure a distribution group as a contact, and then &quot;expand&quot; that group. When a group has been expanded, users can see all the individual members of a group and their current presence information.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InferCertChainFromSSL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, servers will use the certificate information included in the Secure Sockets Layer (SSL) protocol to determine the issuing CA. Certificates will not be accepted for authentication unless the certificate’s CA is trusted.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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
<td><p>Sets the maximum size of the certificate signing request (CSR) key. (A CSR is a message sent from an applicant to a CA in order to apply for a digital certificate.) The maximum size can be set to any integer value between 1024 and 16384 bytes. The default value is 16384.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxGroupSizeToExpand</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Represents the maximum number of people that will be displayed when a group is expanded. For example, if MaxGroupSizeToExpand is set to 75, only the first 75 members of the group will be displayed any time the group is expanded.</p>
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
<td><p>Sets the minimum size of the CSR key. The minimum size can be set to any integer value between 1024 and 16384 bytes. The default value is 16384.</p></td>
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
<td><p>URL for a Web service that can process a location request. This service is typically used only when location requests cannot be resolved locally.</p></td>
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
<p>If set to True (the default value), users joining a meeting by using a client application other than Lync will see a link that points them toward a download for Lync Web App.</p></td>
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
<td><p>Collection of certificates representing certificate chains trusted by the Web server. New certificates added to the collection must be created using the <strong>New-CsWebTrustedCACertificate</strong> cmdlet.</p>
<p>This collection is not used if the InferCertChainFromSSL property is set to True.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseCertificateAuth</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value), clients can be authenticated using certificates. Set this value to False ($False) to disable certificate authentication.</p></td>
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
<td><p>When set to True (the default value), clients can be authenticated using personal identification numbers (PINs). Set this value to False ($False) to disable PIN authentication.</p></td>
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

None. The **New-CsWebServiceConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsWebServiceConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Web.WebServiceSettings object.

## 另请参阅

#### 其他资源

[Get-CsWebServiceConfiguration](get-cswebserviceconfiguration.md)  
[Remove-CsWebServiceConfiguration](remove-cswebserviceconfiguration.md)  
[Set-CsWebServiceConfiguration](set-cswebserviceconfiguration.md)

