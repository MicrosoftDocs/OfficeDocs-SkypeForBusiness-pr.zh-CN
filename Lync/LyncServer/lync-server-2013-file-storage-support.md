---
title: Lync Server 2013 文件存储支持
TOCTitle: 文件存储支持
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399073(v=OCS.15)
ms:contentKeyID: 49314659
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的文件存储支持

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 的所有文件存储使用同一文件存储。文件存储支持包括以下内容：

  - 直接附加存储 (DAS) 或存储区域网络 (SAN)（包括分布式文件系统 (DFS)）以及文件存储的独立磁盘冗余阵列 (RAID) 上的文件共享。有关存储要求的详细信息，请参阅规划文档中的 [Lync Server 2013 中的前端服务器、即时消息和状态的技术要求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)和 [Lync Server 2013 中控制器的软硬件要求](lync-server-2013-hardware-and-software-requirements-for-the-director.md)。有关 Windows Server 2008 操作系统 的 DFS 的详细信息，请参阅 Windows Server 2008 中的分布式文件系统的循序渐进指南，网址为 [http://go.microsoft.com/fwlink/?linkid=202835\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=202835%26clcid=0x804)。

  - 用于文件共享的共享群集。如果使用共享群集，则应使用运行 Windows Server 2008 或 Windows Server 2008 R2 的群集服务器。使用运行较旧版本的 Windows 的群集服务器可能导致妨碍某些功能可用的权限问题。请使用群集管理器创建文件共享。有关使用群集管理器的详细信息，请参阅 Microsoft 知识库文章 284838“如何使用 Cluster.exe 创建服务器群集文件共享”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)。

