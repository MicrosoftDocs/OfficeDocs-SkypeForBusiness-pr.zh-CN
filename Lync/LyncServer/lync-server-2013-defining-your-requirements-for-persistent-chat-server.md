---
title: Lync Server 2013：定义持久聊天服务器要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e7482ab85b72168e990eaa97b2f79cb3665532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中定义持久聊天服务器要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-01-15_

在为你的组织部署持久聊天服务器之前，必须考虑以下关键问题来优化你的部署：

  - 应为持久聊天服务器启用哪些（用户配置文件）？ 持久聊天服务器由可在全局、站点、池或用户级别设置的策略启用。

  - 应该为持久聊天服务器启用多少个用户（缩放）？ 持久聊天服务器支持150000预配的用户（由策略启用），并且最多同时使用持久聊天服务器的最多80000个用户。 一个持久聊天服务器可支持 20,000 个已连接用户，一个持久聊天服务器池可具有最多 4 个活动服务器，以便总共 80,000 个同时连接的用户使用。

  - 是从早期版本的组聊天服务器迁移还是首次部署持久聊天服务器？

  - 是否存在合规性要求？ 持久聊天服务器支持合规性。 合规性服务在持久聊天服务器前端服务器上运行 collocated，而不是在之前的群组聊天服务器部署中对单独计算机的要求。 合规性是可选的，如果选择，则需要一个必须配置为存储合规性数据和事件的合规性数据库。 你可能还希望配置适配器以获取合规性数据库中的数据，并将其转换为其他格式（如 XML 文件或 Exchange 托管的存档）。

  - 您希望如何控制范围、信息隔离边界和访问？ 你可以定义**类别**以隔离这些边界，并选择哪些人被允许位于在其中每个类别中创建的会议室。

  - 您希望如何控制可以创建聊天室的人员？ 你可以配置适合你的类别的**创建者**，这些创建者可以创建聊天室。 创建者可以将其他成员分配为聊天室管理**器**，以便对会议室进行持续管理（添加或删除其他成员），具体取决于该类别配置的**AllowedMembers/DeniedMembers**的范围。

  - 您希望如何创建聊天室？ 持久聊天服务器提供基于 web 的功能，用于创建和管理会议室。 这可以从 Lync 2013 客户端启动。 你可以选择定义自定义解决方案（使用持久聊天服务器软件开发工具包（SDK））来实现你的业务需求和工作流，并配置持久聊天服务器以将用户引导到你的自定义解决方案。

  - 您希望设置哪一类外接程序？ **加载项**通过利用 Lync 2013 客户端中的 "扩展性" 窗格提供与聊天室相关的上下文来增强会议室体验。 您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。 聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。

  - 您具有哪一类高可用性和灾难恢复要求？ 持久聊天服务器支持针对高可用性的 SQL Server 镜像和 SQL Server 群集，并支持使用 SQL Server 日志传送进行灾难恢复的多达8台服务器（4主动和4备用）。

  - 是否存在法规要求？ 如果您的公司所在的国家/地区需要在国家/地区内保留数据，则可能需要将多个持久聊天服务器池部署到特定地理位置。 房间、类别或加载项不会跨越池，它仅属于一个持久聊天服务器池。 你可以管理每个持久聊天服务器池的类别、加载项和会议室集。 用户可以配置为使用类别 AllowedMembers 作用域或文件室的成员身份来访问一个或多个池中的聊天室，具体取决于你的类别的设计方式。
    
    <div>
    

    > [!IMPORTANT]  
    > 具有多个持久聊天服务器池不会为你提供更多的比例（你只能在所有持久聊天服务器池中使用80000并行连接的用户）。 支持多个持久聊天服务器池的主要原因是支持法规问题。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

