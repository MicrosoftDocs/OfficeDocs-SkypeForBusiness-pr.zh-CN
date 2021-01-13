---
title: 添加持久聊天备份 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 配置将为持久SQL Server持久聊天服务器或持久聊天服务器池提供备份数据库的备份存储。
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818732"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="3f542-103">添加持久聊天备份 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="3f542-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="3f542-104">配置将为持久SQL Server持久聊天服务器或持久聊天服务器池提供备份数据库的备份存储。</span><span class="sxs-lookup"><span data-stu-id="3f542-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="3f542-105">**SQL Server存储**：选择现有SQL Server和可选的持久聊天实例。</span><span class="sxs-lookup"><span data-stu-id="3f542-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="3f542-106">单击 **"** 新建"可定义SQL Server持久聊天备份数据的新实例（可选）。</span><span class="sxs-lookup"><span data-stu-id="3f542-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="3f542-107">选中 **"启用SQL Server存储镜像** "复选框以配置一个SQL Server数据库和一个可选实例，这些实例将为持久聊天备份数据提供镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="3f542-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="3f542-108">从列表 **镜像** SQL Server存储SQL Server和可选实例，以充当持久SQL Server持久聊天备份SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3f542-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="3f542-109">单击 **"** 新建"可定义SQL Server持久聊天记录镜像的新实例和SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="3f542-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="3f542-110">从“使用 SQL Server 镜像见证启用自动故障转移”列表选择一个 SQL Server，用作故障转移情况下的见证服务器。</span><span class="sxs-lookup"><span data-stu-id="3f542-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="3f542-111">见证服务器不镜像或承载持久聊天服务器的数据，但确保镜像配置SQL Server只有一个服务器是SQL Server活动服务器。</span><span class="sxs-lookup"><span data-stu-id="3f542-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="3f542-112">单击 **"** 新建"可定义一SQL Server见证镜像见证中的持久聊天备份SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="3f542-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="3f542-113">单击“上一步”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="3f542-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="3f542-114">完成 **为此** 池的备份池存储配置输入SQL Server单击"下一步"，然后继续执行持久聊天服务器池定义。</span><span class="sxs-lookup"><span data-stu-id="3f542-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="3f542-115">单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。</span><span class="sxs-lookup"><span data-stu-id="3f542-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="3f542-116">单击“帮助”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="3f542-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f542-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f542-117">See also</span></span>

[<span data-ttu-id="3f542-118">在 Skype for Business Server 2015 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="3f542-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="3f542-119">Skype for Business Server 2015 的服务器要求</span><span class="sxs-lookup"><span data-stu-id="3f542-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="3f542-120">Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="3f542-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="3f542-121">在 Skype for Business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="3f542-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
