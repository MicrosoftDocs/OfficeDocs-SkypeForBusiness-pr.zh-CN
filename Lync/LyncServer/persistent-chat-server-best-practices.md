---
title: 持久聊天服务器最佳实践
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fceea7401a6d5442738a0cc64e9a2bafbfd83827
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500139"
---
# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="236a2-102">持久聊天服务器最佳实践</span><span class="sxs-lookup"><span data-stu-id="236a2-102">Persistent Chat Server best practices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="236a2-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="236a2-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="236a2-104">创建类别和持久聊天室并设计范围和成员资格时，以下提示可帮助您进行规划：</span><span class="sxs-lookup"><span data-stu-id="236a2-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="236a2-105">如果贵公司不需要符合道德的墙，请不要缩小类别树中的范围。</span><span class="sxs-lookup"><span data-stu-id="236a2-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="236a2-106">将所有用户放在一个类别的范围内，并在该类别中创建所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="236a2-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="236a2-107">随后，仅使用成员身份列表来授予或限制对每个聊天室的访问权限。</span><span class="sxs-lookup"><span data-stu-id="236a2-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="236a2-108">在大多数情况下，应使用户能够创建新的聊天室，以便可以随时启动有关新主题的讨论。</span><span class="sxs-lookup"><span data-stu-id="236a2-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="236a2-109">若要执行此操作， **创建者** 列表与 **AllowedMembers** 列表相同。</span><span class="sxs-lookup"><span data-stu-id="236a2-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="236a2-110">但是，如果您希望仅允许中央支持团队或指定的用户创建聊天室，则将创建 **者** 列表作为相应的子集。</span><span class="sxs-lookup"><span data-stu-id="236a2-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="236a2-111">为每个聊天室提供一个完整的名称和说明摘要，描述它在组织中的适合位置。</span><span class="sxs-lookup"><span data-stu-id="236a2-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="236a2-112">由于用户在使用聊天室时看不到类别名称，因此您不能依赖类别名称来帮助用户确定聊天室的预期讨论论坛。</span><span class="sxs-lookup"><span data-stu-id="236a2-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="236a2-113">如果您有特定的命名约定或其他访问控制或验证实现，则您可能需要具有自定义会议室创建工作流。</span><span class="sxs-lookup"><span data-stu-id="236a2-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="236a2-114">通过持久聊天配置，您可以自定义 **RoomManagementUrl** 到您承载的内容。</span><span class="sxs-lookup"><span data-stu-id="236a2-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="236a2-115">例如，当用户单击其 Lync 客户端中 **的 "创建聊天室** " 时，可以将它们重定向到您的自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="236a2-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="236a2-116">通过将其他业务数据引入聊天室，创建各种外接程序，以帮助增强聊天室的体验。</span><span class="sxs-lookup"><span data-stu-id="236a2-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="236a2-117">管理员必须注册他们希望在系统中允许的外接程序。</span><span class="sxs-lookup"><span data-stu-id="236a2-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="236a2-118">聊天室管理员和创建者可以从允许的加载项列表中选择与各自的聊天室最相关的加载项列表。</span><span class="sxs-lookup"><span data-stu-id="236a2-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="236a2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="236a2-119">See Also</span></span>


[<span data-ttu-id="236a2-120">在 Lync Server 2013 中管理类别、聊天室和外接程序</span><span class="sxs-lookup"><span data-stu-id="236a2-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

