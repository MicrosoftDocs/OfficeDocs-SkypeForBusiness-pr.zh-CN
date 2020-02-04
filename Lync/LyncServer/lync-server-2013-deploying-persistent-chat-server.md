---
title: Lync Server 2013：部署持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中部署持久聊天服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-03-31_

Lync server 2013，持久聊天服务器是 Lync Server 2013 基础结构的一部分。

部署持久聊天服务器需要：

  - 使用拓扑生成器定义或导入拓扑，以及随后发布你要部署的组件。

  - 准备环境以部署持久聊天服务器组件。

  - 为你的部署安装和配置持久聊天服务器组件。

使用 Lync Server 2013 企业版作为单独的池（与企业版前端服务器不 collocated）的持久聊天服务器。 持久聊天服务器要求企业版池中的 SQL Server 后端服务器存储聊天室内容和其他相关的元数据。 我们建议你在专用 SQL Server 后端服务器上安装**PersistentChatStore** ，但支持在同一 sql server 实例上 Collocating Lync Server 2013 后端服务器和**PersistentChatStore** 。

持久聊天服务器也可以与 Lync Server 2013 标准版一起部署。 在这种情况下， **PersistentChatService**前端服务器在标准版计算机上 Collocated， **PersistentChatStore**后端服务器可以部署在本地 SQL Server Express 实例上。

有关支持的 colocation 配置的详细信息，请参阅[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md)。

<div>


> [!IMPORTANT]  
> 我们不支持持久聊天服务器&nbsp;标准版的高可用性。 性能和规模将受到限制。 此外，我们仅支持新的持久聊天&nbsp;服务器标准版服务器。 我们不支持将 Lync Server 2010、群组聊天服务器升级到 Lync Server 2013&nbsp;持久聊天服务器&nbsp;标准版。



</div>

如果你的组织需要合规性支持，你可以在永久聊天服务器前端服务器上安装持久聊天服务器合规性服务。 需要单独的数据库才能实现合规性。

每个拓扑至少需要安装有 Lync Server 2013 的服务器和安装有 SQL Server 数据库软件的服务器。

使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署。 你可以选择使用拓扑生成器添加一个或多个持久聊天服务器池。 按照相同的部署说明部署多个持久聊天服务器池，就像处理任何池一样。 有关详细信息，请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。

有关可用拓扑和安装持久聊天服务器的技术和软件要求的详细信息，请参阅规划文档中的 "[在 lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)"、"计划文档"、"部署文档" 或 "操作文档" 中的 "永久聊天服务器" 的[2013 工作方式](lync-server-2013-how-persistent-chat-server-works.md)，以及可支持性文档中的[lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。

单个持久聊天服务器前端服务器可以支持20000活动用户。 你可以拥有最多4个活动前端服务器的持久聊天服务器池，这些服务器总共支持80000并行用户。

虚拟服务器也支持持久聊天服务器。 如果虚拟服务器与物理服务器的规范相匹配，则该虚拟服务器最多可以支持最多20000个并发用户。

<div>


> [!IMPORTANT]  
> 持久聊天服务器必须安装在 NTFS 文件系统上才能帮助强制实施文件系统安全。 FAT32 不是持久聊天服务器支持的文件系统。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中持久聊天服务器的工作方式](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 中的持久聊天服务器的部署清单](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 中持久聊天服务器的技术要求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中设置持久聊天服务器的系统和基础结构](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中将持久聊天服务器添加到部署](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [在 Lync Server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md)

  - [在 Lync Server 2013 中添加持久聊天管理员](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [在 Lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)

  - [使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 排查持久聊天服务器配置故障](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [在 Lync Server 2013 中对持久聊天服务器进行故障转移和故障回复](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

