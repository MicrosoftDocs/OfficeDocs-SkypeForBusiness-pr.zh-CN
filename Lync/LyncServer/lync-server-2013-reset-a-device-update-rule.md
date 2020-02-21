---
title: Lync Server 2013：重置设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa5bd589a6368e99401f2f84d702756d595f9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中重置设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

如果您不喜欢更新对测试设备的工作方式，则可以重置设备更新规则，该规则会删除规则的待处理状态，并从测试设备中卸载更新。

您可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。

<div>


> [!NOTE]  
> 若要卸载已批准的规则（即，已向后滚动），请将其还原。 有关详细信息，请参阅<A href="lync-server-2013-restore-a-device-update-rule.md">在 Lync Server 2013 中还原设备更新规则</A>。



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板重置设备更新规则

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备更新**" 导航按钮。

4.  在 "**设备更新**" 页上，执行下列操作之一：
    
      - 若要重置一个规则，请选择要重置的规则。
    
      - 若要重置所有规则，请在 "**编辑**" 菜单上单击 "**全选**"。
    
      - 若要重置一个品牌的所有规则，请使用**品牌**栏菜单。

5.  单击 "**操作**"，然后单击 "**取消挂起的更新**"。
    
    <div>
    

    > [!TIP]  
    > 如果你确信不会再推出已取消的设备更新规则，则可能需要将其删除。 有关详细信息，请参阅<A href="lync-server-2013-remove-a-device-update-rule.md">在 Lync Server 2013 中删除设备更新规则</A>。

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重置设备更新规则

还可以使用 Windows PowerShell 和**重置 CsDeviceUpdateRule** cmdlet 重置设备更新规则。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>重置服务器上的特定设备更新规则

  - 以下命令将在 Web 服务器 dc2d9b1222ff9 上重置设备更新规则 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>重置服务器上的所有设备更新规则

  - 此命令将重置 Web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>重置具有特定品牌的所有设备更新规则

  - 在此示例中，将重置组织中与 Microsoft 品牌相同的所有设备更新：
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) Cmdlet 的帮助主题。

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

