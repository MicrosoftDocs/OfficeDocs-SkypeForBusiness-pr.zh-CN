---
title: Remove-CsFIPSConfiguration
TOCTitle: Remove-CsFIPSConfiguration
ms:assetid: b7e43419-0154-4fed-bfc6-9053335ce5d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205201(v=OCS.15)
ms:contentKeyID: 49314030
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsFIPSConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes one or more collections of Federal Information Processing Standards (FIPS) configuration settings. The FIPS standards are a set of United States government security standards required for use in computers maintained by non-military government agencies and by government contractors. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsFIPSConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 resets the properties in the global collection of FIPS configuration settings to their default values.

    Remove-CsFIPSConfiguration -Identity "Global"

## Detailed Description

The Federal Information Processing Standards (FIPS) are a series of standards and guidelines used by computers engaged in work for the United States government; for example, there are FIPS standards that govern the use of such things as cryptography, encryption, and digital signatures. (See <http://www.itl.nist.gov/fipspubs/by-num.htm> for more information.) Lync Server 2013 provides an option that enables the software to use only algorithms that meet the FIPS standards. If you need to work with the United States government (or with other entities that follow FIPS) then you can enable FIPS compliance in Lync Server 2013.

Keep in mind, however, that, for the on-premises version of Lync Server, you have only a single, global collection of FIPS configuration settings: FIPS compliance can only be enabled or disabled for your entire Lync Server implementation. You cannot selectively enable or disable FIPS compliance on, say, an individual site or an individual Registrar pool. If you do enable FIPS compliance, you could potentially encounter problems when trying to communicate with organizations that do not fully adhere to the FIPS standards.

By default, FIPS compliance is disabled in Lync Server 2013.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsFIPSConfiguration

**Lync Server 控制面板:** The functions carried out by the Remove-CsFIPSConfiguration cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique Identity of the FIPS configuration settings to be removed. Because Lync Server 2013 only supports a single, global collection of FIPS settings, the only collection that can be deleted is the global collection:</p>
<p>-Identity global</p>
<p>Note that, in this case, the global collection will not actually be removed from the system; Lync Server 2013 does not support the deletion of the global settings. Instead, the lone property in that collection – RequireFIPSCompliantMedia – will be reset to its default value of False.</p></td>
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
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the FIPS configuration settings being deleted. For example:</p>
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

The **Remove-CsFIPSConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.FIPSConfiguration.FIPSConfiguration object

## Return Types

None. Instead, the **Remove-CsFIPSConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.FIPSConfiguration.FIPSConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsFIPSConfiguration](get-csfipsconfiguration.md)  
[New-CsFIPSConfiguration](new-csfipsconfiguration.md)  
[Set-CsFIPSConfiguration](set-csfipsconfiguration.md)

