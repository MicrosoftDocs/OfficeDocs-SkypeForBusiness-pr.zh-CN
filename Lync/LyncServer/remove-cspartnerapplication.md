---
title: Remove-CsPartnerApplication
TOCTitle: Remove-CsPartnerApplication
ms:assetid: 3918a2eb-d464-4729-888b-fafebe2227ce
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204820(v=OCS.15)
ms:contentKeyID: 49312510
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPartnerApplication

 

_**上一次修改主题：** 2015-03-09_

Removes an existing partner application. A partner application is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPartnerApplication -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 deletes the partner application with the Identity "MicrosoftExchange".

    Remove-CsPartnerApplication -Identity "MicrosoftExchange"

## Example 2

In Example 2, all the partner applications configured for use in the organization are deleted. To do this, the command first uses the **Get-CsPartnerApplication** cmdlet in order to return a collection of all the partner applications. This collection is then piped to the **Remove-CsPartnerApplication** cmdlet, which deletes each application in the collection.

    Get-CsPartnerApplication | Remove-CsPartnerApplication

## Example 3

In Example 3, all the partner applications where the trust level is set to anything other than Full are deleted. To carry out this task, the command first calls the **Get-CsPartnerApplication** cmdlet without any parameters in order to return a collection of all the partner applications configured for use in the organization. This collection is then piped to the Where-Object cmdlet, which selects only those applications where the ApplicationTrustLevel property is not equal to (-ne) "Full". The applications that meet that criterion are then piped to, and removed by, the **Remove-CsPartnerApplication** cmdlet.

    Get-CsPartnerApplication | Where-Object {$_.ApplicationTrustLevel -ne "Full"} | Remove-CsPartnerApplication

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Exchange 2013 to share information) is carried out using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, you will need to configure the other server product (e.g., Exchange 2013) as a partner application. (You will also need to configure Lync Server 2013 as a partner application for the other server product.) In Lync Server 2013, partner applications are managed by using the **CsPartnerApplication** cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPartnerApplication"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsPartnerApplication** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier of the partner application to be removed. For example:</p>
<p>-Identity &quot;MicrosoftExchange&quot;</p>
<p>Note that you cannot use wildcard characters when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the partner application being deleted. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsPartnerApplication** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.PartnerApplication\#Decorated object.

## Return Types

None. Instead, the **Remove-CsPartnerApplication** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.PartnerApplication\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsPartnerApplication](get-cspartnerapplication.md)  
[New-CsPartnerApplication](new-cspartnerapplication.md)  
[Set-CsPartnerApplication](set-cspartnerapplication.md)

