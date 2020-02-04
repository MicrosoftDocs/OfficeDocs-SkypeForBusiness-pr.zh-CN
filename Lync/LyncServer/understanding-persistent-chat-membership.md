---
title: 了解持久聊天成员身份
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>了解持久聊天成员身份

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-22_

用户对持久聊天室的访问权限由成员身份管理;用户必须是聊天室的成员才能发布和阅读邮件。 只有具有 "聊天室" 的指定隶属关系的**演示者**才允许使用**发布到 Auditorium 会议室**。 Auditorium 是一种类型的聊天室（另一种是**正常**情况），其中只有演示者可以发布，并且所有人都可以阅读。

此外，持久聊天室在类别规则下运行。 有关类别的详细信息，请参阅在[Lync Server 2013 中管理类别、会议室和外接程序](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主题后面部分的 "类别范围的工作原理" 和 "会议室类别策略" 部分。

持久聊天管理员可以创建和管理聊天室类别。 在创建和管理聊天室类别的过程中，持久聊天管理员可以配置主体（Active Directory 域服务组、容器和用户），这些主体有权访问属于特定类别的聊天室的成员或访问者。

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory 域服务和持久聊天

持久聊天服务器依赖于内部持久聊天用户池的 Active Directory。 安装持久聊天（客户端）后，您可以将用户和用户组域添加到聊天室类别。 然后，你可以将这些用户和组添加到聊天室类别的成员身份。

<div>


> [!IMPORTANT]  
> 您必须确保要对其永久聊天室进行更改的用户没有重复的名称。 如果存在重复的用户名，请将其更改为不同的名称，以取消阻止用户进行这些更改。 如果用户在 Active Directory 中具有重复的名称，并尝试在其聊天室中进行更改，则会显示一条错误消息，提示用户联系管理员进行解析。



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>类别作用域的工作原理

类别指定了所有用户和组，这些用户和组可以是该类别中的持久聊天室的成员身份列表中的成员，具体取决于其**AllowedMembers**属性。 例如，如果将类别的**AllowedMembers**设置为 contoso.com，则可以将*contoso*中的任何组或用户添加到该类别中的聊天室。 如果将类别的**AllowedMembers**设置为 "*销售*"，则只能将此通讯组列表中的组和用户添加为该类别中的聊天室。 同样，"**创建者**" 属性使您能够控制哪些人可以创建该类别的聊天室。 在创建聊天室后， **AllowedMembers**组中的任何人都可以被指定为**管理者**进行持续管理操作（例如，成员身份更改和审批）。

定义类别的**AllowedMembers**和**创意者**具有以下优点：

  - 该类别中的所有聊天室都绑定了在类别级别设置的限制。 您可以使用此限制，根据业务需求和访问策略隔离聊天室。

  - "**创建者**" 列表中的用户可以在该类别中创建新的聊天室。 如果你想要实现组织中受限制的人员可以创建聊天室的系统，则可以使用此控件来满足该要求。

</div>

<div>

## <a name="room-category-strategies"></a>会议室类别策略

类别的**AllowedMembers**必须包括所有将在此类别中使用任何持久聊天室的用户。 你可能希望定义一个或多个类别，以指定可以搜索和参与聊天室的人员，具体取决于保护业务数据和确保访问级别的要求。 如果你希望仅允许特定的一组用户（中央帮助台，或仅全职员工）创建聊天室，则可以将类别的**创建者**范围限定为满足该要求。

类别也可用于创建符合道德的留言板。 符合道德的墙可防止组织的任何利益冲突。 例如，管理员可以仅在贸易类别中创建聊天室，而另一类别中的聊天室只能由分析员使用。

<div>


> [!NOTE]  
> 在 Lync Server 2013 的持久聊天服务器中，我们不支持对联盟用户的访问。 如果以前版本的持久聊天服务器中存在来自联盟用户的聊天，则将迁移这些聊天。 将联盟用户添加为已禁用主体。



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>将成员收缩到用户组

将域添加到类别时，您可以使用域中包含其组对象的用户组，以便将其指定为该类别中的会议室成员。

我们建议你使用 Active Directory 容器（如域和组织单元）来定义类别的**AllowedMembers**和**创建者**。 你可以将任何域中的对象添加到**AllowedMembers**或**创建者**列表。 只有**AllowedMembers**或 "**创建者**" 列表中的对象才能添加到该类别下的聊天室中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

