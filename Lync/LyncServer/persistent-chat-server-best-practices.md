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

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="409fd-102">持久聊天服务器最佳做法</span><span class="sxs-lookup"><span data-stu-id="409fd-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="409fd-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="409fd-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="409fd-104">当你创建类别和持久聊天室并设计你的范围和成员身份时, 以下提示可帮助你进行规划:</span><span class="sxs-lookup"><span data-stu-id="409fd-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="409fd-105">如果您的公司不需要符合道德的墙, 请不要缩小类别树中的范围。</span><span class="sxs-lookup"><span data-stu-id="409fd-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="409fd-106">将所有用户放在一个类别的范围内, 并创建该类别中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="409fd-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="409fd-107">随后, 仅使用成员身份列表授予或限制对每个聊天室的访问权限。</span><span class="sxs-lookup"><span data-stu-id="409fd-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="409fd-108">在大多数情况下, 你应使用户能够创建新的聊天室, 以便可以随时开始讨论新主题。</span><span class="sxs-lookup"><span data-stu-id="409fd-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="409fd-109">通过使**创建者**列表与**AllowedMembers**列表相同来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="409fd-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="409fd-110">但是, 如果你希望仅允许中央支持团队或指定用户创建聊天室, 则将创建**者**列表作为相应的子集。</span><span class="sxs-lookup"><span data-stu-id="409fd-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="409fd-111">为每个聊天室提供一个完整的名称和说明摘要, 描述它与你的组织相匹配的位置。</span><span class="sxs-lookup"><span data-stu-id="409fd-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="409fd-112">由于用户使用聊天室时看不到类别名称, 因此不能依赖类别名称来帮助用户确定聊天室的预期讨论论坛。</span><span class="sxs-lookup"><span data-stu-id="409fd-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="409fd-113">如果你有某些命名约定或其他访问控制或验证实现, 你可能需要具有自定义聊天室创建工作流。</span><span class="sxs-lookup"><span data-stu-id="409fd-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="409fd-114">持久聊天配置使你能够将**RoomManagementUrl**自定义到你托管的内容。</span><span class="sxs-lookup"><span data-stu-id="409fd-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="409fd-115">例如, 当用户在其 Lync 客户端中单击 "**创建聊天室**" 时, 可以将其重定向到你的自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="409fd-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="409fd-116">通过将其他业务数据引入聊天室, 创建各种可帮助增强聊天室体验的加载项。</span><span class="sxs-lookup"><span data-stu-id="409fd-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="409fd-117">管理员必须在系统中注册要允许的加载项。</span><span class="sxs-lookup"><span data-stu-id="409fd-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="409fd-118">聊天室管理员和创建者可以从允许的加载项列表中选择与各自的聊天室最相关的加载项。</span><span class="sxs-lookup"><span data-stu-id="409fd-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="409fd-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="409fd-119">See Also</span></span>


[<span data-ttu-id="409fd-120">在 Lync Server 2013 中管理类别、聊天室和加载项</span><span class="sxs-lookup"><span data-stu-id="409fd-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

