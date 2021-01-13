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
description: 正确使用类别可更轻松地创建和管理持久聊天室。 持久聊天管理员可以为每个类别定义 AllowedMembers 和 Creators，还可以定义将应用于类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员使用控制面板或 cmdlet 创建和管理Windows PowerShell类别。
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829132"
---
# <a name="select-allowed-members"></a><span data-ttu-id="c0617-105">选择允许的成员</span><span class="sxs-lookup"><span data-stu-id="c0617-105">Select Allowed Members</span></span>

<span data-ttu-id="c0617-106">正确使用类别可更轻松地创建和管理持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="c0617-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="c0617-107">持久聊天管理员可以为每个类别定义 **AllowedMembers** 和 **Creators，** 还可以定义将应用于类别中创建的所有聊天室的默认聊天室设置和行为。</span><span class="sxs-lookup"><span data-stu-id="c0617-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="c0617-108">持久聊天管理员使用控制面板或 cmdlet 创建和管理Windows PowerShell类别。</span><span class="sxs-lookup"><span data-stu-id="c0617-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="c0617-109">标识为类别创建者的用户、组织单位 (OU) 和用户组是唯一允许在该类别中创建聊天室的个人和组。</span><span class="sxs-lookup"><span data-stu-id="c0617-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="c0617-110">创建类别后，他们可以从类别的 **AllowedMembers** 列表中选择用户、US 和用户组作为聊天室管理员和成员来管理和参与聊天室。</span><span class="sxs-lookup"><span data-stu-id="c0617-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="c0617-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="c0617-111">Tasks that you can perform</span></span>

<span data-ttu-id="c0617-112">您可以在“选择允许的成员”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c0617-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="c0617-113">配置类别</span><span class="sxs-lookup"><span data-stu-id="c0617-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="c0617-114">新增的群聊服务器功能</span><span class="sxs-lookup"><span data-stu-id="c0617-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="c0617-115">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="c0617-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="c0617-116">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="c0617-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="c0617-117">在 **"** 成员身份"中，在"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于该类别的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="c0617-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="c0617-118">类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。</span><span class="sxs-lookup"><span data-stu-id="c0617-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="c0617-119">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的 ["持久聊天服务器](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 概述"。</span><span class="sxs-lookup"><span data-stu-id="c0617-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c0617-120">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中[](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)的"配置持久聊天服务器"和操作文档中的"管理[Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)持久聊天服务器"。</span><span class="sxs-lookup"><span data-stu-id="c0617-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0617-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0617-121">See also</span></span>

[<span data-ttu-id="c0617-122">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="c0617-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
