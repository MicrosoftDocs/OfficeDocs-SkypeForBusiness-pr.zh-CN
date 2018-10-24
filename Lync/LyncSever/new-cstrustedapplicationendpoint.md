---
title: New-CsTrustedApplicationEndpoint
TOCTitle: New-CsTrustedApplicationEndpoint
ms:assetid: 78b34ba4-4c31-4f68-9069-3c7e7c162fbf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398594(v=OCS.15)
ms:contentKeyID: 49313317
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsTrustedApplicationEndpoint

 

_**上一次修改主题：** 2015-03-09_

Creates a new endpoint contact for a trusted application. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsTrustedApplicationEndpoint -ApplicationId <String> -TrustedApplicationPoolFqdn <Fqdn> [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DisplayNumber <String>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-PrimaryLanguage <String>] [-SecondaryLanguages <MultiValuedProperty>] [-SipAddress <String>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates a trusted application endpoint for the application with the Application ID tapp1 homed on the pool TrustPool.litwareinc.com. ApplicationID and TrustedApplicationPoolFqdn are the only parameters that are required to create a trusted application endpoint. However, keep in mind that assigning values to only these two parameters will auto-generate a SIP address for the contact. In order to ensure the SIP address is unique, the auto-generated address will include a globally unique identifier (GUID) and will look something like this: sip:RtcApplication-fbf9e2d1-c6aa-45a3-a045-b92d4ef961b2@litwareinc.com. If you’d like a more readable SIP address, see Example 2.

    New-CsTrustedApplicationEndpoint -ApplicationId tapp1 -TrustedApplicationPoolFqdn TrustPool.litwareinc.com

## EXAMPLE 2

Example 2 is identical to Example 1 in that it creates a trusted application endpoint for the application with the Application ID tapp1 on the TrustPool.litwareinc.com pool. Unlike Example 1, we include one more parameter in our endpoint creation: SipAddress. Rather than allowing the system to generate a SIP address, we’ve specified an address of endpoint1@litwareinc.com.

    New-CsTrustedApplicationEndpoint -ApplicationId tapp1 -TrustedApplicationPoolFqdn TrustPool.litwareinc.com -SipAddress sip:endpoint1@litwareinc.com

## Detailed Description

A trusted application endpoint is an Active Directory contact object that enables routing of calls to a trusted application. This cmdlet creates a new endpoint contact object in Active Directory 域服务 for a specified application.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsTrustedApplicationEndpoint** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsTrustedApplicationEndpoint"}

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
<td><p>The application ID of the trusted application for which the endpoint contact is being created. An application with this ID must already exist. Note that you may include only the name part of the application ID, you don’t need to (but you can) include the prefix information. For example, if the application ID is urn:application:TrustedApp1 you only need to pass the string TrustedApp1 to this parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>TrustedApplicationPoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The fully qualified domain name (FQDN) of the trusted application pool associated with the application. The application must already be associated with this pool for the endpoint to be created.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The display name of the endpoint contact object.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The telephone number of the contact as it will appear in the Address Book.</p></td>
</tr>
<tr class="even">
<td><p><em>LineURI</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The phone number of the contact. Must be in the format TEL:&lt;number&gt;, for example TEL:+14255551212.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns the results of this command. Running this cmdlet will display the newly created object; including this parameter will simply repeat that output, making the use of this parameter redundant.</p></td>
</tr>
<tr class="even">
<td><p><em>PrimaryLanguage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The primary language used for the trusted application. The language must be configured using a valid language code, such as en-US (U.S. English), fr-FR (French), etc.</p></td>
</tr>
<tr class="odd">
<td><p><em>SecondaryLanguages</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>A collection of languages that can also be used for trusted applications. Values must be configured as a comma-separated values list of language codes. For example, the following syntax sets French Canadian and French as secondary languages: -SecondaryLanguages &quot;fr-CA&quot;,&quot;fr-FR&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A SIP address for the new contact object. If you do not include a value for this parameter a SIP address will be auto-generated in the format sip:RtcApplication-&lt;GUID&gt;.&lt;domain&gt;, for example sip:RtcApplication-fbf9e2d1-c6aa-45a3-a045-b92d4ef961b2@litwareinc.com. The domain will be the default SIP domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Office 365 tenant account for which the new trusted application pool endpoint is being created. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="even">
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

Creates an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADApplicationContact.

## 另请参阅

#### 其他资源

[Remove-CsTrustedApplicationEndpoint](remove-cstrustedapplicationendpoint.md)  
[Set-CsTrustedApplicationEndpoint](set-cstrustedapplicationendpoint.md)  
[Get-CsTrustedApplicationEndpoint](get-cstrustedapplicationendpoint.md)

