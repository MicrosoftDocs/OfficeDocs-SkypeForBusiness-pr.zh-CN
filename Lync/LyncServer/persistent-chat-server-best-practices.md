---
title: 持久聊天服务器最佳做法
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>持久聊天服务器最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-06_

当你创建类别和持久聊天室并设计你的范围和成员身份时, 以下提示可帮助你进行规划:

  - 如果您的公司不需要符合道德的墙, 请不要缩小类别树中的范围。 将所有用户放在一个类别的范围内, 并创建该类别中的所有聊天室。 随后, 仅使用成员身份列表授予或限制对每个聊天室的访问权限。

  - 在大多数情况下, 你应使用户能够创建新的聊天室, 以便可以随时开始讨论新主题。 通过使**创建者**列表与**AllowedMembers**列表相同来执行此操作。 但是, 如果你希望仅允许中央支持团队或指定用户创建聊天室, 则将创建**者**列表作为相应的子集。

  - 为每个聊天室提供一个完整的名称和说明摘要, 描述它与你的组织相匹配的位置。 由于用户使用聊天室时看不到类别名称, 因此不能依赖类别名称来帮助用户确定聊天室的预期讨论论坛。

  - 如果你有某些命名约定或其他访问控制或验证实现, 你可能需要具有自定义聊天室创建工作流。 持久聊天配置使你能够将**RoomManagementUrl**自定义到你托管的内容。 例如, 当用户在其 Lync 客户端中单击 "**创建聊天室**" 时, 可以将其重定向到你的自定义解决方案。

  - 通过将其他业务数据引入聊天室, 创建各种可帮助增强聊天室体验的加载项。 管理员必须在系统中注册要允许的加载项。 聊天室管理员和创建者可以从允许的加载项列表中选择与各自的聊天室最相关的加载项。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理类别、聊天室和加载项](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

