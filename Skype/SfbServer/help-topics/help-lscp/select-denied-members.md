---
title: 选择被拒绝的成员
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 持久聊天管理员可以创建和管理聊天室类别。 在创建和管理聊天室类别的过程中, 持久聊天管理员可以配置主体 (Active Directory 域服务组/容器/用户), 该主体具有特定类别的聊天室成员/创建者的访问权限。 持久聊天管理员还可以将 DeniedMembers 添加到类别中, 并将它们显式排除在 "允许列表" 中。 DeniedMembers 替代 AllowedMembers 中的内容。
ms.openlocfilehash: bbf54bfb05a2c3a54c9515d77ae6fb93b22a62ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294078"
---
# <a name="select-denied-members"></a><span data-ttu-id="1f14e-106">选择被拒绝的成员</span><span class="sxs-lookup"><span data-stu-id="1f14e-106">Select Denied Members</span></span>

<span data-ttu-id="1f14e-107">持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="1f14e-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="1f14e-108">在创建和管理聊天室类别的过程中, 持久聊天管理员可以配置主体 (Active Directory 域服务组/容器/用户), 该主体具有特定类别的聊天室成员/创建者的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1f14e-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="1f14e-109">持久聊天管理员还可以将 DeniedMembers 添加到类别中, 并将它们显式排除在 "允许列表" 中。</span><span class="sxs-lookup"><span data-stu-id="1f14e-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="1f14e-110">DeniedMembers 替代 AllowedMembers 中的内容。</span><span class="sxs-lookup"><span data-stu-id="1f14e-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="1f14e-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="1f14e-111">Tasks that you can perform</span></span>

<span data-ttu-id="1f14e-112">您可以在“**选择被拒绝的成员**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1f14e-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="1f14e-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="1f14e-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="1f14e-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="1f14e-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="1f14e-115">有关可通过使用 Skype for Business 服务器控制面板执行的不同过程的详细信息, 请参阅[管理 skype for Business server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="1f14e-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="1f14e-116">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="1f14e-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="1f14e-117">在\*\*\*\*"**拒绝成员**" 部分中, 在 "拒绝的成员" 部分中, 添加或删除与从聊天室拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="1f14e-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="1f14e-118">有关持久聊天服务器功能和功能的详细信息, 请参阅规划文档中[持久聊天服务器概述](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1f14e-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="1f14e-119">有关使用持久聊天服务器配置的详细信息, 请参阅在部署文档中[配置持久聊天服务器](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)和在操作文档中[管理 Lync Server 2013 持久聊天服务器](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1f14e-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f14e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f14e-120">See also</span></span>

[<span data-ttu-id="1f14e-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="1f14e-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
