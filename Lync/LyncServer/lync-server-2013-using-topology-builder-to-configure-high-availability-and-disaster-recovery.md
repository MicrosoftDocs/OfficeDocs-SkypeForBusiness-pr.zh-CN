---
title: Lync Server 2013：使用拓扑生成器配置高可用性和灾难恢复
TOCTitle: 使用拓扑生成器配置高可用性和灾难恢复
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205172(v=OCS.15)
ms:contentKeyID: 49313921
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用拓扑生成器配置高可用性和灾难恢复

 

_**上一次修改主题：** 2012-10-06_

在 拓扑生成器中执行以下步骤，以便为 持久聊天服务器配置高可用性和灾难恢复。

1.  添加镜像数据库和日志和日志传送辅助数据库 SQL Server 存储。

2.  编辑 持久聊天服务器服务属性实现以下操作：
    
    1.  为主数据库启用镜像。
    
    2.  添加主镜像 SQL Server 存储。
    
    3.  启用 SQL Server 日志传送数据库。
    
    4.  添加 SQL Server 日志传送辅助 SQL Server 存储。
    
    5.  为辅助数据库添加 SQL Server 存储镜像。
    
    6.  发布拓扑。

