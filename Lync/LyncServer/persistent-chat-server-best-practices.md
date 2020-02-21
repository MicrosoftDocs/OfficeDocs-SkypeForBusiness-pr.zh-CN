---
title: 持久聊天服务器最佳实践
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b613e3ce5c70b9bad7de2ef821d1e0f41e27b956
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>持久聊天服务器最佳实践

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

创建类别和持久聊天室并设计范围和成员资格时，以下提示可帮助您进行规划：

  - 如果贵公司不需要符合道德的墙，请不要缩小类别树中的范围。 将所有用户放在一个类别的范围内，并在该类别中创建所有聊天室。 随后，仅使用成员身份列表来授予或限制对每个聊天室的访问权限。

  - 在大多数情况下，应使用户能够创建新的聊天室，以便可以随时启动有关新主题的讨论。 若要执行此操作，**创建者**列表与**AllowedMembers**列表相同。 但是，如果您希望仅允许中央支持团队或指定的用户创建聊天室，则将创建**者**列表作为相应的子集。

  - 为每个聊天室提供一个完整的名称和说明摘要，描述它在组织中的适合位置。 由于用户在使用聊天室时看不到类别名称，因此您不能依赖类别名称来帮助用户确定聊天室的预期讨论论坛。

  - 如果您有特定的命名约定或其他访问控制或验证实现，则您可能需要具有自定义会议室创建工作流。 通过持久聊天配置，您可以自定义**RoomManagementUrl**到您承载的内容。 例如，当用户单击其 Lync 客户端中**的 "创建聊天室**" 时，可以将它们重定向到您的自定义解决方案。

  - 通过将其他业务数据引入聊天室，创建各种外接程序，以帮助增强聊天室的体验。 管理员必须注册他们希望在系统中允许的外接程序。 聊天室管理员和创建者可以从允许的加载项列表中选择与各自的聊天室最相关的加载项列表。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理类别、聊天室和外接程序](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

