---
title: Lync Server 2013：删除现有 CDR 配置设置集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82170cf695136694588721a0b4e7e63c5c7dd618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有 CDR 配置设置集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

安装 Microsoft Lync Server 2013 时，将为你创建一个 CDR 配置设置的单一全局集合。 管理员还可以选择创建可应用于各个站点的自定义设置集合。 根据设计，在站点范围配置的设置优先于在全局范围配置的设置。 如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。

请注意，您也可以“删除”全局设置。但是，这不会实际删除全局设置，而是将该集合中的所有属性重置为其默认值。例如，默认情况下，将在 CDR 配置设置集合中启用清除。假定您修改全局集合以便禁用清除。如果您稍后删除全局设置，则所有属性都将被重置为其默认值。在此情况下，这意味着将再次启用清除。

您可以使用 Lync Server 控制面板或[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) CMDLET 删除 CDR 配置设置。

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>使用 Lync Server 控制面板删除 CDR 配置设置

1.  在 "Lync Server 控制面板" 中，单击 "**监控和存档**"。

2.  在“呼叫详细信息记录”**** 选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。

3.  单击“编辑”****，然后单击“删除”****。

4.  在 "Lync Server 控制面板" 对话框中，单击 **"确定"**。

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 CDR 配置设置

您可以使用 Windows PowerShell 和**set-cscdrconfiguration** cmdlet 删除呼叫详细信息记录配置设置。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>删除指定的 CDR 配置设置集合

  - 此命令删除适用于 Redmond 站点的 CDR 配置设置：
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>删除应用到站点范围的所有 CDR 配置设置

  - 此命令删除适用于站点范围的所有 CDR 配置设置：
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>删除禁用呼叫详细信息记录的 CDR 配置设置

  - 此命令删除已禁用呼叫详细信息记录的所有 CDR 配置设置：
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

有关详细信息，请参阅[set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

