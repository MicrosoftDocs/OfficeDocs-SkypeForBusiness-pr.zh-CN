---
title: 'Lync Server 2013: 还原设备更新规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90eeb82e710b6ea65bc32184685497494dbef8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中还原设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

若要从部署中的设备卸载设备更新规则, 请将其还原。 还原设备更新规则将卸载更新并重新安装该规则的以前版本。

你可以使用 Lync Server 控制面板或 Windows PowerShell 还原设备更新规则。

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 还原设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备更新**" 导航按钮。

4.  在 "**设备更新**" 页面上, 执行下列操作之一:
    
      - 若要还原一个规则, 请选择该规则。
    
      - 若要还原所有规则, 请单击 "**编辑**", 然后单击 "**全选**"。

5.  单击 "**操作**" 菜单, 然后单击 "**还原**"。

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 还原设备更新规则

还可以使用 Windows PowerShell 和**Restore-CsDeviceUpdateRule** cmdlet 还原设备更新规则。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>在服务器上还原单个设备更新规则

  - 以下命令将在 Web 服务器 dc2d9b1222ff9 上还原设备更新规则 d5ce3c10-2588-420a-atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>还原服务器上的所有设备更新规则

  - 此命令将还原 web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

有关详细信息, 请参阅[Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

