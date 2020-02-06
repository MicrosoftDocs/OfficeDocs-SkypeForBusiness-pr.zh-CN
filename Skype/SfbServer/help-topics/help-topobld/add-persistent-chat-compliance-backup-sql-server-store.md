---
title: 添加持久聊天合规性备份 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 配置将为持久聊天服务器或持久聊天服务器合规性的 SQL Server 存储提供备份数据库的备份合规性 SQL Server 存储。
ms.openlocfilehash: e557651c7c55a847de85be1ce724168fcc713a96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820694"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="ddf35-103">添加持久聊天合规性备份 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="ddf35-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="ddf35-104">配置将为持久聊天服务器或持久聊天服务器合规性的 SQL Server 存储提供备份数据库的备份合规性 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="ddf35-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="ddf35-105">**SQL server 应用商店**：选择现有的 SQL server 和（可选）持久聊天的实例。</span><span class="sxs-lookup"><span data-stu-id="ddf35-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="ddf35-106">单击 "**新建**" 以定义新的 SQL Server，还可以选择新的持久聊天备份合规性数据实例。</span><span class="sxs-lookup"><span data-stu-id="ddf35-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="ddf35-107">选中 "**启用 Sql server 应用商店镜像**" 复选框以配置 sql server 数据库和可选实例，该数据库将为持久的聊天备份合规性数据提供镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="ddf35-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="ddf35-108">从列表中选择 "**镜像 sql** server" 将 sql server 和可选实例用作持久的 "聊天" 备份合规性 sql SERVER 的 sql server 镜像。</span><span class="sxs-lookup"><span data-stu-id="ddf35-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="ddf35-109">单击 "**新建**" 以定义新的 SQL Server 和持久聊天 SQL server 镜像的新实例（可选）。</span><span class="sxs-lookup"><span data-stu-id="ddf35-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="ddf35-110">从“**使用 SQL Server 镜像见证启用自动故障转移**”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。</span><span class="sxs-lookup"><span data-stu-id="ddf35-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="ddf35-111">见证服务器不会镜像或承载持久聊天服务器的数据，但可确保镜像配置中的每个 SQL Server 在任何时候都是活动 SQL 服务器。</span><span class="sxs-lookup"><span data-stu-id="ddf35-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="ddf35-112">单击 "**新建**" 以定义新的 SQL server 见证（可选择一个适用于持久的聊天备份合规性 sql server 镜像见证的实例）。</span><span class="sxs-lookup"><span data-stu-id="ddf35-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="ddf35-113">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="ddf35-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ddf35-114">输入此池的备份 SQL Server 应用商店配置的选项后，单击 "**下一步**"，然后继续使用持久聊天服务器池定义。</span><span class="sxs-lookup"><span data-stu-id="ddf35-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ddf35-115">单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。</span><span class="sxs-lookup"><span data-stu-id="ddf35-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ddf35-116">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="ddf35-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ddf35-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddf35-117">See also</span></span>

[<span data-ttu-id="ddf35-118">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="ddf35-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ddf35-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ddf35-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="ddf35-120">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="ddf35-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="ddf35-121">为 Skype for Business Server 2015 中的持久聊天服务器配置合规性服务</span><span class="sxs-lookup"><span data-stu-id="ddf35-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="ddf35-122">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ddf35-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
