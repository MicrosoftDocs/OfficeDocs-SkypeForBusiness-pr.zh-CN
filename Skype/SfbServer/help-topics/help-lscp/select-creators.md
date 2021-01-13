---
title: 选择创建者
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 正确使用类别可更轻松地创建和管理持久聊天室。 持久聊天管理员可以为每个类别定义 AllowedMembers 和 Creators，还可以定义将应用于该类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员使用 Skype for Business Server 控制面板或 Windows PowerShell cmdlet 创建和管理类别。
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821952"
---
# <a name="select-creators"></a><span data-ttu-id="c2bda-105">选择创建者</span><span class="sxs-lookup"><span data-stu-id="c2bda-105">Select Creators</span></span>

<span data-ttu-id="c2bda-106">正确使用类别可更轻松地创建和管理持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="c2bda-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="c2bda-107">持久聊天管理员可以为每个类别定义 **AllowedMembers** 和 **Creators，** 还可以定义将应用于该类别中创建的所有聊天室的默认聊天室设置和行为。</span><span class="sxs-lookup"><span data-stu-id="c2bda-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="c2bda-108">持久聊天管理员使用 Skype for Business Server 控制面板或 Windows PowerShell cmdlet 创建和管理类别。</span><span class="sxs-lookup"><span data-stu-id="c2bda-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="c2bda-109">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="c2bda-109">Tasks that you can perform</span></span>

<span data-ttu-id="c2bda-110">您可以在“选择创建者”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c2bda-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="c2bda-111">配置类别</span><span class="sxs-lookup"><span data-stu-id="c2bda-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="c2bda-112">新增的群聊服务器功能</span><span class="sxs-lookup"><span data-stu-id="c2bda-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="c2bda-113">有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="c2bda-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="c2bda-114">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="c2bda-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="c2bda-115">在 **"成员身份**"中的" **创建者** "部分，添加或删除与类别的创建者关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="c2bda-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="c2bda-116">创建者是有权创建聊天室并指定聊天室管理员和成员的用户。</span><span class="sxs-lookup"><span data-stu-id="c2bda-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="c2bda-117">有关持久聊天服务器特性和功能的详细信息，请参阅规划文档中的 ["持久聊天服务器](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 概述"。</span><span class="sxs-lookup"><span data-stu-id="c2bda-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c2bda-118">有关使用持久聊天服务器配置的详细信息，请参阅部署文档中[](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)的"配置持久聊天服务器"和操作文档中的"管理[Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)持久聊天服务器"。</span><span class="sxs-lookup"><span data-stu-id="c2bda-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2bda-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2bda-119">See also</span></span>

[<span data-ttu-id="c2bda-120">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="c2bda-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="c2bda-121">使用类别管理持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="c2bda-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="c2bda-122">将聊天室从一个类别移动到另一个类型</span><span class="sxs-lookup"><span data-stu-id="c2bda-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="c2bda-123">创建或编辑新聊天室</span><span class="sxs-lookup"><span data-stu-id="c2bda-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
