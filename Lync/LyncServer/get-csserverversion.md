---
title: Get-CsServerVersion
TOCTitle: Get-CsServerVersion
ms:assetid: 66af07c0-fdfe-491a-ad48-b8821fb58904
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398470(v=OCS.15)
ms:contentKeyID: 49313082
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsServerVersion

 

_**上一次修改主题：** 2015-03-09_

Returns server licensing information for a computer running Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsServerVersion

## Examples

## EXAMPLE 1

The command shown in Example 1 returns licensing information for the local computer. This is the only way that the **Get-CsServerVersion** cmdlet can be used.

    Get-CsServerVersion

## Detailed Description

Lync Server comes in two different versions: an evaluation version (which will eventually expire) and a fully-licensed version. The **Get-CsServerVersion** cmdlet provides a way for administrators to determine which version of Lync Server is running on a computer. The **Get-CsServerVersion** cmdlet, which is designed to run only on the local computer and which has no additional parameters, attempts to read the registry value HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Real-Time Communications\\{A593FD00-64F1-4288-A6F4-E699ED9DCA35}\\Type. Based on that registry value, the cmdlet will then report back the version number of the software and the Lync Server licensing information. That licensing information will tell you one of the following:

That the evaluation license key has been installed.

That the volume license key has been installed.

That no license key is required for the components installed on the local computer. (Licensing is required only for computers functioning as a 前端服务器, a 控制器, or an 边缘服务器.)

If an error occurs, the **Get-CsServerVersion** cmdlet will report that the license type and version information could not be retrieved, and recommend that you reinstall the Lync Server components.

Note that Get-CsServerVersion returns only the base version number. For example, Get-CsServerVersion will return a value such as 5.0.8308 even if an update has officially changed the version number to 5.0.8308.291. If you need a very specific version number then you should use the Windows Control Panel.

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
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsServerVersion** cmdlet does not support pipelined input.

## Return Types

The **Get-CsServerVersion** cmdlet returns a string value.

