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
description: 配置 SQL Server 存储的符合性，将提供数据库的持久聊天服务器或持久聊天服务器的法规遵从性功能。
ms.openlocfilehash: 7854255195e73dcf03ce9027cdd7390c8f4bde54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="a102e-103">添加持久聊天合规性 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="a102e-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="a102e-104">配置 SQL Server 存储的符合性，将提供数据库的持久聊天服务器或持久聊天服务器的法规遵从性功能。</span><span class="sxs-lookup"><span data-stu-id="a102e-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="a102e-105">**SQL Server 存储**： 为持久聊天中选择现有的 SQL Server 和实例 （可选）。</span><span class="sxs-lookup"><span data-stu-id="a102e-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="a102e-106">单击**新建**以定义新的 SQL Server 和 （可选） 为持久聊天的法规遵从性数据的新实例。</span><span class="sxs-lookup"><span data-stu-id="a102e-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="a102e-107">选择**启用 SQL Server 存储镜像**复选框来配置 SQL Server 数据库和可选将提供持久聊天的法规遵从性数据镜像的数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="a102e-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="a102e-108">从**镜像 SQL Server 存储**列表中选择要用作 SQL Server 镜像持久聊天遵守 SQL Server 的 SQL Server 和可选的实例。</span><span class="sxs-lookup"><span data-stu-id="a102e-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="a102e-109">单击**新建**以定义新的 SQL Server 和 （可选） 为持久聊天 SQL Server 镜像的新实例。</span><span class="sxs-lookup"><span data-stu-id="a102e-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="a102e-110">从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。</span><span class="sxs-lookup"><span data-stu-id="a102e-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="a102e-111">见证服务器不镜像或主机的数据持久聊天服务器，但可以确保将镜像配置中只有一个 SQL Server 在任何时间进行活动的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a102e-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="a102e-112">单击**新建**以定义新的 SQL Server 见证 （可选） 持续聊天遵守 SQL Server 镜像见证实例。</span><span class="sxs-lookup"><span data-stu-id="a102e-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="a102e-113">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="a102e-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a102e-114">输入此池的备份 SQL Server 存储配置并继续持久聊天服务器池定义的选项之后，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a102e-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="a102e-115">单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。</span><span class="sxs-lookup"><span data-stu-id="a102e-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="a102e-116">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="a102e-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a102e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a102e-117">See also</span></span>

#### 

[<span data-ttu-id="a102e-118">在 Skype 的持久聊天服务器业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="a102e-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="a102e-119">业务服务器 2015 Skype 的的服务要求</span><span class="sxs-lookup"><span data-stu-id="a102e-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="a102e-120">硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="a102e-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="a102e-121">在 Skype 为业务服务器 2015年配置持久聊天服务器的法规遵从性服务</span><span class="sxs-lookup"><span data-stu-id="a102e-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)

