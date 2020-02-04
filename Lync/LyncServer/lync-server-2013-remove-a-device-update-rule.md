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
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中删除设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

删除设备更新规则会将其永久从设备更新队列中删除。

删除规则与从部署中的设备或测试设备卸载更新不同。 若要从部署中卸载已批准的更新，请*还原*设备更新规则。 有关详细信息，请参阅[在 Lync Server 2013 中还原设备更新规则](lync-server-2013-restore-a-device-update-rule.md)。 若要卸载尚未通过测试设备批准的更新，请*重置*它。 有关详细信息，请参阅[在 Lync Server 2013 中重置设备更新规则](lync-server-2013-reset-a-device-update-rule.md)。

你可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 删除设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。

4.  在 "**设备更新**" 页面上，执行下列操作之一：
    
      - 若要删除一个规则，请选择要删除的规则。
    
      - 若要删除所有规则，请单击 "**编辑**" 菜单，然后单击 "**全选**"。

5.  单击“**编辑**”，然后单击“**删除**”。

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除设备更新规则

还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 删除设备更新规则。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>从服务器中删除单个设备更新规则

  - 以下命令将从 dc2d9b1222ff9 上的 Web 服务器中删除 device update 规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>从服务器中删除所有设备更新规则

  - 此命令将从 atl-cs-001.litwareinc.com 中的 web 服务器删除所有设备更新规则。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中批准设备更新规则](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

