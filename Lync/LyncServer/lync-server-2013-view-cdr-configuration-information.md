---
title: Lync Server 2013：查看 CDR 配置信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eff8985832d9bb6e8aa4e06b777944417c7b8bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看 CDR 配置信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

安装 Microsoft Lync Server 2013 时，将为你创建一个 CDR 配置设置的单一全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 您可以使用 Lync Server 控制面板或[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 查看在您的组织中使用的 CDR 配置设置。

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板查看 CDR 配置信息

1.  在 Lync Server 控制面板中，单击 "**监控和存档**"。

2.  所有 CDR 配置设置的列表将显示在“呼叫详细信息记录”**** 选项卡中；对于每个设置集合，您将看到集合“名称”****；是否已启用 CDR（“CDR”**** 属性）；是否已启用清除（“CDR 清除”**** 属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“编辑”****，然后单击“显示详细信息”****。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 CDR 配置信息

您可以使用 Windows PowerShell 和 Set-cscdrconfiguration cmdlet 查看 CDR 配置设置。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-view-cdr-configuration-information"></a>查看 CDR 配置信息

  - 若要查看有关所有 CDR 配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsCdrConfiguration
    
    这将返回与以下类似的信息：
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

有关详细信息，请参阅[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

