---
title: Set-CsCallParkServiceMusicOnHoldFile
TOCTitle: Set-CsCallParkServiceMusicOnHoldFile
ms:assetid: af5e7573-4bfd-47b1-a92b-83b06a537158
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412836(v=OCS.15)
ms:contentKeyID: 49313957
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCallParkServiceMusicOnHoldFile

 

_**上一次修改主题：** 2015-03-09_

更改寄存呼叫时向处于呼叫等待状态的呼叫者播放的音频文件。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsCallParkServiceMusicOnHoldFile -Content <Byte[]> -Service <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例将 SoothingMusic.wma 文件设置为寄存呼叫时向呼叫者播放的音频文件。此示例的第一行调用 **Get-Content** cmdlet。此 cmdlet 仅用于读取文件内容并将其分配给变量（在此示例中为变量 $a）。我们将参数值 0 传递到 ReadCount 参数，因此 **Get-Content** cmdlet 将一次读取整个文件（而不是逐行读取，这不适用于音频文件）。将参数 Encoding 设置为 byte。这将通知 **Get-Content** cmdlet，要读取到变量 $a 中的内容是字节数组，而不是 .wma 格式的音频文件。

此示例中的第 2 行是实际分配音频文件的位置。调用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet，并指定运行呼叫寄存服务的服务 ID。然后，将读取到变量 $a 中的音频文件内容传递给 Content 参数。（请记住，这些内容必须采用字节格式。）

    $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
    Set-CsCallParkServiceMusicOnHoldFile -Service ApplicationServer:pool0.litwareinc.com -Content $a

## 详细说明

呼叫寄存是一项允许用户寄存来电的服务。寄存呼叫会将呼叫转接至指定范围内的某个号码，并立即将其置于呼叫等待状态。根据呼叫寄存服务的配置设置，可在寄存呼叫时向呼叫者播放呼叫等待音乐。使用此 cmdlet 可更改向处于呼叫等待状态的寄存呼叫者播放的音频文件（呼叫等待音乐）。

只有在呼叫寄存服务的 EnableMusicOnHold 属性设置为 True 时，才会播放呼叫等待音乐。可以通过调用 **Get-CsCpsConfiguration** cmdlet 检查此属性。可以在使用 **New-CsCpsConfiguration** cmdlet 创建呼叫寄存配置时设置该属性，或者在已存在呼叫寄存配置后通过调用 **Set-CsCpsConfiguration** cmdlet 设置该属性。该属性的默认值为 True。

Lync Server 附带了一个默认呼叫寄存服务呼叫等待音乐文件。如果没有指定音频文件，则使用此默认文件。

音频文件必须为以下格式：Windows Media Audio 9、44 kHz、16 位、Mono、CBR 或 32 kbps。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCallParkServiceMusicOnHoldFile"}

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
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Content</em></p></td>
<td><p>必需</p></td>
<td><p>System.Byte[]</p></td>
<td><p>字节格式的音频文件内容。</p>
<p>使用 <strong>Get-Content</strong> cmdlet 可检索字节格式的音频文件内容。（有关详细信息，请参阅本主题中的“示例”部分。）</p></td>
</tr>
<tr class="even">
<td><p><em>Service</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>呼叫寄存服务所在的服务的 ID；例如 ApplicationServer:pool0.litwareinc.com。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Byte\[\]。接受通过管道传递的包含呼叫等待音乐文件的字节数组的输入。

## 返回类型

此 cmdlet 不会返回值。

## 另请参阅

#### 其他资源

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Remove-CsCpsConfiguration](remove-cscpsconfiguration.md)  
[Set-CsCpsConfiguration](set-cscpsconfiguration.md)  
[Get-CsCpsConfiguration](get-cscpsconfiguration.md)

