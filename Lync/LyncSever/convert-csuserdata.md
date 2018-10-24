---
title: Convert-CsUserData
TOCTitle: Convert-CsUserData
ms:assetid: e52f8037-19f3-49c9-8dfc-79b0c27d8b94
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205337(v=OCS.15)
ms:contentKeyID: 49314556
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Convert-CsUserData

 

_**上一次修改主题：** 2015-03-09_

Converts exported user data to the data format used by either Microsoft Lync Server 2010 or Lync Server 2013. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Convert-CsUserData -InputFile <String> -OutputFile <String> -TargetVersion <Lync2010 | Current> [-ConfDirectoryFilter <String>] [-Force <SwitchParameter>] [-UserFilter <String>]

## Examples

## Example 1

The command shown in Example 1 converts the user data stored in the file C:\\Logs\\Lync2013Data.zip to the user data format used in Lync Server 2010. The converted data is stored in the XML file C:\\Logs\\Lync2010Data.xml.

    Convert-CsUserData -InputFile "C:\Logs\Lync2013Data.Zip" -OutputFile "C:\Logs\Lync2010Data.xml" -TargetVersion Lync2010

## Example 2

Example 2 shows how you can convert data for a single user; in this example, the user with the SIP address kenmyer@litwareinc.com. This is done by including the UserFilter parameter followed by the user’s SIP address (minus the sip: prefix).

    Convert-CsUserData -InputFile "C:\Logs\Lync2013Data.Zip" -OutputFile "C:\Logs\Lync2010data.xml" -TargetVersion Lync2010 -UserFilter "kenmyer@litwareinc.com"

## Detailed Description

The **Convert-CsUserData** cmdlet takes data exported by using the [Export-CsUserData](export-csuserdata.md) cmdlet and then converts that data to the user data format used by either Microsoft Lync Server 2010 or Lync Server 2013. In turn, that enables the **Import-CsUserData** cmdlet to import that data to the appropriate version of Lync Server.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Convert-CsUserData"}

**Lync Server 控制面板:** The functions carried out by the **Convert-CsUserData** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>InputFile</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the .ZIP file or .XML file containing the user data to be converted. For example:</p>
<p>-InputFile “C:\Data\Lync2010.zip&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>OutputFile</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the file that will store the converted data. If you are outputting the data using the Microsoft Lync Server 2010 format then the output file must use a .XML file extension; for example:</p>
<p>-OutputFile &quot;C:\Data\ConvertedLync2010Data.xml&quot;</p>
<p>If you are using the Lync Server 2013 format, the output file must use a .ZIP file extension:</p>
<p>-OutputFile &quot;C:\Data\ConvertedLyncData.zip&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetVersion</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.BlobStore.Cmdlets.ConvertTarget</p></td>
<td><p>Indicates the format for the converted data. Allowed values are:</p>
<p>Lync2010</p>
<p>Current</p></td>
</tr>
<tr class="even">
<td><p><em>ConfDirectoryFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to convert conference directory data. To do this, include the ConfDirectoryFilter parameter and specify the Identity of the conference directory:</p>
<p>-ConfDirectoryFilter 13</p>
<p>You can retrieve conference directory Identities by using this command:</p>
<p>Get-CsConferenceDirectory | Select-Object Identity, ServiceId</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>UserFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to convert data for a single user. That user specified by using his or her SIP address, minus the sip: prefix. For example:</p>
<p>-UserFilter &quot;kenmyer@litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Convert-CsUserData** cmdlet does not accept pipelined input.

## Return Types

The **Convert-CsUserData** cmdlet creates either XML or ZIP files, depending on whether the converted data is to be used with Lync Server 2010 or with Lync Server 2013.

## 另请参阅

#### 其他资源

[Export-CsUserData](export-csuserdata.md)  
[Import-CsUserData](import-csuserdata.md)  
[Sync-CsUserData](sync-csuserdata.md)  
[Update-CsUserData](update-csuserdata.md)

