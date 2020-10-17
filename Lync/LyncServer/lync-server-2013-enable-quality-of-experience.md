---
title: Lync Server 2013：启用体验质量
description: Lync Server 2013：启用体验质量。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43746227395477596ff5e39809cf819c110287ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547868"
---
# <a name="enable-quality-of-experience-in-lync-server-2013"></a>启用 Lync Server 2013 中的体验质量

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

用户体验质量 (QoE) 记录指示媒体质量以及有关呼叫和会话中所涉及参与者、设备名称、驱动程序、IP 地址和终结点类型的信息的数值型数据。 有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划监视](lync-server-2013-planning-for-monitoring.md) 。

使用以下过程为整个组织或组织中的每个站点启用 QoE。

<div>


> [!NOTE]  
> 为了启用 QoE，必须首先配置监控和监控后端数据库。 有关详细信息，请参阅 <A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监控</A>。



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板启用 QoE 的具体方法

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色，请登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“用户体验质量数据”****。

4.  在“用户体验质量数据”**** 页上，单击表中相应的集合，再单击“操作”****，然后单击“启用 QoE”****。

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用 QoE

您可以使用 Windows PowerShell 和 **new-csqoeconfiguration** Cmdlet 启用 QoE。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>对单个位置启用 QoE

  - 要启用 QoE，请将 EnableQoE 参数设置为 True ($True)。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>对单个位置禁用 QoE

  - 要禁用 QoE，请将 EnableQoE 参数设置为 False ($False)。这不会卸载监控。但会暂停 QoE 数据的收集和存储。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>使用单个命令在多个位置启用 QoE

  - 以下命令可对组织中当前使用的所有 QoE 配置设置启用 QoE。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

有关详细信息，请参阅 [new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划监视](lync-server-2013-planning-for-monitoring.md)  
[在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

