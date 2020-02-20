---
title: Lync Server 2013：创建或修改带宽策略配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b40b4a397ffe3eeeaade138542e5634bf8f7afd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改带宽策略配置文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-15_

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。 在 Microsoft Lync Server 2013 中，仅可为音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 您可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络站点相关联。 可使用以下过程创建或修改带宽策略配置文件。 若要删除带宽策略配置文件，请参阅[在 Lync Server 2013 中删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>创建新的带宽策略配置文件

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“带宽策略”****。

4.  在“带宽策略”**** 页上，单击“新建”****。

5.  在“新建带宽策略配置文件”**** 的“名称”**** 字段中键入名称。此名称必须在所有带宽策略配置文件中是唯一的。

6.  在“音频限制”**** 字段中，键入一个数值。此值是要为所有音频连接分配的最大带宽量，以 kbps 为单位表示。

7.  在“音频会话限制”**** 字段中输入一个数值。此值是要为单个音频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 40 或更大。

8.  在“视频限制”**** 字段中输入一个数值。此值是要为所有视频连接分配的最大带宽量，以 kbps 为单位表示。

9.  在“视频会话限制”**** 字段中输入一个数值。此值是要为单个视频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 100 或更大。

10. （可选）在“说明”**** 字段中键入值，用以提供仅通过名称无法表达的更多有关该带宽策略配置文件的信息。

11. 单击“提交”****。
    
    <div>
    

    > [!NOTE]  
    > 创建新的带宽策略配置文件不会自动强制实施带宽限制。 必须先将策略配置文件与站点相关联。 有关如何将策略配置文件与网站相关联的详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中创建或修改网络站点</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>修改带宽策略配置文件

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“带宽策略”****。

4.  在“带宽策略”**** 页上，单击要修改的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在“编辑带宽策略配置文件”**** 页上，根据需要修改字段（有关详细信息，请参阅本主题前面的“创建带宽策略配置文件”一节）。

7.  单击“提交”****。
    
    <div>
    

    > [!NOTE]  
    > 修改带宽策略配置文件时，会立即更新与此带宽策略配置文件关联的所有网络站点的带宽限制。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)  
[新 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

