---
title: Lync Server 2013：还原设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 728adc1384738d93fc7ac4506a55621830c7de39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中还原设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

若要从部署中的设备中卸载设备更新规则，请将其还原。 还原设备更新规则的同时会卸载更新并重新安装该规则的早期版本。

您可以使用 Lync Server 控制面板或 Windows PowerShell 还原设备更新规则。

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板还原设备更新规则

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。

4.  在 "**设备更新**" 页上，执行下列操作之一：
    
      - 若要还原一个规则，请选择该规则。
    
      - 若要还原所有规则，请单击 "**编辑**"，然后单击 "**全选**"。

5.  单击 "**操作**" 菜单，然后单击 "**还原**"。

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 还原设备更新规则

还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 还原设备更新规则。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>在服务器上还原单个设备更新规则

  - 以下命令将在 Web 服务器 dc2d9b1222ff9 上还原设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>还原服务器上的所有设备更新规则

  - 此命令将还原 web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

