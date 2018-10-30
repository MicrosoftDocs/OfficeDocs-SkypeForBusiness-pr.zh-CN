---
title: Lync Server 2013：持久聊天服务器的技术要求
TOCTitle: 持久聊天服务器的技术要求
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398495(v=OCS.15)
ms:contentKeyID: 49313119
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中持久聊天服务器的技术要求

 

_**上一次修改主题：** 2016-12-08_

承载 持久聊天服务器的每台计算机必须有权访问包含以下组件的现有 Lync Server 2013 拓扑：

  - **Lync Server 2013前端服务器。** 前端服务器是会话初始协议 (SIP) 路由的基础，它使得在运行 持久聊天服务器与 持久聊天功能的计算机之间通信成为可能。在开始部署 持久聊天服务器之前，请根据您组织的具体情况验证 Lync Server 2013 Standard Edition 或 Lync Server前端池的部署以及任何其他运行 Lync Server 的内部计算机的部署。

以下几节介绍 持久聊天服务器和存储 持久聊天数据的数据库的特定要求。

## 持久聊天服务器要求

有关部署 Lync Server 的推荐硬件和 持久聊天服务器最新版本的详细信息，请参阅可支持性文档中的 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

有关 Lync Server 和 持久聊天服务器的服务器和工具操作系统支持的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

有关部署 持久聊天服务器所需的其他软件的详细信息，请参阅下表。

### 持久聊天服务器的必备软件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>软件</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>消息队列</p></td>
<td><p>由 持久聊天服务器和 持久聊天合规性服务（如果已部署）使用。</p></td>
</tr>
</tbody>
</table>


## 持久聊天服务器的数据库要求

持久聊天服务器使用 持久聊天数据库存储聊天历史记录、配置和用户设置数据。（可选）它使用 持久聊天合规性数据库存储合规性数据。

> [!IMPORTANT]
> 持久聊天数据库 (mgc) 和合规性数据库 (mgccomp) 可以位于同一 SQL Server 实例或不同 SQL Servers 中。


若要准备数据库服务器平台，请确保每台计算机均满足硬件要求，然后安装必备软件。

持久聊天数据库服务器的服务器平台的硬件要求与 Lync Server 后端数据库服务器相同。有关详细信息，请参阅可支持性文档中的 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

在数据库服务器上，确保安装了以下软件应用程序之一：

  - Microsoft SQL Server 2012。有关如何安装 Microsoft SQL Server 2012 的详细信息，请参阅位于 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559) 上的“安装 SQL Server 2012”。

  - Microsoft SQL Server 2008 R2。有关如何安装 Microsoft SQL Server 2008 R2 的详细信息，请参阅位于 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702) 上的“SQL Server 安装 (SQL Server 2008 R2)”。

## 持久聊天服务器的证书要求

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅部署文档中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

