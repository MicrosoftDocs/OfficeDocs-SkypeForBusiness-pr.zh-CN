---
title: 添加持久聊天 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 配置将为持久聊天服务器或持久聊天服务器池提供数据库的 SQL Server 存储。
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685055"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="3c632-103">添加持久聊天 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="3c632-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="3c632-104">配置将为持久聊天服务器或持久聊天服务器池提供数据库的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="3c632-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="3c632-105">**SQL server 应用商店**：选择现有的 SQL server 和（可选）持久聊天的实例。</span><span class="sxs-lookup"><span data-stu-id="3c632-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="3c632-106">单击 "**新建**" 以定义新的 SQL Server 和持久聊天数据的新实例（可选）。</span><span class="sxs-lookup"><span data-stu-id="3c632-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="3c632-107">选中 "**启用 Sql server 应用商店镜像**" 复选框，以配置 sql server 数据库和可为持久聊天数据提供镜像数据库的可选实例。</span><span class="sxs-lookup"><span data-stu-id="3c632-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="3c632-108">从列表中选择 "**镜像 sql** server" 将 sql server 和可选实例用作持久聊天 sql SERVER 的 sql server 镜像。</span><span class="sxs-lookup"><span data-stu-id="3c632-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="3c632-109">单击 "**新建**" 以定义新的 SQL Server 和持久聊天 SQL server 镜像的新实例（可选）。</span><span class="sxs-lookup"><span data-stu-id="3c632-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="3c632-110">从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。</span><span class="sxs-lookup"><span data-stu-id="3c632-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="3c632-111">见证服务器不会镜像或承载持久聊天服务器的数据，但可确保镜像配置中的每个 SQL Server 在任何时候都是活动 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="3c632-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="3c632-112">单击 "**新建**" 以定义新的 SQL server 见证（可选择一个持久聊天 sql server 镜像见证的实例）。</span><span class="sxs-lookup"><span data-stu-id="3c632-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="3c632-113">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="3c632-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="3c632-114">输入此池的 SQL Server 应用商店配置的选项后，单击 "**下一步**"，然后继续使用持久聊天服务器池定义。</span><span class="sxs-lookup"><span data-stu-id="3c632-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="3c632-115">单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。</span><span class="sxs-lookup"><span data-stu-id="3c632-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="3c632-116">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="3c632-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c632-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c632-117">See also</span></span>

[<span data-ttu-id="3c632-118">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="3c632-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="3c632-119">将持久聊天服务器添加到 Skype for business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="3c632-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="3c632-120">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="3c632-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="3c632-121">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c632-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="3c632-122">Skype for Business Server 2015 的拓扑基础知识</span><span class="sxs-lookup"><span data-stu-id="3c632-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="3c632-123">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="3c632-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
