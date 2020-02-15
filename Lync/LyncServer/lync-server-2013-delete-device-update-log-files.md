---
title: Lync Server 2013：删除设备更新日志文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f5b8ed6d087bb7b80ba93aead7c3ab530c82000
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中删除设备更新日志文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

设备更新 Web 服务可保留大量的日志文件集合。 此集合包括服务本身执行的审核日志和从客户端设备上传的日志文件。 若要防止服务器填满设备更新 Web 服务日志，您可能需要清除已在特定天数内的日志文件。 根据组织中的更新活动和客户端设备的数量以及使用 Lync Server 控制面板或 Lync Server 命令行管理程序，设置此天数。

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板清除设备更新日志的具体方法

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击 **“客户端”**，然后单击 **“设备日志配置”**。

3.  在 **“设备日志配置”** 页上，双击要更改的配置。

4.  在 "**编辑日志设置**" 对话框中的 "**保留日志文件的天数" （1-365）** 中，指定天数。

5.  单击“提交”****。 在服务器上已超过指定天数的所有文件都将被删除。 此设置将应用于此配置，直到您更改它。

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 清除设备更新日志

您可以使用 Windows PowerShell 和**CsDeviceUpdateLog** cmdlet 来清除设备更新日志。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>清除一台服务器上的设备更新日志

  - 以下命令清除 Web 服务器 atl-cs-001.litwareinc.com 上的设备更新日志。 超过10天的所有日志条目（由 DaysBack 参数指定的值）将从日志中删除。
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>清除所有设备更新日志

  - 此命令从当前在组织中使用的所有设备更新日志中删除了过期的条目（在此示例中，条目数超过10天）。
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

有关详细信息，请参阅[CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

