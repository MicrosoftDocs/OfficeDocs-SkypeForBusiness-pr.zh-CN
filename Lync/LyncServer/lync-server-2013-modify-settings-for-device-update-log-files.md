---
title: 'Lync Server 2013: 修改设备更新日志文件的设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中修改设备更新日志文件的设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

你可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序更改设备更新信息在你的组织中的记录方式的设置。 下表显示了哪些设置是可修改的, 以及用于修改设置的工具。

可以在全局或每个网站上更改和应用日志设置。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要更改</th>
<th>使用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>日志文件的最大大小 (以字节为单位)</p></td>
<td><p>Lync Server 控制面板</p>
<p>或</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>可以保留在缓存中的最大信息量 (以字节为单位)</p></td>
<td><p>Lync Server 控制面板</p>
<p>或</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>将缓存的信息写入日志文件的频率 (以分钟为单位)</p></td>
<td><p>Lync Server 控制面板</p>
<p>或</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>将日志文件保留多长时间 (天)</p></td>
<td><p>Lync Server 控制面板</p>
<p>或</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>何时 (一天的时间) 检查应删除的过期文件</p></td>
<td><p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>允许的日志文件扩展名</p></td>
<td><p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>要保留的日志文件类型</p></td>
<td><p>Lync Server 命令行管理程序</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 更改日志记录设置

1.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备日志配置**"。

3.  在 "**设备日志配置**" 页面上, 双击要更改的配置。

4.  在 "**编辑日志设置**" 对话框中, 更改以下任何设置:
    
      - **最大文件大小 (字节)**   指定日志文件在清除之前可以达到的最大大小。 默认值为1024000字节 (1 MB)。
    
      - **最大缓存大小 (字节)**   指定必须在日志文件缓存中保留的最大信息量 (以字节为单位), 然后才能在该缓存中清除, 并将数据写入日志文件。 默认值为512000字节 (0.5 MB)。
    
      - **刷新缓存的分钟数 (1-60)**   表示将日志文件缓存中存储的信息写入实际日志文件的频率。 记录数据后, 将清除缓存。 默认值为5分钟。
    
      - **保留日志文件的天数 (1-365)**   指定日志文件在清除之前保留的天数。 默认值为10天。

5.  单击“**提交**”。

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 更改日志记录设置

可以使用 Windows PowerShell 和**CsDeviceUpdateConfiguration** cmdlet 修改设备更新日志文件设置。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

以下示例显示了可使用**CsDeviceUpdateConfiguration**修改设置的几种方式。

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>修改日志文件的最大大小和日志清除间隔

  - 以下命令将修改应用于 Redmond 网站的设备更新日志设置。 在此示例中, 最大日志文件大小设置为204800字节, 日志清除间隔设置为14天。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>修改日志清除的一天时间

  - 此命令将雷德蒙站点的日志清除时间设置为 3:00 AM。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

有关详细信息, 请参阅[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

