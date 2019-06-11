---
title: 'Lync Server 2013: 启用呼叫许可控制'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中启用呼叫许可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。 配置 CAC 网络后, 必须启用 CAC 才能强制实施带宽限制。 您可以使用 Lync Server "控制面板" 执行此操作。

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>从 Lync Server "控制面板" 中启用 CAC

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。

4.  在 "**全局**" 页面上, 单击 "**全局**配置"。
    
    <div>
    

    > [!NOTE]  
    > 只能为任何 Microsoft Lync Server 2013 部署配置一个网络, 因此列表中永远不会有多个网络配置。 不能重命名全局配置。

    
    </div>

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑全局设置**" 页面上, 选中 "**启用呼叫许可控制**" 复选框, 然后单击 "**提交**"。

单击 "**提交**" 时, 将运行配置测试。 "**编辑全局设置**" 对话框将关闭, 返回到**全局**页。 如果你的网络配置中发现了任何错误或不一致 (例如, 如果每个区域未通过 interregion 路由连接到其他每个区域), 你将收到警告。

如果你对网络配置进行了更改, 则可以通过打开全局配置并单击 "**提交**" 来再次运行验证检查。 无需首先禁用 CAC: 选中复选框, 然后单击 "**提交**"。 您可以随时执行此操作, 而无需进行任何配置更改。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫许可控制概述](lync-server-2013-overview-of-call-admission-control.md)  


[在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中配置呼叫许可控制](lync-server-2013-configure-call-admission-control.md)  
[Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

