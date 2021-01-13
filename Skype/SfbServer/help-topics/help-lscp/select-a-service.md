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
ms.openlocfilehash: c1f0f1c3f5add413f6f2f801bb54c84179b46f91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829192"
---
# <a name="select-a-service"></a><span data-ttu-id="9fdf7-104">选择一个服务</span><span class="sxs-lookup"><span data-stu-id="9fdf7-104">Select a Service</span></span>

<span data-ttu-id="9fdf7-105">使用 **"选择服务** "对话框查找环境中可用的服务。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-105">Use the **Select a Service** dialog box to find services available in your environment.</span></span> <span data-ttu-id="9fdf7-106">要使用现有服务，请单击列表中的某个服务，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-106">To use an existing service, click a service in the list and then click **OK**.</span></span>

<span data-ttu-id="9fdf7-107">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="9fdf7-107">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9fdf7-108">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="9fdf7-108">Tasks you can perform</span></span>

<span data-ttu-id="9fdf7-109">您可以在“选择服务”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9fdf7-109">You can perform the following tasks on the **Select a Service** page:</span></span>

- [<span data-ttu-id="9fdf7-110">配置类别</span><span class="sxs-lookup"><span data-stu-id="9fdf7-110">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="9fdf7-111">为房间配置外接程序</span><span class="sxs-lookup"><span data-stu-id="9fdf7-111">Configure Add-ins for Rooms</span></span>](https://technet.microsoft.com/library/4eeaf19e-8369-4f6f-af65-a283cf7daa1c.aspx)

- [<span data-ttu-id="9fdf7-112">为持久聊天服务器池全局配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="9fdf7-112">Configure Persistent Chat Server Options Globally or for Persistent Chat Server Pool</span></span>](https://technet.microsoft.com/library/1e8d5245-cd58-4aad-9a1c-35b24189bc40.aspx)

<span data-ttu-id="9fdf7-113">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="9fdf7-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="9fdf7-114">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="9fdf7-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="9fdf7-115">在 **"选择服务**"中，选择与需要创建类别的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-115">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="9fdf7-116">该服务是持久聊天服务器池，持久聊天 (客户端) 该类别所属的池。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-116">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="9fdf7-117">类别只能属于一个持久聊天服务器池，并且不能移动到另一个池，也不能与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-117">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="9fdf7-118">配置聊天室外接程序</span><span class="sxs-lookup"><span data-stu-id="9fdf7-118">To configure add-ins for chat rooms</span></span>

<span data-ttu-id="9fdf7-119">在 **"选择服务**"中，选择与需要创建外接程序的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="9fdf7-120">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="9fdf7-121">为特定持久聊天服务器池配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="9fdf7-121">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="9fdf7-122">在 **"选择服务**"中，选择与要配置的持久聊天服务器池关联的服务。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-122">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

<span data-ttu-id="9fdf7-123">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的 ["持久聊天服务器](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 概述"。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-123">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9fdf7-124">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中[](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)的"配置持久聊天服务器"和操作文档中的"管理[Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)持久聊天服务器"。</span><span class="sxs-lookup"><span data-stu-id="9fdf7-124">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

