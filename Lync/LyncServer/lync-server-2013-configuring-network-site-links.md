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
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>在 Lync Server 2013 中配置网络站点链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

在呼叫许可控制（CAC）配置中，你可以创建网络间策略来定义直接链接的网站之间的带宽限制。 当网络站点共享直接链接时，可以在这两个站点之间定义音频和视频连接的带宽限制。 无法使用 Lync Server 控制面板配置网络网站策略，只能通过 Lync Server 命令行管理程序使用 cmdlet 执行此操作。 你可以从 Lync Server 命令行管理程序创建、修改和删除网络网站链接（也称为网络内部站点策略）。

<div>

## <a name="to-create-a-network-site-link"></a>创建网络站点链接

1.  以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  在命令提示符处，键入以下命令，替换适用于您的配置的有效值：
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    此示例创建一个名为 Reno\_的新网络网站链接，该链接设置 Reno 和网络站点之间的带宽限制。 运行此命令之前，网络站点和带宽策略配置文件必须已经存在。

有关详细的参数说明，请参阅 Lync Server Management Shell 文档中的 "[新建-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) "。 若要检索可应用于网络站点链接的带宽策略配置文件的列表，请调用**CsNetworkBandwidthPolicyProfile** cmdlet。 有关详细信息，请参阅 Lync Server Management Shell 文档中的[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>修改网络站点链接

1.  以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  使用**CsNetworkInterSitePolicy** cmdlet 修改给定网络网站链接的属性。 您可以修改两个（或两者）或连接的网站，并且可以修改与链接关联的带宽策略配置文件。 下面是修改名为 Reno\_的网站链接的带宽策略配置文件的示例：
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

有关详细的参数说明，请参阅 Lync Server Management Shell 文档中的 "[设置 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) "。

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>删除网络网站链接

1.  以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  使用**CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。 以下示例删除 Reno\_的 "上海" 网络网站链接：
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

有关详细的参数说明，请参阅 Lync Server Management Shell 文档中的[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫许可控制 cmdlet](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

