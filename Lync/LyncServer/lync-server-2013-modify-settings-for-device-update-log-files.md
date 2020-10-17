---
title: Lync Server 2013：修改设备更新日志文件的设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2118cac5e8380d27e8f273f5cb469efdbddfd9bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534329"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中修改设备更新日志文件的设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序更改设备更新信息在组织中的记录方式的设置。 下表显示了哪些设置是可修改的，以及用来修改设置) 哪个工具 (s。

可以在全局或每个站点上更改和应用日志设置。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要更改</th>
<th>用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>日志文件的最大大小 () （以字节为单位）</p></td>
<td><p>Lync 服务器控制面板</p>
<p>-或者-</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>可在缓存中保留的最大信息量 (（以字节为单位）) </p></td>
<td><p>Lync 服务器控制面板</p>
<p>-或者-</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>将缓存信息写入日志文件的时间（分钟） (的频率) </p></td>
<td><p>Lync 服务器控制面板</p>
<p>-或者-</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>) 保留日志文件的时间 (（天）</p></td>
<td><p>Lync 服务器控制面板</p>
<p>-或者-</p>
<p>Lync Server 命令行管理程序</p></td>
</tr>
<tr class="odd">
<td><p>当一天中的 (时间) 检查应删除的已过期文件</p></td>
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

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板更改日志记录设置的具体方法

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击 **“客户端”**，然后单击 **“设备日志配置”**。

3.  在 **“设备日志配置”** 页上，双击要更改的配置。

4.  在 " **编辑日志设置** " 对话框中，更改以下任何设置：
    
      - ** (字节的最大文件大小) **    指定日志文件在清除之前可以达到的最大大小。 默认值为1024000个字节 (1 MB) 。
    
      - ** (字节的最大缓存大小) **    指定必须在日志文件缓存中保留的最大信息量（以字节为单位），在该缓存必须被清除，并将数据写入日志文件时，才能在日志文件缓存中保留 () 。 默认值为512000个字节 (0.5 MB) 。
    
      - **刷新缓存 (1-60 的分钟数) **    指示日志文件缓存中存储的信息写入实际日志文件的频率。 记录数据后，将清除缓存。 默认值为5分钟。
    
      - **日志文件 (1-365) **     的保留天数指定日志文件在清除之前保留的天数。 默认值为10天。

5.  单击 **“提交”**。

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 更改日志记录设置

可以使用 Windows PowerShell 和 **CsDeviceUpdateConfiguration** cmdlet 修改设备更新日志文件设置。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

以下示例显示了使用 **CsDeviceUpdateConfiguration** 修改设置的几种方法。

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>修改日志文件的最大大小和日志清除间隔

  - 以下命令将修改应用于 Redmond 站点的设备更新日志设置。 在此示例中，日志文件的最大大小设置为204800个字节，日志清理间隔设置为14天。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>修改日志清除的一天的时间

  - 此命令将 Redmond 网站的日志清除时间设置为 3:00 AM。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

有关详细信息，请参阅 [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

