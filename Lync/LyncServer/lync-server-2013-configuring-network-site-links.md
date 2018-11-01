---
title: 配置网络站点链接
TOCTitle: 配置网络站点链接
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521023(v=OCS.15)
ms:contentKeyID: 49313380
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置网络站点链接

 

_**上一次修改主题：** 2012-11-01_

在呼叫允许控制 (CAC) 配置中，可以创建定义直接链接的站点之间的带宽限制的网络站点间策略。当两个网络站点共享一条直接链接时，可定义这两个站点之间的音频和视频连接的带宽限制。不能使用 Lync Server 控制面板配置网络站点策略，只能通过使用 Lync Server 命令行管理程序中的 cmdlet 来实现。可以在 Lync Server 命令行管理程序中创建、修改和删除网络站点链接（又称为网络站点间策略）。

## 创建网络站点链接

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符处，键入以下命令，取代有效的配置值：
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    本示例创建名为 Reno\_Portland 的新网络站点链接，该链接设置 Reno 和 Portland 网络站点之间的带宽限制。运行此命令之前，必须已存在网络站点和带宽策略配置文件。

有关详细的参数说明，请参阅 Lync Server 命令行管理程序文档中的 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)。要检索可应用于网络站点链接的带宽策略配置文件列表，请调用 **Get-CsNetworkBandwidthPolicyProfile** cmdlet。有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

## 修改网络站点链接

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  使用 **Set-CsNetworkInterSitePolicy** cmdlet 修改给定网络站点链接的属性。可以修改连接站点中的任一个（或两个），也可以修改与链接关联的带宽策略配置文件。以下是修改名为 Reno\_Portland 的站点链接的带宽策略配置文件的示例：
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

有关详细的参数说明，请参阅 Lync Server 命令行管理程序文档中的 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)。

## 删除网络站点链接

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  使用 **Remove-CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。以下示例删除 Reno\_Portland 网络站点链接：
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

有关详细的参数说明，请参阅 Lync Server 命令行管理程序文档中的 [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。

## 另请参阅

#### 概念

[呼叫允许控制 Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/)  

#### 其他资源

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

