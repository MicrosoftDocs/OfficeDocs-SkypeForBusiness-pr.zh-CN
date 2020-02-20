---
title: Lync Server 2013：启用呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ee956918fd56cb3fa91d1d5065f364d525f8446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中启用呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。 配置 CAC 网络后，必须启用 CAC 以强制实施带宽限制。 您可以使用 Lync Server 控制面板执行此操作。

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>从 Lync Server 控制面板启用 CAC

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“全局”****。

4.  在“全局”**** 页上，单击“全局”**** 配置。
    
    <div>
    

    > [!NOTE]  
    > 只能为任何 Microsoft Lync Server 2013 部署配置一个网络，因此列表中永远不会有多个网络配置。 无法重命名“全局”配置。

    
    </div>

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在“编辑全局设置”**** 页上，选中“启用呼叫允许控制”**** 复选框，然后单击“提交”****。

单击“提交”**** 时，运行配置测试。此时将关闭“编辑全局设置”**** 对话框，并返回到“全局”**** 页。如果在网络配置中发现任何阻止其正常工作的错误或不一致问题（例如，如果每个区域未通过区域间路由连接到其他每个区域），则会收到警告。

如果更改网络配置，则可通过打开“全局”配置并单击“提交”**** 再次运行验证检查。无需先禁用 CAC：保留此复选框的选中状态，并单击“提交”****。在未对配置进行任何更改的情况下可随时执行此操作。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)  


[在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)  
[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

