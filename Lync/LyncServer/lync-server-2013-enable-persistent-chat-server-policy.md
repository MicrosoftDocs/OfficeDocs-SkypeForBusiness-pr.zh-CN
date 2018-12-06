---
title: Lync Server 2013：启用持久聊天服务器策略
TOCTitle: 启用持久聊天服务器策略
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205056(v=OCS.15)
ms:contentKeyID: 49313503
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用持久聊天服务器策略

 

_**上一次修改主题：** 2012-10-06_

在 Lync Server 2013 控制面板中，可使用“持久聊天”组的“持久聊天策略”页管理全局级别、池级别、站点级别或用户级别的策略，包括为部署配置默认全局策略和创建一个或多个其他用户和站点策略。如果根据策略为用户启用了 持久聊天服务器，则 持久聊天服务器环境将出现在其 Lync 2013 客户端中。

> [!NOTE]  
> 在拓扑中，将全局、每用户工具或用户网站或每用户应用 持久聊天服务器网站策略。



在部署 持久聊天服务器时会自动创建全局策略，可以对全局策略进行配置，但不能将其删除。因为全局策略适用于所有用户，但不必对每用户进行设置。

可以创建并配置多个站点和用户策略，这些策略可与全局策略一起使用，以支持 持久聊天服务器用户。池和站点 持久聊天服务器策略覆盖全局 持久聊天服务器策略，但仅适用于该站点的用户。用户策略将覆盖分配有用户策略的用户的全局、池和站点策略。

> [!NOTE]  
> 要配置和使用 持久聊天服务器，则必须先使用 拓扑生成器将 持久聊天服务器支持添加到拓扑，然后发布该拓扑。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">在 Lync Server 2013 中将持久聊天服务器添加到部署</a>。



## 本节内容

  - [在 Lync Server 2013 中配置持久聊天的全局策略](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中为持久聊天创建站点策略](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中为持久聊天创建用户策略](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中将持久聊天策略应用于用户或用户组](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

