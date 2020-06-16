---
title: 了解持久聊天成员身份
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400866812ab2d5efb12960dc3c2f37c2fcb8eb45
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>了解持久聊天成员身份

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

用户对持久聊天室的访问权限由成员资格管理;用户必须是聊天室的成员才能发布和阅读邮件。 只允许与聊天室有指定的附属关系的**演示者**使用**在大会堂聊天室发布消息**。 大会堂是其中一种聊天室类型（另一种是**普通聊天室**），在这种聊天室中，只有演示者能发布消息，但任何人都能阅读消息。

此外，持久聊天室在类别规则下运行。 有关类别的详细信息，请参阅[在 Lync Server 2013 中管理类别、聊天室和外接程序](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主题后面部分的 "类别作用域的工作原理" 和 "会议室类别策略" 部分。

持久聊天管理员可以创建和管理聊天室类别。 在创建和管理聊天室类别的过程中，持久聊天管理员可以配置有权访问特定类别的聊天室的成员或访问者的主体（Active Directory 域服务组、容器和用户）。

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory 域服务和持久聊天

持久聊天服务器依赖于内部持久聊天用户池的 Active Directory。 安装持久聊天（客户端）后，可以将用户和用户组的域添加到聊天室类别中。 然后，可以将这些用户和组添加到您的聊天室类别的成员身份中。

<div>


> [!IMPORTANT]  
> 您必须确保要对其持久聊天室进行更改的用户没有重复的名称。 如果存在重复的用户名，请将它们更改为不同的名称以解除针对用户进行这些更改的限制。 如果用户在 Active Directory 中具有重复的名称，并尝试在其聊天室中进行更改，则会出现一条错误消息，提示用户与管理员联系以进行解决。



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>类别作用域的工作机制

类别指定在该类别中的持久聊天室的成员资格列表中可以是其成员的所有用户和组，具体取决于其**AllowedMembers**属性。 例如，如果将类别的**AllowedMembers**设置为 contoso.com，则可以将*contoso*中的任何组或用户添加为该类别中的聊天室的成员。 如果将某个类别上的 **AllowedMembers** 设置为 *Sales*，则只能将此通讯组列表中的组和用户添加为该类别中的聊天室的成员。 同样，利用 **Creators** 属性，您可以控制可在该类别中创建聊天室的人员。 创建聊天室后，可将 **AllowedMembers** 组中的任何人指定为聊天室中正在进行的管理操作（例如，成员身份更改和审批）的 **Manager**。

为类别定义 **AllowedMembers** 和 **Creators** 有以下好处：

  - All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.

  - A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.

</div>

<div>

## <a name="room-category-strategies"></a>聊天室类别策略

类别的**AllowedMembers**必须包括将在此类别中使用任何持久聊天室的所有用户。 根据您保护业务数据和确保适当的访问级别的要求，您可能希望定义一个或多个类别以指定可在聊天室中进行搜索和加入聊天室的人员。 如果希望只允许一组特定的用户（中央支持人员或仅全职员工）创建聊天室，则可以设置类别的 **Creators** 的作用域来满足该要求。

Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.

<div>


> [!NOTE]  
> 在 Lync Server 2013 的持久聊天服务器中，我们不支持对联合用户的访问。 如果来自以前版本的持久聊天服务器的联盟用户的聊天，将迁移这些聊天。 将联盟用户添加为已禁用的主体。



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>将成员缩小至用户组

当您向类别添加域时，组对象隶属于该域的用户组可供您使用，以将其指定为该类别中的聊天室的成员。

我们建议您使用 Active Directory 容器（如域和组织单位）定义类别的**AllowedMembers**和**创建者**的常规规则。 您可以将任何域中的对象添加到 **AllowedMembers** 或 **Creators** 列表。 只有 **AllowedMembers** 或 **Creators** 列表中的对象能添加到该类别下的聊天室。

</div>

</div>

<span> </span>

</div>

</div>

</div>

