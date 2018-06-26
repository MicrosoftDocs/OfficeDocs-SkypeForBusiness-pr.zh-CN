---
title: 选择允许的成员
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 创建和管理的持久聊天聊天室类别的正确使用与要容易得多。 持久聊天管理员可以为每个类别定义 AllowedMembers 和 Creators 和还可以定义默认聊天室设置和将应用于所有聊天室的类别中创建的行为。 持久聊天管理员创建和使用控制面板或 Windows PowerShell cmdlet 管理类别。
ms.openlocfilehash: c29163a88394fd9c3653e9bbbdae8c9f744f610e
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "20045608"
---
# <a name="select-allowed-members"></a><span data-ttu-id="09476-105">选择允许的成员</span><span class="sxs-lookup"><span data-stu-id="09476-105">Select Allowed Members</span></span>
 
<span data-ttu-id="09476-106">创建和管理的持久聊天聊天室类别的正确使用与要容易得多。</span><span class="sxs-lookup"><span data-stu-id="09476-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="09476-107">持久聊天管理员可以为每个类别定义**AllowedMembers**和**Creators**和还可以定义默认聊天室设置和将应用于所有聊天室的类别中创建的行为。</span><span class="sxs-lookup"><span data-stu-id="09476-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="09476-108">持久聊天管理员创建和使用控制面板或 Windows PowerShell cmdlet 管理类别。</span><span class="sxs-lookup"><span data-stu-id="09476-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
<span data-ttu-id="09476-109">标识为类别创建者的用户、组织单位 (OU) 和用户组是仅有的被允许在类别中创建聊天室的个人和组。</span><span class="sxs-lookup"><span data-stu-id="09476-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="09476-110">在创建类别后，他们可以选择用户、 Ou 和用户组从该类别的**AllowedMembers**列表为聊天室管理员和成员来管理和加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="09476-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="09476-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="09476-111">Tasks that you can perform</span></span>

<span data-ttu-id="09476-112">您可以在“**选择允许的成员**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="09476-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>
  
- [<span data-ttu-id="09476-113">配置类别</span><span class="sxs-lookup"><span data-stu-id="09476-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="09476-114">持久聊天服务器的新增功能</span><span class="sxs-lookup"><span data-stu-id="09476-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
 
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="09476-115">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="09476-115">To configure categories for chat rooms</span></span>

<span data-ttu-id="09476-116">在**成员资格**，在**允许成员**部分中，添加或删除用户和其他 Active Directory 域服务主体 （用户、 通讯组、 组织单位，等） 允许添加为聊天室的成员属于类别。</span><span class="sxs-lookup"><span data-stu-id="09476-116">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="09476-117">类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。</span><span class="sxs-lookup"><span data-stu-id="09476-117">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
  
### 

<span data-ttu-id="09476-118">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的[持久聊天服务器的概述](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09476-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="09476-119">有关使用持久聊天服务器配置的详细信息，请参阅[Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)中的部署文档和[Managing Lync Server 2013，Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)操作文档中。</span><span class="sxs-lookup"><span data-stu-id="09476-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09476-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09476-120">See also</span></span>

[<span data-ttu-id="09476-121">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="09476-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)