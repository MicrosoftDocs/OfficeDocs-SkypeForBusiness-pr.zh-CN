---
title: 选择被拒绝的成员
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 持久聊天管理员可以创建和管理聊天室类别。 作为创建和管理聊天室类别的一部分，a Persistent Chat Administrator 可配置有权在特定类别的聊天室的成员/创建者的主体 （Active Directory 域服务组/容器/用户）。 A Persistent Chat Administrator 还可以将 DeniedMembers 添加到类别和这些成为显式排除到允许列表。 DeniedMembers 重写 AllowedMembers 中是什么。
ms.openlocfilehash: f8fc7179df8facb98408e4506cf681cbefb97c62
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="select-denied-members"></a><span data-ttu-id="cb4f1-106">选择被拒绝的成员</span><span class="sxs-lookup"><span data-stu-id="cb4f1-106">Select Denied Members</span></span>
 
<span data-ttu-id="cb4f1-107">持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="cb4f1-108">作为创建和管理聊天室类别的一部分，a Persistent Chat Administrator 可配置有权在特定类别的聊天室的成员/创建者的主体 （Active Directory 域服务组/容器/用户）。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="cb4f1-109">A Persistent Chat Administrator 还可以将 DeniedMembers 添加到类别和这些成为显式排除到允许列表。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="cb4f1-110">DeniedMembers 重写 AllowedMembers 中是什么。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-110">DeniedMembers override what's in AllowedMembers.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="cb4f1-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="cb4f1-111">Tasks that you can perform</span></span>

<span data-ttu-id="cb4f1-112">您可以在“**选择被拒绝的成员**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="cb4f1-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>
  
- [<span data-ttu-id="cb4f1-113">配置类别</span><span class="sxs-lookup"><span data-stu-id="cb4f1-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="cb4f1-114">持久聊天服务器的新增功能</span><span class="sxs-lookup"><span data-stu-id="cb4f1-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="cb4f1-115">有关您可以使用适用于业务 Server Control Panel Skype 执行的各种过程的详细信息，请参阅[管理的 Skype 的业务服务器 2015年](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="cb4f1-116">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="cb4f1-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="cb4f1-117">中的**成员资格**，**拒绝成员**部分中添加或删除用户和其他与聊天室拒绝的成员关联的 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
  
### 

<span data-ttu-id="cb4f1-118">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的[持久聊天服务器的概述](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="cb4f1-119">有关使用持久聊天服务器配置的详细信息，请参阅[Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)中的部署文档和[Managing Lync Server 2013，Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)操作文档中。</span><span class="sxs-lookup"><span data-stu-id="cb4f1-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb4f1-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb4f1-120">See also</span></span>

#### 

[<span data-ttu-id="cb4f1-121">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="cb4f1-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

