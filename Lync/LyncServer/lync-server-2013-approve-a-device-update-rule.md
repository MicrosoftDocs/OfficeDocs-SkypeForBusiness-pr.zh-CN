---
title: Lync Server 2013：批准设备更新规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb464d0845f70012bdd8e70365c8a7993de6b4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中批准设备更新规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

导入设备更新规则后，它将安装在测试设备上。 如果你的测试成功，并且希望将更新部署到你的组织，请使用 Lync Server 控制面板或 Windows PowerShell 批准它。

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 批准设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在 "**设备更新**" 页面上，执行下列操作之一：
    
      - 若要批准一个规则，请选择该规则。
    
      - 若要批准所有规则，请单击 "**编辑**"，然后单击 "**全选**"。

4.  单击 "**操作**"，然后单击 "**批准**"。

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 批准设备更新规则

还可以使用 Windows PowerShell 和**CsDeviceUpdateRule** cmdlet 批准设备更新规则。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>批准单个设备更新规则

  - 以下命令批准在 Web 服务器 dc2d9b1222ff9 上找到的 device update 规则 d5ce3c10-2588-420a-atl-cs-001.litwareinc.com：
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>批准多个设备更新规则

  - 此命令批准 Microsoft 品牌设备的所有设备更新规则：
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

有关详细信息，请参阅[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中导入设备更新规则](lync-server-2013-import-device-update-rules.md)  
[在 Lync Server 2013 中还原设备更新规则](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

