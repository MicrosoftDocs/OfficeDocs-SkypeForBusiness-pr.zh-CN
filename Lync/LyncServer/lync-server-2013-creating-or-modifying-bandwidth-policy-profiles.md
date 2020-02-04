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
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改带宽策略配置文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-15_

作为呼叫许可控制（CAC）的一部分，带宽策略用于定义某些形式的带宽限制。 在 Microsoft Lync Server 2013 中，只有音频和视频形式可以分配带宽限制。 你可以设置整体带宽限制和会话限制。 你可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络网站相关联。 使用以下过程创建或修改带宽策略配置文件。 若要删除带宽策略配置文件，请参阅[在 Lync Server 2013 中删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>创建新的带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击 "**新建**"。

5.  在**新的带宽策略配置文件**中，在 "**名称**" 字段中键入名称。 此名称在所有带宽策略配置文件中必须是唯一的。

6.  在 "**音频限制**" 字段中，键入一个数字值。 此值表示为所有音频连接分配的最大带宽量（以 kbps 为单位）。

7.  在 "**音频会话限制**" 字段中输入一个数字值。 此值表示为单个音频连接分配的最大带宽量（以 kbps 为单位）。 此值必须为40或更高版本。

8.  在 "**视频限制**" 字段中输入一个数字值。 此值表示为所有视频连接分配的最大带宽量（以 kbps 为单位）。

9.  在 "**视频会话限制**" 字段中输入一个数字值。 此值表示为单个视频连接分配的最大带宽量（以 kbps 为单位）。 此值必须为100或更高版本。

10. 可选在 "**说明**" 字段中键入一个值，以提供有关无法单独以名称表示的此带宽策略配置文件的详细信息。

11. 单击“**提交**”。
    
    <div>
    

    > [!NOTE]  
    > 创建新的带宽策略配置文件不会自动强制实施带宽限制。 必须首先将策略配置文件与网站相关联。 有关如何将策略配置文件与网站相关联的详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中创建或修改网络站点</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>修改带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击要修改的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑带宽策略配置文件**" 页面上，根据需要修改字段（有关详细信息，请参阅本主题前面的 "创建带宽策略配置文件" 部分）。

7.  单击“**提交**”。
    
    <div>
    

    > [!NOTE]  
    > 修改带宽策略配置文件时，它将立即更新与此带宽策略配置文件相关联的所有网络站点的带宽限制。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[删除 Lync Server 2013 中的网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[在 Lync Server 2013 中配置呼叫许可控制](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

