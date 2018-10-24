---
title: New-CsPartnerApplication
TOCTitle: New-CsPartnerApplication
ms:assetid: 0248acde-626d-42b4-a071-c96171364a18
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204628(v=OCS.15)
ms:contentKeyID: 49311815
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPartnerApplication

 

_**上一次修改主题：** 2015-03-09_

Creates a new partner application. A partner application is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsPartnerApplication -ApplicationIdentifier <String> -ApplicationTrustLevel <User | Application | Full> -CertificateRawData <String> -Realm <String> [-AcceptSecurityIdentifierInformation <$true | $false>] [-Enabled <$true | $false>] [-Identity <XdsGlobalRelativeIdentity>] [-Tenant <Guid>] <COMMON PARAMETERS>

    New-CsPartnerApplication -ApplicationIdentifier <String> -ApplicationTrustLevel <User | Application | Full> -CertificateFileData <String> -Realm <String> [-AcceptSecurityIdentifierInformation <$true | $false>] [-Enabled <$true | $false>] [-Identity <XdsGlobalRelativeIdentity>] [-Tenant <Guid>] <COMMON PARAMETERS>

    New-CsPartnerApplication -ApplicationIdentifier <String> -ApplicationTrustLevel <User | Application | Full> -UseOAuthServer <SwitchParameter> [-AcceptSecurityIdentifierInformation <$true | $false>] [-Enabled <$true | $false>] [-Identity <XdsGlobalRelativeIdentity>] [-Realm <String>] [-Tenant <Guid>] <COMMON PARAMETERS>

    New-CsPartnerApplication -ApplicationTrustLevel <User | Application | Full> -MetadataUrl <String> [-AcceptSecurityIdentifierInformation <$true | $false>] [-Enabled <$true | $false>] [-Identity <XdsGlobalRelativeIdentity>] [-Tenant <Guid>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 creates a new partner application with the Identity "MicrosoftExchange". In this example, the new partner application uses the metadata URL https://autodiscover.litwareinc.com/metadata/json/1.

    New-CsPartnerApplication -Identity "MicrosoftExchange" -ApplicationTrustLevel "Full" -MetadataUrl"https://autodiscover.litwareinc.com/metadata/json/1"

## Example 2

The command shown in Example 2 also creates a new partner application with the Identity "MicrosoftExchange". In this case, however, the new partner application does not use a metadata URL but, instead, is configured to use a predefined OAuth Server. To do this, the command uses the UseOAuthServer parameter instead of the MetadataUrl parameter.

    New-CsPartnerApplication -Identity "MicrosoftExchange" -ApplicationIdentifier "microsoft.exchange" -ApplicationTrustLevel "Full" -UseOAuthServer

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Exchange 2013 to share information) is carried out by using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, you will need to configure the other server product (e.g., Exchange 2013) as a partner application. (You will also need to configure Lync Server 2013 as a partner application for the other server product.) In Lync Server 2013, partner applications are managed by using the **CsPartnerApplication** cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPartnerApplication"}

**Lync Server 控制面板:** The functions carried out by the **New-CsPartnerApplication** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>ApplicationIdentifier</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Unique identifier for the partner application. The ApplicationIdentifier is provided by the server application. You cannot use the ApplicationIdentifier parameter and the MetadataUrl parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>ApplicationTrustLevel</em></p></td>
<td><p>Required</p></td>
<td><p>ApplicationTrustLevel</p></td>
<td><p>Specifies the level of trust between Lync Server 2013 and the partner application. Allowed values are:</p>
<p>* Full -- The partner application is trusted to represent itself and to impersonate any user in the realm. This is the default value.</p>
<p>* Application -- The partner application is trusted to represent itself within the realm. In order to impersonate a user, it must obtain consent through from a security token server.</p>
<p>* User -- The partner application must obtain consent from a security token server in order to represent a user, and cannot represent itself.</p>
<p>The default value is Full.</p></td>
</tr>
<tr class="odd">
<td><p><em>CertificateFileData</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Path to a certificate file that can be assigned to the partner application. For example:</p>
<p>-CertificateFileData &quot;C:\Certificates\PartnerApplication.cer&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>CertificateRawData</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Certificate (in Base64 encoded format) that can be assigned to the partner application. To read raw data from a certificate and then convert that data to the required format, use commands similar to these:</p>
<p>$x = Get-Content &quot;C:\Certificates\PartnerApplication.cer&quot; –Encoding Byte</p>
<p>$y = [Convert]::ToBase64String($x)</p>
<p>You can then use this syntax to assign the certificate data stored in the variable $y:</p>
<p>-CertificateRawData $y</p></td>
</tr>
<tr class="odd">
<td><p><em>MetadataUrl</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>URL where the WS-FederationMetadata for the partner application is published. Partner applications use the metadata to agree on the types of tokens that will be exchanged as well the keys that will be used to sign these tokens.</p></td>
</tr>
<tr class="even">
<td><p><em>UseOAuthServer</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>When present, indicates that the partner application will use one of the pre-authorized OAuth servers instead of a security token server built into the application itself.</p></td>
</tr>
<tr class="odd">
<td><p><em>AcceptSecurityIdentifierInformation</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True ($True), security identifiers (SIDs) can be used for authentication purposes. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True the partner application will be enabled and available for immediate use. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the new partner application.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Realm</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Server-to-server security container. By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new partner application is being created. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsPartnerApplication** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPartnerApplication** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.PartnerApplication\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsPartnerApplication](get-cspartnerapplication.md)  
[Remove-CsPartnerApplication](remove-cspartnerapplication.md)  
[Set-CsPartnerApplication](set-cspartnerapplication.md)

