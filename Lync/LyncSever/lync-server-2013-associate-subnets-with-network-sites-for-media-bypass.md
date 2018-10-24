---
title: 将子网与网络站点相关联以启用媒体绕过
TOCTitle: 将子网与网络站点相关联以启用媒体绕过
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398401(v=OCS.15)
ms:contentKeyID: 49312965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将子网与网络站点相关联以启用媒体绕过

 

_**上一次修改主题：** 2012-09-12_

> [!NOTE]  
> 本主题假设已配置了媒体旁路全局设置，并为媒体旁路配置了网络区域和网络站点。



网络中的每个子网必须与特定网络站点相关联。这是因为子网信息用于确定端点所在的网络站点。当会话双方的位置已知时，媒体旁路可以确定将媒体发送到何处进行处理。

媒体旁路对于将子网与网络站点关联没有特殊要求。要在拓扑中的子网和网络站点之间建立关联，请执行[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)中的步骤。

## 后续步骤：创建带宽策略配置文件

为实现媒体旁路而将子网与网络站点关联后，必须创建一个或多个带宽策略配置文件，将子网区分为具有良好连接和不具有良好连接，从而方便进行媒体旁路。其网络站点没有带宽限制的网络区域中的所有子网均具有良好的连接，因此这些子网可以使用媒体旁路。

有关配置带宽策略配置文件的过程，请参阅[创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。

