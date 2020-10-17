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
ms.openlocfilehash: e4caab36c57c3c8901bd0691e5623f232879bd03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528519"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中启用网络媒体旁路

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

媒体绕过设置在 Microsoft Lync Server 2013 部署中全局应用。 媒体旁路允许呼叫绕过中介服务器。 有关何时使用媒体旁路的详细信息，请参阅规划部分中的在 [Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md) 。

您可以从 Lync Server 控制面板启用和配置媒体旁路。

<div>

## <a name="to-enable-and-configure-media-bypass"></a>启用和配置媒体旁路

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“全局”****。

4.  在“全局”**** 页上，单击“全局”**** 配置。 始终只有一种配置，并且总是名为 Global。

5.  在 " **编辑** " 菜单上，单击 " **查看详细信息**"。

6.  在 " **编辑全局设置** " 页上，单击 " **启用媒体旁路** " 复选框。

7.  选择下列选项之一：
    
      - **始终绕过**    选择此选项可在所有呼叫中尝试媒体旁路。 如果已启用呼叫允许控制 (CAC) ，此选项将不可用。 如果未启用 CAC，请在以下情况下选择此选项：
        
          - 无需带宽控制。
        
          - 不需要进行细粒度配置来确定何时应应何时发生绕过。
        
          - 网关和客户端之间存在完全连接。
    
      - **使用网站和区域配置**    如果启用 CAC，则默认情况下此选项处于选中状态，并且无法更改。 选择此选项后，将使用网络配置网站和区域确定何时可以使用媒体旁路。 如果选择此选项，则可以选择对未映射的网站启用旁路。 仅当您具有一个或多个与不具有带宽约束的相同区域相关联的大型网站时，单击 "为 **非映射网站启用旁路** " 复选框 (例如，大型中央网站) ，并且您也有一些与具有带宽限制的相同区域相关联的分支站点。 为非映射网站启用旁路时，将简化配置，因为您仅指定与分支站点关联的子网，而不需要指定与所有站点关联的所有子网。 如果启用了 CAC，我们建议您不要选中 "为 **非映射网站启用旁路** " 复选框。

8.  单击 " **提交** " 以保存所做的更改。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中禁用网络媒体旁路](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013 中的全局媒体旁路选项](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

