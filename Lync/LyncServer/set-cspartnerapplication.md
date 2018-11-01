---
title: Set-CsPartnerApplication
TOCTitle: Set-CsPartnerApplication
ms:assetid: 29c8c511-157b-478e-814f-b911955a8251
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204755(v=OCS.15)
ms:contentKeyID: 49312320
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPartnerApplication

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing partner application. A partner application is any application that Skype for Business Online can directly exchange security tokens with, without having to go through a third-party security token server. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPartnerApplication -Identity <XdsGlobalRelativeIdentity> [-AcceptSecurityIdentifierInformation <$true | $false>] [-ApplicationTrustLevel <User | Application | Full>] [-Enabled <$true | $false>] [-Tenant <Guid>] <COMMON PARAMETERS>

    Set-CsPartnerApplication -Identity <XdsGlobalRelativeIdentity> -MetadataUrl <String> [-AcceptSecurityIdentifierInformation <$true | $false>] [-ApplicationTrustLevel <User | Application | Full>] [-Enabled <$true | $false>] [-Tenant <Guid>] <COMMON PARAMETERS>

    Set-CsPartnerApplication -CertificateRawData <String> -Identity <XdsGlobalRelativeIdentity> [-AcceptSecurityIdentifierInformation <$true | $false>] [-ApplicationTrustLevel <User | Application | Full>] [-Enabled <$true | $false>] [-Tenant <Guid>] <COMMON PARAMETERS>

    Set-CsPartnerApplication -CertificateFileData <String> -Identity <XdsGlobalRelativeIdentity> [-AcceptSecurityIdentifierInformation <$true | $false>] [-ApplicationTrustLevel <User | Application | Full>] [-Enabled <$true | $false>] [-Tenant <Guid>] <COMMON PARAMETERS>

    Set-CsPartnerApplication -Identity <XdsGlobalRelativeIdentity> -UseOAuthServer <SwitchParameter> [-AcceptSecurityIdentifierInformation <$true | $false>] [-ApplicationTrustLevel <User | Application | Full>] [-Enabled <$true | $false>] [-Tenant <Guid>] <COMMON PARAMETERS>

    Set-CsPartnerApplication [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 disables the partner application MicrosoftExchange. This is done by setting the Enabled property to False ($False).

    Set-CsPartnerApplication -Identity "MicrosoftExchange" -Enabled $False

## Example 2

In Example 2, all the partner applications currently in use in the organization are disabled. To do this, the command first uses the **Get-CsPartnerApplication** cmdlet to return a collection of all the partner applications. This collection is then piped to the **ForEach-Object** cmdlet. In turn, the **ForEach-Object** cmdlet runs the **Set-CsPartnerApplication** cmdlet against each application in the collection. Doing so disables each of those partner applications.

    Get-CsPartnerApplication | ForEach-Object {Set-CsPartnerApplication -Identity $_.Identity -Enabled $False}

## Example 3

Example 3 disables all partner applications where the ApplicationTrustLevel property is set to User. To carry out this task, the command first calls the **Get-CsPartnerApplication** cmdlet without any parameters; that returns a collection of all the partner applications configured for use in the organization. This collection is then piped to the Where-Object cmdlet, which picks out only those applications where the ApplicationTrustLevel property is equal to "User". That filtered collection is then piped to the **ForEach-Object** cmdlet, which uses the **Set-CsPartnerApplication** cmdlet to take each item in the collection and set the Enabled property to $False.

    Get-CsPartnerApplication | Where-Object {$_.ApplicationTrustLevel -eq "User"} | ForEach-Object {Set-CsPartnerApplication -Identity $_.Identity -Enabled $False}

## Detailed Description

In Skype for Business Online, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Exchange 2013 to share information) is carried out using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, you will need to configure the other server product (e.g., Exchange 2013) as a partner application. (You will also need to configure Lync Server 2013 as a partner application for the other server product.) In Lync Server 2013, partner applications are managed by using the **CsPartnerApplication** cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPartnerApplication"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsPartnerApplication** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier of the partner application. For example:</p>
<p>-Identity &quot;MicrosoftExchange&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>MetadataUrl</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>URL of the security token servicer federation metadata that carries the signing keys, the issuer identifier, and the issuer endpoint URL.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseOAuthServer</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>When present, the partner application will use the configured OAuth Server for server-to-server authentication. When not present, the partner application will use its built-in security token service for server-to-server authentication.</p></td>
</tr>
<tr class="even">
<td><p><em>AcceptSecurityIdentifierInformation</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True ($True), security identifiers (SIDs) can be used for authentication purposes. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>ApplicationTrustLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>ApplicationTrustLevel</p></td>
<td><p>Specifies the level of trust between Lync Server 2013 and the partner application. Allowed values are:</p>
<p>* Full -- The partner application is trusted to represent itself and to impersonate any user in the realm. This is the default value.</p>
<p>* Application -- The partner application is trusted to represent itself within the realm. In order to impersonate a user, it must obtain consent through from a security token server.</p>
<p>* User -- The partner application must obtain consent from a security token server in order to represent a user, and cannot represent itself.</p>
<p>The default value is Full.</p></td>
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
<td><p>When set to True, the partner application is available for use with Lync Server 2013. When set to False the partner application will continue to run, but will not be able to communicate with Lync Server until the Enabled property has been set to True.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the partner application being modified. For example:</p>
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

None. The **Set-CsPartnerApplication** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Set-CsPartnerApplication** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.PartnerApplication\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsPartnerApplication](get-cspartnerapplication.md)  
[New-CsPartnerApplication](new-cspartnerapplication.md)  
[Remove-CsPartnerApplication](remove-cspartnerapplication.md)

