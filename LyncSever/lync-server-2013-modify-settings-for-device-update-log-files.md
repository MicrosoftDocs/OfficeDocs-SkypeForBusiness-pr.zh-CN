---
title: 修改设备更新日志文件的设置
TOCTitle: 修改设备更新日志文件的设置
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182554(v=OCS.15)
ms:contentKeyID: 49313727
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 修改设备更新日志文件的设置

 

_**上一次修改主题：** 2015-03-09_

可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序更改在组织中记录设备更新信息方式的设置。下表显示哪些设置可修改，以及可以使用哪些工具来修改这些设置。

可以全局性地或针对每个站点更改和应用日志设置。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>更改</th>
<th>使用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>日志文件的最大大小（以字节为单位）</p></td>
<td><p>Lync Server 控制面板</p>
<p>- 或者 -</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>可以保存在缓存中的最大信息量（以字节为单位）</p></td>
<td><p>Lync Server 控制面板</p>
<p>- 或者 -</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>将缓存的信息写入日志文件的频率（以分钟为单位）</p></td>
<td><p>Lync Server 控制面板</p>
<p>- 或者 -</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>保留日志文件的时间（以天为单位）</p></td>
<td><p>Lync Server 控制面板</p>
<p>- 或者 -</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>检查应删除的到期文件的时间（一天中的时刻）</p></td>
<td><p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>允许的日志文件扩展名</p></td>
<td><p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>保留的日志文件类型</p></td>
<td><p>Lync Server 命令行管理程序</p></td>
</tr>
</tbody>
</table>


## 使用 Lync Server 控制面板更改日志记录设置

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“客户端”，然后单击“设备日志配置”。

3.  在“设备日志配置”页上，双击要更改的配置。

4.  在“编辑日志设置”对话框中，更改下列任一设置：
    
      - **最大文件大小(字节)** 指定日志文件在清除前可以达到的最大大小。默认值为 1,024,000 字节 (1 MB)。
    
      - **最大缓存大小(字节)** 指定在必须清除日志文件缓存并将数据写入日志文件之前，缓存中所能存储的最大信息量（字节）。默认值为 512,000 字节 (0.5 MB)。
    
      - **刷新缓存的分钟数(1-60)** 指示存储在日志文件缓存中的信息写入实际日志文件的频率。记录数据后，将清除缓存。默认值为 5 分钟。
    
      - **保留日志文件的天数(1-365)** 指定日志文件在清除前的保留天数。默认值为 10 天。

5.  单击“提交”。

## 使用 Windows PowerShell Cmdlet 更改日志设置

可以使用 Windows PowerShell 和 **Set-CsDeviceUpdateConfiguration** cmdlet 修改设备更新日志文件设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。



下面的示例演示几种可以使用 **Set-CsDeviceUpdateConfiguration** 修改设置的方法。

## 修改最大日志文件大小和日志清除时间间隔

  - 下面的命令将修改应用到 Redmond 网站的设备更新日志设置。在此示例中，最大日志文件大小设置为 204800 字节，日志清除时间间隔设置为 14 天。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

## 修改日志清除时刻

  - 此命令将 Redmond 网站的日志清除时间设置为凌晨 3:00。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

有关详细信息，请参阅 [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet 的帮助主题。

