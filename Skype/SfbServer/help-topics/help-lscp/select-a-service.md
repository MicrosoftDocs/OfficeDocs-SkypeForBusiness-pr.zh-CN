---
title: 选择一个服务
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
- ms.lync.lscp.SelectPool
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6086162-8a41-4e75-afa3-7d1889ffdc90
description: 使用"选择服务"对话框查找环境中可用的服务。 要使用现有服务，请单击列表中的某个服务，然后单击“确定”。
ms.openlocfilehash: 06ee0217a8a495a881c9925c57e33311e4944607
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108038"
---
# <a name="select-a-service"></a><span data-ttu-id="e38d1-104">选择一个服务</span><span class="sxs-lookup"><span data-stu-id="e38d1-104">Select a Service</span></span>

<span data-ttu-id="e38d1-105">使用 **"选择服务** "对话框查找环境中可用的服务。</span><span class="sxs-lookup"><span data-stu-id="e38d1-105">Use the **Select a Service** dialog box to find services available in your environment.</span></span> <span data-ttu-id="e38d1-106">要使用现有服务，请单击列表中的某个服务，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="e38d1-106">To use an existing service, click a service in the list and then click **OK**.</span></span>

<span data-ttu-id="e38d1-107">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅[管理 Skype for Business Server 2015。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="e38d1-107">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e38d1-108">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="e38d1-108">Tasks you can perform</span></span>

<span data-ttu-id="e38d1-109">您可以在“选择服务”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e38d1-109">You can perform the following tasks on the **Select a Service** page:</span></span>

- [<span data-ttu-id="e38d1-110">配置类别</span><span class="sxs-lookup"><span data-stu-id="e38d1-110">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="e38d1-111">为房间配置外接程序</span><span class="sxs-lookup"><span data-stu-id="e38d1-111">Configure Add-ins for Rooms</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-add-ins-for-rooms)

- [<span data-ttu-id="e38d1-112">为持久聊天服务器池全局配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="e38d1-112">Configure Persistent Chat Server Options Globally or for Persistent Chat Server Pool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool)

<span data-ttu-id="e38d1-113">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅[管理 Skype for Business Server 2015。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="e38d1-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="e38d1-114">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="e38d1-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="e38d1-115">在 **"选择服务**"中，选择与需要创建类别的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="e38d1-115">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="e38d1-116">该服务是持久聊天服务器池， (客户端) 该类别所属的池。</span><span class="sxs-lookup"><span data-stu-id="e38d1-116">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="e38d1-117">类别只能属于一个持久聊天服务器池，并且不能移动到另一个池，也不能与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="e38d1-117">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="e38d1-118">配置聊天室外接程序</span><span class="sxs-lookup"><span data-stu-id="e38d1-118">To configure add-ins for chat rooms</span></span>

<span data-ttu-id="e38d1-119">在 **"选择服务**"中，选择与需要创建外接程序的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="e38d1-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="e38d1-120">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="e38d1-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="e38d1-121">为特定持久聊天服务器池配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="e38d1-121">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="e38d1-122">在 **"选择服务**"中，选择要配置的与持久聊天服务器池关联的服务。</span><span class="sxs-lookup"><span data-stu-id="e38d1-122">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

<span data-ttu-id="e38d1-123">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的[Overview of Persistent Chat Server。](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="e38d1-123">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="e38d1-124">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中的[Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)和操作文档中的[Managing Lync Server 2013， Persistent Chat Server。](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server)</span><span class="sxs-lookup"><span data-stu-id="e38d1-124">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>