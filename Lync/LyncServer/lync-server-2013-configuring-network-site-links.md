---
title: Lync Server 2013：配置网络站点链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50457100f1ba476fd3ddfa923b73acd6bfe6d843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>在 Lync Server 2013 中配置网络站点链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

在呼叫允许控制 (CAC) 配置中，可以创建定义直接链接的站点之间的带宽限制的网络站点间策略。 当两个网络站点共享一条直接链接时，可定义这两个站点之间的音频和视频连接的带宽限制。 您不能使用 Lync Server 控制面板配置网络站点策略，这只能通过使用 Lync Server 命令行管理程序中的 cmdlet 来实现。 您可以从 Lync Server 命令行管理程序中创建、修改和删除网络站点链接（也称为网络站点间策略）。

<div>

## <a name="to-create-a-network-site-link"></a>创建网络站点链接

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令提示符处，键入以下命令，取代有效的配置值：
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    本示例创建一个名为里诺\_的新网络站点链接，用于设置里诺和新的网络站点之间的带宽限制。 运行此命令之前，必须已存在网络站点和带宽策略配置文件。

有关参数的详细说明，请参阅 Lync Server 命令行管理程序文档中的[new-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 。 要检索可应用于网络站点链接的带宽策略配置文件列表，请调用 **Get-CsNetworkBandwidthPolicyProfile** cmdlet。 有关详细信息，请参阅 Lync Server 命令行管理程序文档中的[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>修改网络站点链接

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  使用 **Set-CsNetworkInterSitePolicy** cmdlet 修改给定网络站点链接的属性。 可以修改连接站点中的任一个（或两个），也可以修改与链接关联的带宽策略配置文件。 下面的示例展示了如何修改名为里诺\_的站点链接的带宽策略配置文件：
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

有关参数的详细说明，请参阅 Lync Server 命令行管理程序文档中的[new-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>删除网络站点链接

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  使用 **Remove-CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。 下面的示例删除了里诺\_的 "上海 network site" 链接：
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

有关参数的详细说明，请参阅 Lync Server 命令行管理程序文档中的[new-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫允许控制 cmdlet](https://docs.microsoft.com/powershell/module/skype/)  


[新 New-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[New-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[New-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[New-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

