---
title: Lync Server 2013：查看网络带宽策略配置文件信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51e0ec43758823666809321c2abe424ce7f480ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看网络带宽策略配置文件信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。 在 Microsoft Lync Server 2013 中，仅可为音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 您可以使用 Lync Server 控制面板为这些策略创建、修改或删除容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络站点相关联。 使用下列过程可查看带宽策略配置文件。 若要创建或修改带宽策略配置文件，请参阅[在 Lync Server 2013 中创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>查看带宽策略配置文件

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“带宽策略”****。

4.  在 "**带宽策略**" 页上，单击要查看的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络带宽策略配置文件信息

可以使用 Windows PowerShell 和 CsNetworkBandwidthPolicyProfile cmdlet 查看网络带宽配置文件。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>查看网络带宽策略配置文件信息

  - 若要查看有关所有网络带宽策略配置文件的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkBandwidthPolicyProfile
    
    这将返回与以下类似的信息：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

有关详细信息，请参阅[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改带宽策略配置文件](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[在 Lync Server 2013 中删除网络带宽策略配置文件](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

