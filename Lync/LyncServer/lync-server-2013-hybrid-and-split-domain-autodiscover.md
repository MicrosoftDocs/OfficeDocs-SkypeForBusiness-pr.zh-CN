---
title: 混合和拆分域 - 自动发现
TOCTitle: 混合和拆分域 - 自动发现
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945652(v=OCS.15)
ms:contentKeyID: 52061119
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 混合和拆分域 - 自动发现

 

_**上一次修改主题：** 2013-02-14_

共享 SIP 地址空间也称为*拆分域* 部署或*混合* 部署，它是一种跨本地部署和联机环境部署用户的配置。期望的结果是无论用户的主服务器位于何处（本地或联机），用户都能登录到部署并被重定向到其主服务器位置。若要实现此目的，需要使用 Lync Server 2013 的自动发现功能将在线用户重定向到在线拓扑。为此，可通过使用 Lync Server 命令行管理程序、**Get-CsHostingProvider** cmdlet 以及 **Set-CsHostingProvider** cmdlet 来配置自动发现统一资源定位器 (URL)。

## 拆分域部署的移动性

您需要收集和记录下列部署的属性：

  - 从 Lync Server 命令行管理程序，键入
    
        Get-CsHostingProvider

  - 在结果中，查找属性为 **ProxyFQDN** 的在线提供商。例如，sipfed.online.lync.com。

  - 记录 ProxyFQDN 的值。

  - 在本地 Lync Server 控制面板中启用联盟，以允许与在线提供商建立联盟。

  - 为在线提供商启用联盟。默认情况下，对所有在线用户启用域联盟，因此在线用户可以与所有域通信。

  - 如果要定义阻止域和允许域，请确定要明确允许或阻止的域。

  - 对于在线联盟，您必须规划防火墙例外、证书和 DNS 主机（如使用 IPv6，则为 A 或 AAAA）记录。此外，您还必须配置联盟策略。有关详细信息，请参阅[规划 Lync Server 和 Office Communications Server 联盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。

