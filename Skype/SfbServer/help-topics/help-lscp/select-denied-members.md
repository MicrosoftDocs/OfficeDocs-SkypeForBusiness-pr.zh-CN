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
description: 持久聊天管理员可以创建和管理聊天室类别。 在创建和管理聊天室类别时，持久聊天管理员可以配置主体 (Active Directory 域服务组/容器/用户) 这些主体有权访问特定类别的聊天室的成员/创建者。 持久聊天管理员还可以将 DeniedMembers 添加到类别，这些成员将成为允许列表的显式排除项。 DeniedMembers 会覆盖 AllowedMembers 中的功能。
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107958"
---
# <a name="select-denied-members"></a><span data-ttu-id="0bc2a-106">选择被拒绝的成员</span><span class="sxs-lookup"><span data-stu-id="0bc2a-106">Select Denied Members</span></span>

<span data-ttu-id="0bc2a-107">持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="0bc2a-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="0bc2a-108">在创建和管理聊天室类别时，持久聊天管理员可以配置主体 (Active Directory 域服务组/容器/用户) 这些主体有权访问特定类别的聊天室的成员/创建者。</span><span class="sxs-lookup"><span data-stu-id="0bc2a-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="0bc2a-109">持久聊天管理员还可以将 DeniedMembers 添加到类别，这些成员将成为允许列表的显式排除项。</span><span class="sxs-lookup"><span data-stu-id="0bc2a-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="0bc2a-110">DeniedMembers 会覆盖 AllowedMembers 中的功能。</span><span class="sxs-lookup"><span data-stu-id="0bc2a-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0bc2a-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="0bc2a-111">Tasks that you can perform</span></span>

<span data-ttu-id="0bc2a-112">您可以在“选择被拒绝的成员”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0bc2a-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="0bc2a-113">配置类别</span><span class="sxs-lookup"><span data-stu-id="0bc2a-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="0bc2a-114">新增的群聊服务器功能</span><span class="sxs-lookup"><span data-stu-id="0bc2a-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="0bc2a-115">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅[管理 Skype for Business Server 2015。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="0bc2a-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0bc2a-116">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="0bc2a-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="0bc2a-117">在 **"成员身份**"中的" **拒绝** 的成员"部分，添加或删除与聊天室中被拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="0bc2a-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="0bc2a-118">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的[Overview of Persistent Chat Server。](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="0bc2a-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="0bc2a-119">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中的[Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)和操作文档中的[Managing Lync Server 2013， Persistent Chat Server。](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="0bc2a-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bc2a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bc2a-120">See also</span></span>

[<span data-ttu-id="0bc2a-121">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="0bc2a-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)