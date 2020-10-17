---
title: Lync Server 2013：定义持久聊天服务器的要求
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
ms.openlocfilehash: e63e7af0dca758f6ac543bb0373d2cbb0d953ba0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504299"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>定义您的组织在 Lync Server 2013 中的持久聊天服务器的要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-01-15_

在为您的组织部署持久聊天服务器之前，必须考虑以下关键问题来优化您的部署：

  - 应为持久聊天服务器启用 (用户配置文件) 的用户？ 持久聊天服务器是由可在全局、站点、池或用户级别设置的策略启用的。

  - 应为持久聊天服务器启用 (比例) 的用户数？ 持久聊天服务器支持150000预配的用户 (由策略) 启用，最多使用持久聊天服务器的最多80000个并发用户。 一个持久聊天服务器可支持20000个连接的用户，一个持久聊天服务器池最长可包含4个活动服务器，共80000个并行连接的用户。

  - 您是从早期版本的组聊天服务器进行迁移，还是首次部署持久聊天服务器？

  - 是否有合规性要求？ 持久聊天服务器支持符合性。 合规性服务在持久聊天服务器前端服务器上运行并置，而不是对以前的组聊天服务器部署中的单独计算机的要求。 合规性是可选的，如果选择它，则需要必须配置为存储合规性数据和事件的合规性数据库。 您可能需要配置适配器以获取合规性数据库中的数据，并将其转换为其他格式 (如 XML 文件或 Exchange 托管存档) 。

  - 您希望如何控制范围、信息隔离边界和访问？您可以定义**类别**来分隔这些边界，并选择可进入在每种类别中创建的聊天室的用户。

  - 您希望如何控制可创建聊天室的用户？您可以配置适合您的类别的**创建者**，他们可以创建聊天室。创建者可将其他成员指定为**聊天室管理员**，以便根据按类别配置的 **AllowedMembers/DeniedMembers** 的范围对聊天室进行持续管理（添加或删除其他成员）。

  - 您希望如何创建聊天室？ 持久聊天服务器为创建和管理会议室提供了基于 web 的功能。 这可以从 Lync 2013 客户端启动。 您可以选择使用持久聊天服务器软件开发工具包 (SDK) # A3 来定义自定义解决方案 (，以实现您的业务需求和工作流，并配置持久聊天服务器以将用户引导到您的自定义解决方案。

  - 您希望设置哪一类外接程序？ **外接程序** 通过利用 Lync 2013 客户端中的扩展性窗格来提供与聊天室相关的上下文，增强了会议室体验。 您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。 聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。

  - 您具有哪一类高可用性和灾难恢复要求？ 持久聊天服务器支持 SQL Server 镜像和 SQL Server 群集功能，以实现高可用性，并支持使用 SQL Server 日志传送功能的延伸池中的最多8台服务器 (4 个活动和4个备用) ，以实现灾难恢复。

  - 是否有管理要求？ 如果贵公司所在的国家/地区内的数据需要保留在国家/地区内，您可能需要将多个持久聊天服务器池（每个本地）部署到特定地理位置。 会议室、类别或加载项不会跨越池，仅属于一个持久聊天服务器池。 您可以管理每个持久聊天服务器池的一组类别、外接程序和文件室。 可以将用户配置为在一个或多个池中使用类别 AllowedMembers 作用域或文件室的成员范围来访问聊天室，具体取决于您设计类别的方式。
    
    <div>
    

    > [!IMPORTANT]  
    > 具有多个持久聊天服务器池不会为您提供更多的比例 (您仍可以在) 的所有持久聊天服务器池中仅有80000并发连接的用户。 支持多个持久聊天服务器池的主要原因是为了支持法规方面的问题。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

