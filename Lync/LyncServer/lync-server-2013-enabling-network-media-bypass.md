---
title: Lync Server 2013：启用网络媒体旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中启用网络媒体旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

媒体绕过设置在 Microsoft Lync Server 2013 部署中全局应用。 媒体绕过允许呼叫绕过中介服务器。 有关何时使用 "媒体绕过" 的详细信息，请参阅 "规划" 部分中的 "[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)"。

你可以从 Lync Server 控制面板启用和配置 "绕过媒体"。

<div>

## <a name="to-enable-and-configure-media-bypass"></a>启用和配置绕过媒体

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**全局**"。

4.  在 "**全局**" 页面上，单击 "**全局**配置"。 始终只有一种配置，它始终名为 Global。

5.  在 "**编辑**" 菜单上，单击 "**查看详细信息**"。

6.  在 "**编辑全局设置**" 页面上，单击 "**启用绕过媒体**" 复选框。

7.  选择下列选项之一：
    
      - **"始终绕过**   " 选择此选项可在所有呼叫中尝试媒体绕过。 如果启用了 "呼叫许可控制（CAC）"，此选项将不可用。 如果未启用 CAC，请在以下情况下选择此选项：
        
          - 无需带宽控制。
        
          - 不需要精确的配置来确定何时应发生绕过。
        
          - 网关和客户端之间存在完全连接。
    
      - **使用网站和区域配置**   如果启用了 CAC，则默认情况下此选项处于选中状态，并且不能更改。 选中此选项时，将使用网络配置网站和区域确定何时可能使用媒体绕过。 如果选择此选项，则可以选择对未映射的网站启用 "绕过"。 仅当你有一个或多个大型网站与不具有带宽约束的同一区域（例如，大型中央网站）关联，并且你还具有与具有带宽限制的同一区域相关联的某些分支网站时，请单击 "**为非映射网站启用绕过**" 复选框。 为非映射网站启用 "绕过" 时，将简化配置，因为你只需指定与分支网站相关联的子网，而无需指定与所有网站相关联的所有子网。 如果启用了 CAC，我们建议您不要选中 "为**未映射的网站启用旁路**" 复选框。

8.  单击 "**提交**" 保存所做的更改。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中禁用网络媒体旁路](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013 中的全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

