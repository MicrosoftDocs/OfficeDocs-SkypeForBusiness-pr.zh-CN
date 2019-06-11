---
title: 'Lync Server 2013: 重置设备更新规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab03c5c28db28ddbd883f3f50845eaf91d4fd1a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>重置 Lync Server 2013 中的设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

如果你不喜欢更新在你的测试设备上的工作方式, 你可以重置设备更新规则, 这将删除规则的挂起状态并从测试设备中卸载更新。

你可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。

<div>


> [!NOTE]  
> 若要卸载已批准 (即已推出) 的规则, 请将其还原。 有关详细信息, 请参阅<A href="lync-server-2013-restore-a-device-update-rule.md">在 Lync Server 2013 中还原设备更新规则</A>。



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 重置设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备更新**" 导航按钮。

4.  在 "**设备更新**" 页面上, 执行下列操作之一:
    
      - 若要重置一个规则, 请选择要重置的规则。
    
      - 若要重置所有规则, 请在 "**编辑**" 菜单上单击 "**全选**"。
    
      - 若要重置一个品牌的所有规则, 请使用 "**品牌**" 列菜单。

5.  单击 "**操作**", 然后单击 "**取消挂起的更新**"。
    
    <div>
    

    > [!TIP]  
    > 如果您确信不希望再推出已取消的设备更新规则, 您可能需要将其删除。 有关详细信息, 请参阅<A href="lync-server-2013-remove-a-device-update-rule.md">在 Lync Server 2013 中删除设备更新规则</A>。

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重置设备更新规则

还可以使用 Windows PowerShell 和**Reset CsDeviceUpdateRule** cmdlet 重置设备更新规则。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>在服务器上重置特定的设备更新规则

  - 以下命令将在 Web 服务器 dc2d9b1222ff9 上重置设备更新规则 d5ce3c10-2588-420a-atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>重置服务器上的所有设备更新规则

  - 此命令将重置 Web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>重置具有特定品牌的所有设备更新规则

  - 在此示例中, 将重置整个组织中具有等于 Microsoft 的品牌的所有设备更新:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

有关详细信息, 请参阅 Reset cmdlet 的帮助主题[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) 。

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

