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
ms.openlocfilehash: ab8049097383932bacb198cd8eb4fe6e96917feb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中部署持久聊天服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-31_

Lync Server 2013，持久聊天服务器是 Lync Server 2013 基础结构的一部分。

部署持久聊天服务器要求您执行以下操作：

  - 使用拓扑生成器定义或导入您的拓扑，并随后发布您要部署的组件。

  - 准备部署持久聊天服务器组件的环境。

  - 为您的部署安装和配置持久聊天服务器组件。

在 Lync Server 2013 Enterprise Edition 中将持久聊天服务器作为单独的池（而不是与 Enterprise Edition 前端服务器的并置）一起使用。 持久聊天服务器要求企业版池中的 SQL Server 后端服务器存储聊天室内容和其他相关元数据。 我们建议您在专用 SQL Server 后端服务器上安装**PersistentChatStore** ，但支持在同一 sql server 实例上并置 Lync Server 2013 后端服务器和**PersistentChatStore** 。

持久聊天服务器也可以使用 Lync Server 2013 Standard Edition 进行部署。 在这种情况下， **PersistentChatService**前端服务器在 Standard Edition 计算机上为并置， **PersistentChatStore**后端服务器可以部署在本地 SQL Server Express 实例上。

有关支持的 colocation 配置的详细信息，请参阅[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

<div>


> [!IMPORTANT]  
> 我们不支持持久聊天服务器&nbsp;Standard Edition 的高可用性。 性能和规模将受到限制。 此外，我们仅支持新的持久聊天&nbsp;服务器 Standard Edition server。 我们不支持将 Lync Server 2010、Group Chat Server 升级为 Lync Server 2013&nbsp;持久聊天服务器&nbsp;Standard Edition。



</div>

如果您的组织需要合规性支持，则可以在持久聊天服务器前端服务器上安装持久聊天服务器合规性服务。 合规性需要单独的数据库。

每个拓扑至少需要安装了 Lync Server 2013 的服务器和一个安装了 SQL Server 数据库软件的服务器。

使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署。 您可以选择使用拓扑生成器添加一个或多个持久聊天服务器池。 按照与对任意池相同的方式部署多个持久聊天服务器池的相同部署说明进行操作。 有关详细信息，请参阅部署文档中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

有关可用拓扑的详细信息以及安装持久聊天服务器的技术和软件要求，请参阅规划文档中的 "在[lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)"、规划文档、部署文档或操作文档中的[持久聊天服务器的工作2013原理](lync-server-2013-how-persistent-chat-server-works.md)，以及可支持性文档中的[lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅部署文档中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

一个持久聊天服务器前端服务器可支持20000个活动用户。 您可以拥有一个持久聊天服务器池和最高4个活动前端服务器，共支持80000个并发用户。

虚拟服务器上也支持持久聊天服务器。 如果虚拟服务器与物理服务器的规格一致，则最多可支持 20,000 个并发用户。

<div>


> [!IMPORTANT]  
> 必须在 NTFS 文件系统上安装持久聊天服务器，以帮助强制实施文件系统安全。 FAT32 不是持久聊天服务器支持的文件系统。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中持久聊天服务器的工作原理](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 中持久聊天服务器的部署清单](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 中持久聊天服务器的技术要求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [在 Lync Server 2013 中为持久聊天服务器设置系统和基础结构](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [将持久聊天服务器添加到 Lync Server 2013 中的部署](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [在 Lync Server 2013 中安装持久聊天服务器](lync-server-2013-installing-persistent-chat-server.md)

  - [在 Lync Server 2013 中添加持久聊天管理员](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [在 Lync Server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)

  - [使用 Windows PowerShell cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中使用 Windows PowerShell cmdlet 对持久聊天服务器配置进行故障排除](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [在 Lync Server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [在 Lync Server 2013 中对持久聊天服务器进行故障转移和故障回复](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

