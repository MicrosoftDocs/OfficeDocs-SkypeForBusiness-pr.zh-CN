---
title: Lync Server 2013：新的响应组应用程序功能
TOCTitle: 新的响应组应用程序功能
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398373(v=OCS.15)
ms:contentKeyID: 49312895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的响应组应用程序功能

 

_**上一次修改主题：** 2012-10-29_

通过响应组应用程序，可以按特定用途将传入呼叫路由和排列到指定人员，例如客户服务、内部技术支持或部门的常规电话支持。

以下是 Lync Server 2013 中新增的响应组应用程序功能：

  - **Manager 角色**
    
    Lync Server 2013 引入了一个新的 响应组 Manager角色。现在，响应组具有两类管理角色： 响应组 Manager 和 响应组 Administrator。 响应组 Administrator 仍可为任何响应组配置任意元素，而 Manager 只能为其拥有的响应组配置特定元素。
    
    针对管理模型的此改进可提高响应组的可伸缩性，尤其是在大型部署方案中。

  - **高可用性**
    
    响应组应用程序的高可用性支持（采用 SQL Server 镜像形式）是作为 Lync Server 2013 的高可用性的整体配置和部署的一部分实现的。如果您配置高可用性但丢失与主后端服务器的连接，则利用镜像后端服务器不会影响响应组功能。
    
    无法在 Lync Server 2013 高可用性整体配置的外部单独启用或配置 响应组应用程序的 SQL Server 镜像支持。

  - **灾难恢复**
    
    响应组应用程序的灾难恢复支持是作为成对的 前端池的配置和部署的一部分实现的，这是 Lync Server 2013 的整体灾难恢复配置的一部分。此外，响应组导入和导出 cmdlet 支持故障转移到备份池的过程以及故障回复到主池或新池的过程。如果主池中出现中断情况，可将响应组故障转移到备份池，然后在中断停止后将响应组故障回复到主池或新池。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划响应组](lync-server-2013-planning-for-response-groups.md)

