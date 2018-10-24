---
title: 在位于外围网络外的观察程序节点上安装证书
TOCTitle: 在位于外围网络外的观察程序节点上安装证书
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49888488
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在位于外围网络外的观察程序节点上安装证书

 

_**上一次修改主题：** 2016-12-08_

在位于企业外部（如外部综合事务观察程序节点）或跨 Active Directory 域服务 信任边界的外围网络（如 Lync Server 边缘服务器）中运行的 System Center Operations Manager 代理可能要求配置 System Center Operations Manager 网关服务器。此服务器角色允许与根管理服务器没有信任关系的代理发出警报。有关详细信息，请参阅 System Center Operations Manager TechNet 库（网址为 [http://go.microsoft.com/fwlink/?linkid=268703\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268703%26clcid=0x804)）中的“管理 Operations Manager 2007 中的网关服务器”。

如果在这些位置之一部署了代理，则还需要请求和配置一个支持观察程序节点向 System Center Operations Manager 发送警报的证书。为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。若要获取详细信息和下载这些实用程序，请参阅“利用证书生成向导轻松获取未加入域的代理的证书”博客文章，网址为 [http://go.microsoft.com/fwlink/?linkid=267421\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=267421%26clcid=0x804)。

