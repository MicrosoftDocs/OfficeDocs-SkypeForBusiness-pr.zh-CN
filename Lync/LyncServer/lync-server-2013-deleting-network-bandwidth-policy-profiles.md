---
title: Lync Server 2013：删除网络带宽策略配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d01bdea6efb632d95a15c631715e9ebe0c9a3bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>删除 Lync Server 2013 中的网络带宽策略配置文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

作为呼叫许可控制（CAC）的一部分，带宽策略用于定义某些形式的带宽限制。 在 Microsoft Lync Server 2013 中，只有音频和视频形式可以分配带宽限制。 你可以设置整体带宽限制和会话限制。 你可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。 使用以下过程删除网络带宽策略配置文件。 有关创建或修改网络带宽策略配置文件的详细信息，请参阅[在 Lync Server 2013 中创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>删除带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击要删除的带宽策略配置文件。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个配置文件。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个配置文件。 或者，若要选择所有配置文件，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  在 "**编辑**" 菜单上，单击 "**删除**"。
    
    <div>
    

    > [!WARNING]  
    > 您不能删除与网络站点相关联的带宽策略配置文件。 您必须先删除与网络站点的关联，然后才能删除配置文件。 有关如何修改网络站点的详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中创建或修改网络站点</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[在 Lync Server 2013 中查看网络带宽策略配置文件信息](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[在 Lync Server 2013 中配置呼叫许可控制](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

