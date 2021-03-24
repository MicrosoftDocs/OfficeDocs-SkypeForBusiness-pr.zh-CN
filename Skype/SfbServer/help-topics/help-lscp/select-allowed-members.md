---
title: 选择允许的成员
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 正确使用类别可更轻松地创建和管理持久聊天室。 持久聊天管理员可以为每个类别定义 AllowedMembers 和 Creators，还可以定义将应用于在类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员使用控制面板或 cmdlet 创建和管理Windows PowerShell类别。
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107988"
---
# <a name="select-allowed-members"></a><span data-ttu-id="8dcc5-105">选择允许的成员</span><span class="sxs-lookup"><span data-stu-id="8dcc5-105">Select Allowed Members</span></span>

<span data-ttu-id="8dcc5-106">正确使用类别可更轻松地创建和管理持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="8dcc5-107">持久聊天管理员可以为每个类别定义 **AllowedMembers** 和 **Creators，** 还可以定义将应用于在类别中创建的所有聊天室的默认聊天室设置和行为。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="8dcc5-108">持久聊天管理员使用控制面板或 cmdlet 创建和管理Windows PowerShell类别。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="8dcc5-109">标识为类别创建者的用户、组织单位 (OU) 和用户组是唯一允许在该类别中创建聊天室的个人和组。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="8dcc5-110">创建类别后，他们可以从类别的 **AllowedMembers** 列表中选择用户、US 和用户组作为聊天室管理员和成员来管理和参与聊天室。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="8dcc5-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="8dcc5-111">Tasks that you can perform</span></span>

<span data-ttu-id="8dcc5-112">您可以在“选择允许的成员”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8dcc5-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="8dcc5-113">配置类别</span><span class="sxs-lookup"><span data-stu-id="8dcc5-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="8dcc5-114">新增的群聊服务器功能</span><span class="sxs-lookup"><span data-stu-id="8dcc5-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="8dcc5-115">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅[管理 Skype for Business Server 2015。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="8dcc5-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="8dcc5-116">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="8dcc5-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="8dcc5-117">在"成员身份"的"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于类别的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="8dcc5-118">类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。</span><span class="sxs-lookup"><span data-stu-id="8dcc5-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="8dcc5-119">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的[Overview of Persistent Chat Server。](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="8dcc5-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="8dcc5-120">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中的[Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)和操作文档中的[Managing Lync Server 2013， Persistent Chat Server。](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="8dcc5-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dcc5-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dcc5-121">See also</span></span>

[<span data-ttu-id="8dcc5-122">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="8dcc5-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)