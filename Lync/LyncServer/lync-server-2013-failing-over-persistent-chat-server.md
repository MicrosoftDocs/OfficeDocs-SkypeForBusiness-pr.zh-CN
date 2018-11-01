---
title: Lync Server 2013：对持久聊天服务器进行故障转移
TOCTitle: 对持久聊天服务器进行故障转移
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204772(v=OCS.15)
ms:contentKeyID: 49312354
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中对持久聊天服务器进行故障转移

 

_**上一次修改主题：** 2014-02-05_

持久聊天服务器故障转移主要设计为一个手动过程。

故障转移过程基于一种假设，即，辅助数据中心正在运行，但 持久聊天主数据库所在的 持久聊天服务器服务完全不可用，其中包括：

  - 持久聊天服务器主数据库和 持久聊天服务器镜像数据库不可用。

  - Lync Server前端服务器不可用。

该过程主要包含两个基本步骤：

  - 恢复主 持久聊天数据库 (mgc)。

  - 建立新的主数据库的镜像。

持久聊天合规性数据库 (mgccomp) 未进行故障转移。此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。您作为 持久聊天管理员有责任正确管理适配器输出以避免丢失数据。

## 对 持久聊天服务器进行故障转移

1.  从 持久聊天服务器备份日志传送数据库取消日志传送。
    
    1.  使用 SQL Server Management Studio 连接到 持久聊天服务器备份 mgc 数据库所在的数据库实例。
    
    2.  打开主数据库的查询窗口。
    
    3.  使用以下命令取消日志传送：
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。

3.  按顺序将任何未应用的事务日志备份应用到辅助数据库。有关详细信息，请参阅“如何：应用事务日志备份 (Transact-SQL)”，网址为 http://go.microsoft.com/fwlink/?linkid=247428\&clcid=0x804

4.  使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：
    
    1.  如果包含以下项，将断开与 mgc 数据库的所有连接：
        
        1.  **exec sp\_who2**，用于识别与 mgc 数据库的连接。
        
        2.  **kill \<spid\>**，用于断开这些连接。
    
    2.  使数据库联机：
        
        1.  **通过恢复还原数据库 mgc**。

5.  在 Lync Server 命令行管理程序中，使用命令 **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** 故障转移到 mgc 备份数据库。确保用您的“持久聊天”池的完全限定的域名替换 atl-cs-001.litwareinc.com。
    
    mgc 备份数据库现在充当主数据库。

6.  在 Lync Server 命令行管理程序中，使用 **Install-CsMirrorDatabase** cmdlet 来建立现在充当主数据库的备份数据库的高可用性镜像。使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。此镜像与最初在安装期间为主数据库配置的镜像不同。有关详细信息，请参阅[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)中的“使用 Lync Server 命令行管理程序 Cmdlet”一节。

7.  设置 持久聊天服务器活动服务器。从 Lync Server 命令外壳中，使用 **Set-CsPersistentChatActiveServer** cmdlet 设置活动服务器列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。
    
    此时，从 持久聊天服务器主数据库到 持久聊天服务器备份数据库的故障转移即成功完成。

