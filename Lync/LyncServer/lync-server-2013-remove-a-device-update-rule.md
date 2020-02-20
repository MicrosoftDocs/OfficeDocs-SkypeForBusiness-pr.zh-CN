---
title: Lync Server 2013：删除设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b02da5927b6a33cabefd005a8f026ca65f99b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中删除设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

删除设备更新规则会将其从设备更新队列中永久删除。

删除规则不同于从部署中的设备或测试设备中卸载更新。 若要从部署中卸载已批准的更新，请*还原*设备更新规则。 有关详细信息，请参阅[在 Lync Server 2013 中还原设备更新规则](lync-server-2013-restore-a-device-update-rule.md)。 若要卸载未通过测试设备批准的更新，请*重置*它。 有关详细信息，请参阅[在 Lync Server 2013 中重置设备更新规则](lync-server-2013-reset-a-device-update-rule.md)。

您可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板删除设备更新规则

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。

4.  在 "**设备更新**" 页上，执行下列操作之一：
    
      - 若要删除一个规则，请选择要删除的规则。
    
      - 若要删除所有规则，请单击 "**编辑**" 菜单，然后单击 "**全选**"。

5.  单击“编辑”****，然后单击“删除”****。

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除设备更新规则

还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 删除设备更新规则。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>从服务器中删除单个设备更新规则

  - 下面的命令从 dc2d9b1222ff9 上的 Web 服务器中删除设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>从服务器中删除所有设备更新规则

  - 此命令将从 atl-cs-001.litwareinc.com 上的 web 服务器中删除所有设备更新规则。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中审批设备更新规则](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

