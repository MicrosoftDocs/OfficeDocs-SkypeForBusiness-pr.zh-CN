---
title: 添加持久聊天合规性 SQL Server 存储
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 配置 SQL Server 存储将持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性。
ms.openlocfilehash: 467d90e88b50bc4ea5505c322d5be5eab3a7d719
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="d40a6-103">添加持久聊天合规性 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="d40a6-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="d40a6-104">配置 SQL Server 存储将持久聊天服务器或持久聊天服务器合规性功能提供数据库的合规性。</span><span class="sxs-lookup"><span data-stu-id="d40a6-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="d40a6-105">**SQL Server 存储**： 选择现有的 SQL Server 和可选实例的持久聊天。</span><span class="sxs-lookup"><span data-stu-id="d40a6-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="d40a6-106">单击**新建**以定义一个新的 SQL Server 和可选的持久聊天合规性数据的新实例。</span><span class="sxs-lookup"><span data-stu-id="d40a6-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="d40a6-107">选择**启用 SQL Server 存储镜像**复选框以配置的 SQL Server 数据库和将持久聊天合规性数据提供镜像的数据库的可选实例。</span><span class="sxs-lookup"><span data-stu-id="d40a6-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="d40a6-108">从**镜像 SQL Server 存储**列表中选择一个 SQL Server 和可选实例以用作持久聊天合规性 SQL Server 的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="d40a6-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="d40a6-109">单击**新建**以定义一个新的 SQL Server 和可选的持久聊天 SQL Server 镜像的新实例。</span><span class="sxs-lookup"><span data-stu-id="d40a6-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="d40a6-110">从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。</span><span class="sxs-lookup"><span data-stu-id="d40a6-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="d40a6-111">见证服务器不镜像或主机的数据的持久聊天服务器，但可确保只有一个 SQL Server 镜像配置中随时都是活动的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d40a6-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="d40a6-112">单击**新建**以定义一个新的 SQL Server 见证和可选持久聊天合规性 SQL Server 镜像见证实例。</span><span class="sxs-lookup"><span data-stu-id="d40a6-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="d40a6-113">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="d40a6-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="d40a6-114">完成输入为该池的备份 SQL Server 存储配置并继续进行持久聊天服务器池定义的选项后，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d40a6-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="d40a6-115">单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。</span><span class="sxs-lookup"><span data-stu-id="d40a6-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="d40a6-116">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="d40a6-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d40a6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d40a6-117">See also</span></span>

#### 

[<span data-ttu-id="d40a6-118">规划持久聊天服务器 Skype 中的业务 Server 2015</span><span class="sxs-lookup"><span data-stu-id="d40a6-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="d40a6-119">Skype for Business Server 2015 服务器要求</span><span class="sxs-lookup"><span data-stu-id="d40a6-119">Server requirements for Skype for Business Server 2015</span></span>](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="d40a6-120">硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="d40a6-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="d40a6-121">为业务服务器 2015 Skype 中配置持久聊天服务器合规性的服务</span><span class="sxs-lookup"><span data-stu-id="d40a6-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../manage/persistent-chat/configure-compliance.md)

