---
title: Lync Server 2013：启用持久聊天服务器策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27d87277c813c24ae36de14430bc711d991d7181
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>在 Lync Server 2013 中启用持久聊天服务器策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

在 Lync Server 2013 控制面板中，你可以使用**持久**聊天组的**持久聊天策略**页来管理全局、池、网站或用户级别的策略，包括配置默认全局策略以及为你的部署创建一个或多个其他用户和网站策略。 如果用户通过策略启用持久聊天服务器，则永久聊天服务器环境将显示在其 Lync 2013 客户端中。

<div>


> [!NOTE]  
> 在拓扑中，持久聊天服务器网站策略适用于全局、每个用户的池、每个用户的网站或每个用户。



</div>

全局策略是在部署持久聊天服务器时自动创建的，并且可以配置，但不能删除。 因为全局策略适用于所有用户，但不必对每用户进行设置。

你可以创建和配置多个网站和用户策略，这些策略与全局策略一起为持久聊天服务器启用用户。 池和网站持久聊天服务器策略替代全局持久聊天服务器策略，但仅适用于该网站的用户。 用户策略将覆盖分配有用户策略的用户的全局、池和站点策略。

<div>


> [!NOTE]  
> 若要配置和使用持久聊天服务器，必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持，然后发布拓扑。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</A>中的部署。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置持久聊天的全局策略](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中为持久聊天创建站点策略](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中为持久聊天创建用户策略](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [在 Lync Server 2013 中将持久聊天策略应用于用户或用户组](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

