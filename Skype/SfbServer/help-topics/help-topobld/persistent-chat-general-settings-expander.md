---
title: 持久聊天常规设置扩展器
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
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 通过配置或定义这些属性，可以编辑持久聊天服务器或持久聊天服务器池的常规设置：
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819474"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="291a2-103">持久聊天常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="291a2-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="291a2-104">通过配置或定义这些属性，可以编辑持久聊天服务器或持久聊天服务器池的**常规**设置：</span><span class="sxs-lookup"><span data-stu-id="291a2-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="291a2-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="291a2-105">**General**</span></span>
  
- <span data-ttu-id="291a2-106">**FQDN**：编辑此设置以定义持久聊天服务器或持久聊天服务器池的完全限定的域名</span><span class="sxs-lookup"><span data-stu-id="291a2-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="291a2-107">**持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。</span><span class="sxs-lookup"><span data-stu-id="291a2-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="291a2-108">此设置将使你的用户能够更轻松地基于显示名称关联给定的持久聊天服务器或持久聊天服务器池，而不是更难理解完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="291a2-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="291a2-109">**持久聊天端口**：指定要用于持久聊天的端口。</span><span class="sxs-lookup"><span data-stu-id="291a2-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="291a2-110">通过配置或定义这些属性，可以编辑持久聊天服务器或持久聊天服务器池的**关联**设置：</span><span class="sxs-lookup"><span data-stu-id="291a2-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="291a2-111">**关联**</span><span class="sxs-lookup"><span data-stu-id="291a2-111">**Associations**</span></span>
  
- <span data-ttu-id="291a2-112">**SQL Server 存储**：从列表中选择 SQL Server 存储和可选的命名实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="291a2-113">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-114">如果要为主 SQL Server 应用商店启用镜像，请选中 "**启用 SQL Server 应用商店镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-115">如果您选择启用 SQL Server 应用商店镜像，请从列表**镜像 SQL Server 应用商店**中选择应用商店和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="291a2-116">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-117">如果需要主 SQL Server 应用商店的自动故障转移，请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-118">如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移，请从列表中选择 "应用商店和实例"。</span><span class="sxs-lookup"><span data-stu-id="291a2-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="291a2-119">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="291a2-120">如果要启用 SQL Server 灾难恢复的使用，请选中 "**使用备份 SQL Server 存储来启用灾难恢复**" 复选框</span><span class="sxs-lookup"><span data-stu-id="291a2-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="291a2-121">如果选择启用灾难恢复，则从“**备份 SQL Server 存储**”列表选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="291a2-122">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-123">如果要为备份 SQL Server 镜像存储启用镜像，请选中 "**启用 SQL server 应用商店镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="291a2-124">如果您选择启用 "备份 SQL Server 应用商店镜像"，请从列表中选择 "**备份 Sql server 存储" 镜像**中的应用商店和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="291a2-125">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-126">如果需要自动故障切换备份 SQL Server 应用商店，请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-127">如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移，请从列表中选择 "应用商店和实例"。</span><span class="sxs-lookup"><span data-stu-id="291a2-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="291a2-128">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="291a2-129">如果要允许使用合规性数据库，则选中“**启用合规性**”复选框</span><span class="sxs-lookup"><span data-stu-id="291a2-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="291a2-130">如果选择启用合规性，则从“**合规性 SQL Server 存储**”列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="291a2-131">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-132">如果要为合规性 SQL Server 应用商店启用镜像，请选中 "**启用 SQL server 应用商店镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-133">如果你选择启用合规性 SQL Server 应用商店镜像，请从 "列表**合规性 Sql server 应用商店镜像**" 中选择应用商店和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="291a2-134">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-135">如果需要自动故障转移 SQL Server 应用商店，请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-136">如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移，请从列表中选择 "应用商店和实例"。</span><span class="sxs-lookup"><span data-stu-id="291a2-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="291a2-137">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="291a2-138">如果选择启用合规性，则从“**备份合规性 SQL Server 存储**”列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="291a2-139">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-140">如果要为合规性 SQL Server 应用商店启用镜像，请选中 "**启用 SQL server 应用商店镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-141">如果你选择启用合规性 SQL Server 应用商店镜像，请从列表中选择 "**备份合规性 Sql server 应用商店" 镜像**中的应用商店和实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="291a2-142">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="291a2-143">如果想要自动执行备份合规性 SQL Server 应用商店，请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="291a2-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="291a2-144">如果你选择启用 SQL Server 应用商店镜像见证以启用自动故障转移，请从列表中选择 "应用商店和实例"。</span><span class="sxs-lookup"><span data-stu-id="291a2-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="291a2-145">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="291a2-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="291a2-146">**文件存储**从列表中选择文件存储位置，或单击 "**新建**" 以创建新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="291a2-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="291a2-147">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="291a2-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="291a2-148">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="291a2-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="291a2-149">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="291a2-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="291a2-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="291a2-150">See also</span></span>

[<span data-ttu-id="291a2-151">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="291a2-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="291a2-152">将持久聊天服务器添加到 Skype for business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="291a2-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="291a2-153">为 Skype for Business Server 2015 中的持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="291a2-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
