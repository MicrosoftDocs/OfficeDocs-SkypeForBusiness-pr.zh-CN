---
title: 选择被拒绝的成员
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 持久聊天管理员可以创建和管理聊天室类别。 作为创建和管理聊天室类别的一部分，持久聊天管理员可以配置主体 (Active Directory 域服务组/容器/用户) ，这些主体有权访问为特定类别的聊天室的成员/创建者。 持久聊天管理员还可以将 DeniedMembers 添加到类别，这些类别将成为允许列表的显式排除项。 DeniedMembers 会覆盖 AllowedMembers 中的功能。
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814572"
---
# <a name="select-denied-members"></a><span data-ttu-id="62729-106">选择被拒绝的成员</span><span class="sxs-lookup"><span data-stu-id="62729-106">Select Denied Members</span></span>

<span data-ttu-id="62729-107">持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="62729-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="62729-108">作为创建和管理聊天室类别的一部分，持久聊天管理员可以配置主体 (Active Directory 域服务组/容器/用户) ，这些主体有权访问为特定类别的聊天室的成员/创建者。</span><span class="sxs-lookup"><span data-stu-id="62729-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="62729-109">持久聊天管理员还可以将 DeniedMembers 添加到类别，这些类别将成为允许列表的显式排除项。</span><span class="sxs-lookup"><span data-stu-id="62729-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="62729-110">DeniedMembers 会覆盖 AllowedMembers 中的功能。</span><span class="sxs-lookup"><span data-stu-id="62729-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="62729-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="62729-111">Tasks that you can perform</span></span>

<span data-ttu-id="62729-112">您可以在“选择被拒绝的成员”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="62729-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="62729-113">配置类别</span><span class="sxs-lookup"><span data-stu-id="62729-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="62729-114">新增的群聊服务器功能</span><span class="sxs-lookup"><span data-stu-id="62729-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="62729-115">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="62729-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="62729-116">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="62729-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="62729-117">在 **"成员身份**"中的"拒绝的成员"部分，添加或删除与聊天室中被拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="62729-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="62729-118">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的 ["持久聊天服务器](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 概述"。</span><span class="sxs-lookup"><span data-stu-id="62729-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="62729-119">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中[](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)的"配置持久聊天服务器"和操作文档中的"管理[Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)持久聊天服务器"。</span><span class="sxs-lookup"><span data-stu-id="62729-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="62729-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62729-120">See also</span></span>

[<span data-ttu-id="62729-121">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="62729-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
