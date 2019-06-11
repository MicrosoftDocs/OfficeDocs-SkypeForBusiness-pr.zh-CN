---
title: Lync Server 2013：设置系统平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>在 Lync Server 2013 中设置系统平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

在开始部署持久聊天服务器之前, 必须在满足服务器上的系统要求的硬件上安装所需操作系统:

有关运行 Lync Server 2013、数据库服务器和文件服务器的服务器支持的硬件的详细信息, 请参阅支持文档中的[Lync Server 2013 支持的硬件](lync-server-2013-supported-hardware.md)。 有关受支持的操作系统和数据库软件的详细信息, 请参阅支持文档中的[Lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。 有关 Windows 更新要求的详细信息, 请参阅支持文档中[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。

持久聊天服务器前端服务器**PersistentChatService**可在 Lync Server 2013 Enterprise Edition 池中的一个或多个独立计算机上部署。 不能在 Lync Server 企业版前端服务器上 collocated。 引导程序可以部署持久聊天服务器, 就像其他 Lync 服务器角色一样。 **用于文件上传/下载的持久聊天 Web 服务**和**用于聊天室管理的持久聊天 web 服务**是在 Lync Server 2013 前端服务器上部署的 web 组件。

单个持久聊天服务器前端服务器可以支持20000活动用户。 你可以拥有最多4个活动前端的持久聊天服务器池, 同时支持80000并发用户总数。 持久的聊天后端服务器 " **PersistentChatStore**" 存储聊天室和类别。 我们建议你在企业版池中的专用 SQL Server 后端服务器上安装**PersistentChatStore** ;虽然我们支持在同一 SQL Server 实例上 collocating Lync Server 2013 后端服务器和**PersistentChatStore** 。

如果你的组织需要合规性支持, 你可以使用拓扑生成器安装它。 持久聊天服务器合规性服务与持久聊天服务器前端服务器安装在同一台计算机上。 需要单独的数据库才能实现合规性。 有关持久聊天服务器的合规性要求的详细信息, 请参阅规划文档中的[Lync server 2013 中的 "持久聊天服务器计划](lync-server-2013-planning-for-persistent-chat-server.md)"。

每个拓扑至少需要安装有 Lync Server 2013 的服务器和安装有 SQL Server 数据库软件的服务器。 拓扑生成器支持多个持久聊天服务器池。 按照相同的部署说明部署多个持久聊天服务器池, 就像在部署文档中[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)的任何池一样。

您也可以将持久聊天服务器与 Lync Server 2013 标准版一起部署。 在这种情况下, **PersistentChatService**前端服务器在标准版服务器上 collocated, 并且你可以在本地 SQL Server Express 实例上部署**PersistentChatStore**后端服务器。

<div>


> [!IMPORTANT]  
> 我们不支持持久聊天服务器&nbsp;标准版提供高可用性。 性能和规模将受到限制。 此外, 我们仅支持新的持久聊天&nbsp;服务器标准版服务器部署。 我们不支持将 Lync Server 2010、群组聊天服务器升级到 Lync Server 2013&nbsp;持久聊天服务器&nbsp;标准版。



</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)  


[支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)  
[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)  
[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

