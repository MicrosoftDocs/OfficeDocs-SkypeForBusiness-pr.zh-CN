---
title: Lync Server 2013：查看设备更新配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cf34d5f8241735263547fe64dc0f3e3b124bb10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看设备更新配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

您可以使用 Lync Server 命令行管理程序和**CsDeviceUpdateConfiguration** cmdlet （可从 Lync server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行）来查看设备更新服务配置设置

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

<div>


<div>


  - 若要查看有关所有语音路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsDeviceUpdateConfiguration
    
    此命令返回与以下内容类似的信息：
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

有关此 cmdlet 的详细信息，请参阅[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

