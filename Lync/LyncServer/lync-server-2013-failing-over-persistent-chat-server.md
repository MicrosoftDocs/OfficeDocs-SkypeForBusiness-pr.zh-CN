---
title: Lync Server 2013：对持久聊天服务器进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中对持久聊天服务器进行故障转移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

持久聊天服务器的故障转移主要是一个手动过程。

故障转移过程基于以下假设：辅助数据中心已启动并在运行，但主持久聊天数据库所在的持久聊天服务器服务完全不可用，其中包括以下内容：

  - 持久聊天服务器主数据库和持久聊天服务器镜像数据库已关闭。

  - Lync Server 前端服务器已关闭。

该过程主要包含两个基本步骤：

  - 恢复主持久聊天数据库（mgc）。

  - 建立新的主数据库的镜像。

持久聊天合规性数据库（mgccomp）未进行故障转移。 此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。 作为持久聊天管理员，你的责任是正确管理适配器输出以避免数据丢失。

<div>

## <a name="to-fail-over-persistent-chat-server"></a>对持久聊天服务器进行故障转移

1.  从持久聊天服务器备份日志传送数据库中删除日志传送。
    
    1.  使用 SQL Server Management Studio 连接到持久聊天服务器备份 mgc 数据库所在的数据库实例。
    
    2.  打开主数据库的查询窗口。
    
    3.  使用以下命令取消日志传送：
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。

3.  按顺序将任何未应用的事务日志备份应用到辅助数据库。 有关详细信息，请参阅在上http://go.microsoft.com/fwlink/p/?linkid=247428的 "如何：应用事务日志备份（transact-sql）"。

4.  使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：
    
    1.  如果包含以下项，将断开与 mgc 数据库的所有连接：
        
        1.  **exec sp\_who2** ，用于识别与 mgc 数据库的连接。
        
        2.  **kill \<spid\> **以结束这些连接。
    
    2.  使数据库联机：
        
        1.  **使用恢复还原数据库 mgc**。

5.  在 Lync Server 命令行管理程序中，使用命令**集 CsPersistentChatState-Identity "service： atl-cs-001.litwareinc.com" – PoolState FailedOver**故障转移到 mgc 备份数据库。 请务必将持久聊天池的完全限定域名替换为 atl-cs-001.litwareinc.com。
    
    mgc 备份数据库现在充当主数据库。

6.  在 Lync Server 命令行管理程序中，使用**CsMirrorDatabase** cmdlet 为现在用作主数据库的备份数据库建立高可用性镜像。 使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。 此镜像与最初在安装期间为主数据库配置的镜像不同。 有关详细信息，请参阅在[Lync server 2013 中部署 SQL 镜像以实现后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)一节中的 "使用 Lync Server 命令行管理程序 cmdlet" 一节。

7.  设置持久聊天服务器活动服务器。 在 Lync Server 命令行管理程序中，使用**set-cspersistentchatactiveserver** cmdlet 设置活动服务器的列表。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。

    
    </div>
    
    在这种情况下，从持久聊天服务器主数据库到持久聊天服务器备份数据库的故障转移已成功完成。

</div>

</div>

<span> </span>

</div>

</div>

</div>

