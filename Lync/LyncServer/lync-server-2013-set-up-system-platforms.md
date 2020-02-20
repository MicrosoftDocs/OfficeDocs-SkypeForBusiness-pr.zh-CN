---
title: Lync Server 2013：设置系统平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec8b2e923b4c0815449ce7fd7beb2624fe728623
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>在 Lync Server 2013 中设置系统平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在开始部署持久聊天服务器之前，必须在满足服务器上的系统要求的硬件上安装所需的操作系统：

有关运行 Lync Server 2013、数据库服务器和文件服务器的服务器支持的硬件的详细信息，请参阅可支持性文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。 有关受支持的操作系统和数据库软件的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。 有关 Windows 更新要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。

可以在 Lync Server 2013 Enterprise Edition 池中的一个或多个独立计算机上部署持久聊天服务器前端服务器（ **PersistentChatService**）。 不能在 Lync Server Enterprise Edition 前端服务器上并置。 引导程序可以部署持久聊天服务器，就像其他 Lync Server 角色一样。 **用于文件上传/下载的持久聊天 Web 服务**和**聊天室管理的持久聊天 web**服务是在 Lync Server 2013 前端服务器上部署的 web 组件。

一个持久聊天服务器前端服务器可支持20000个活动用户。 您可以拥有一个持久聊天服务器池和最高4个活动前端支持总共80000个并发用户。 持久的聊天后端服务器**PersistentChatStore**，存储聊天室和类别。 我们建议您在企业版池中的专用 SQL Server 后端服务器上安装**PersistentChatStore** ;尽管我们在同一 SQL Server 实例上支持并置 Lync Server 2013 后端服务器和**PersistentChatStore** 。

如果你的组织需要合规性支持，可以使用拓扑生成器安装它。 持久聊天服务器合规性服务与持久聊天服务器前端服务器安装在同一台计算机上。 合规性需要单独的数据库。 有关持久聊天服务器的合规性要求的详细信息，请参阅规划文档中的在[Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

每个拓扑至少需要安装了 Lync Server 2013 的服务器和一个安装了 SQL Server 数据库软件的服务器。 拓扑生成器支持多个持久聊天服务器池。 按照部署文档中部署[Lync server 2013](lync-server-2013-deploying-lync-server.md)的任何池的方式部署多个持久聊天服务器池的相同部署说明进行操作。

您还可以使用 Lync Server 2013 Standard Edition 部署持久聊天服务器。 在这种情况下， **PersistentChatService**前端服务器在 Standard Edition Server 上为并置，您可以在本地 SQL Server Express 实例上部署**PersistentChatStore**后端服务器。

<div>


> [!IMPORTANT]  
> 我们不支持持久聊天服务器&nbsp;标准版实现高可用性。 性能和规模将受到限制。 此外，我们仅支持新的持久聊天&nbsp;服务器 Standard Edition server 部署。 我们不支持将 Lync Server 2010 （Group Chat Server）升级到 Lync Server 2013&nbsp;持久聊天服务器&nbsp;Standard Edition。



</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)  
[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

