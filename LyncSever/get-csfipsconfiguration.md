---
title: Get-CsFIPSConfiguration
TOCTitle: Get-CsFIPSConfiguration
ms:assetid: 56d29011-187f-4034-a5ed-71625087bf36
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204904(v=OCS.15)
ms:contentKeyID: 49312897
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsFIPSConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Federal Information Processing Standards (FIPS) configuration settings currently in use in the organization. The FIPS standards are a set of United States government security standards required for use in computers maintained by non-military government agencies and by government contractors. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsFIPSConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsFIPSConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>] [-Tenant <Guid>]

## Examples

## Example 1

The command shown in Example 1 returns information for all the FIPS configuration settings currently in use in the organization. Note that there is only a single, global instance of FIPS configuration settings.

    Get-CsFIPSConfiguration

## Detailed Description

The Federal Information Processing Standards (FIPS) are a series of standards and guidelines used by computers engaged in work for the US government; for example, there are FIPS standards that govern the use of such things as cryptography, encryption, and digital signatures. (See <http://www.itl.nist.gov/fipspubs/by-num.htm> for more information.) Lync Server 2013 provides an option that enables the software to use only algorithms that meet the FIPS standards. If you need to work with the United States government (or with other entities that follow FIPS) then you can enable FIPS compliance in Lync Server 2013.

Keep in mind, however, that, for the on-premises version of Lync Server, you have only a single, global collection of FIPS configuration settings: FIPS compliance can only be enabled or disabled for your entire Lync Server implementation. You cannot selectively enable or disable FIPS compliance on, say, an individual site or an individual Registrar pool. If you do enable FIPS compliance, you could potentially encounter problems when trying to communicate with organizations that do not fully adhere to the FIPS standards.

By default, FIPS compliance is disabled in Lync Server 2013.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsFIPSConfiguration"}

**Lync Server 控制面板:** The functions carried out by the Get-CsFIPSConfiguration cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard values when referencing a collection of FIPS configuration settings. Because you can only have a single, global instance of these settings there is no reason to use the Filter parameter. However, if you prefer you can use the following syntax to reference the global settings:</p>
<p>-Filter &quot;g*&quot;</p>
<p>That syntax brings back all the FIPS configuration settings that have an Identity that begins with the letter &quot;g&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique Identity of the FIPS configuration settings. Because you can only have a single, global instance of these settings, you do not need to specify an Identity when calling the <strong>Get-CsFIPSConfiguration</strong> cmdlet. If you prefer, however, you can use the following syntax to reference the global settings:</p>
<p>-Identity global</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the FIPS configuration data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account whose FIPS configuration settings are to be retrieved.</p>
<p>For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsFIPSConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsFIPSConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.FIPSConfiguration.FIPSConfiguration object.

## 另请参阅

#### 其他资源

[New-CsFIPSConfiguration](new-csfipsconfiguration.md)  
[Remove-CsFIPSConfiguration](remove-csfipsconfiguration.md)  
[Set-CsFIPSConfiguration](set-csfipsconfiguration.md)

