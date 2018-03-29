---
title: 持久聊天常规设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 您可以通过配置或定义这些属性编辑为持久聊天服务器池的持久聊天服务器的常规设置：
ms.openlocfilehash: 84d6600c6ff99d55233ad40c7238fbb2c0480c98
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="db207-103">持久聊天常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="db207-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="db207-104">您可以通过配置或定义这些属性编辑为持久聊天服务器池的持久聊天服务器的**常规**设置：</span><span class="sxs-lookup"><span data-stu-id="db207-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="db207-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="db207-105">**General**</span></span>
  
- <span data-ttu-id="db207-106">**FQDN**： 编辑此设置定义持久聊天服务器或持久聊天服务器池的完全限定的域名</span><span class="sxs-lookup"><span data-stu-id="db207-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="db207-107">**持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。</span><span class="sxs-lookup"><span data-stu-id="db207-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="db207-108">此设置将使容易对您的用户将给定的持久聊天服务器或基于显示名称而不是更难理解完全合格的域名称的持久聊天服务器池相关联。</span><span class="sxs-lookup"><span data-stu-id="db207-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="db207-109">**持久聊天端口**：指定要用于持久聊天的端口。</span><span class="sxs-lookup"><span data-stu-id="db207-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="db207-110">您可以通过配置或定义这些属性编辑持久聊天服务器或持久聊天服务器池的**关联**设置：</span><span class="sxs-lookup"><span data-stu-id="db207-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="db207-111">**关联**</span><span class="sxs-lookup"><span data-stu-id="db207-111">**Associations**</span></span>
  
- <span data-ttu-id="db207-112">**SQL Server 存储**：从列表中选择 SQL Server 存储和可选的命名实例。</span><span class="sxs-lookup"><span data-stu-id="db207-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="db207-113">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-114">如果您想要启用镜像的主 SQL Server 存储区，请选择**启用 SQL Server 存储镜像**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="db207-115">如果您选择启用 SQL Server 存储镜像，商店和实例从列表中选择**镜像 SQL Server 存储**。</span><span class="sxs-lookup"><span data-stu-id="db207-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="db207-116">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-117">如果希望主 SQL Server 存储的自动故障切换，请选择**使用 SQL Server 镜像见证启用自动故障切换**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="db207-118">如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="db207-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="db207-119">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="db207-120">选择**使用备份 SQL Server 存储以实现灾难恢复**复选框如果您希望能够使用的 SQL Server 灾难恢复</span><span class="sxs-lookup"><span data-stu-id="db207-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="db207-121">如果选择启用灾难恢复，则从“**备份 SQL Server 存储**”列表选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="db207-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="db207-122">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-123">如果您想要启用镜像的镜像存储备份 SQL Server，请选择**启用 SQL Server 存储镜像**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="db207-124">如果您选择启用镜像备份 SQL Server 存储，存储和实例从列表中选择**备份 SQL Server 存储镜像**。</span><span class="sxs-lookup"><span data-stu-id="db207-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="db207-125">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-126">如果您希望备份的 SQL Server 存储的自动故障切换，请选择**使用 SQL Server 镜像见证启用自动故障切换**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="db207-127">如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="db207-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="db207-128">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="db207-129">如果要允许使用合规性数据库，则选中“**启用合规性**”复选框</span><span class="sxs-lookup"><span data-stu-id="db207-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="db207-130">如果选择启用合规性，则从“**合规性 SQL Server 存储**”列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="db207-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="db207-131">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-132">如果您想要启用镜像为法规遵从性 SQL Server 存储，请选择**启用 SQL Server 存储镜像**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="db207-133">如果您选择启用镜像的法规遵从性 SQL Server 存储，存储和实例从列表中选择**法规遵从性 SQL Server 存储镜像**。</span><span class="sxs-lookup"><span data-stu-id="db207-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="db207-134">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-135">如果所需的法规遵从性 SQL Server 存储的自动故障转移，请选中**使用 SQL Server 镜像见证启用自动故障切换**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="db207-136">如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="db207-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="db207-137">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="db207-138">如果选择启用合规性，则从“**备份合规性 SQL Server 存储**”列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="db207-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="db207-139">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-140">如果您想要启用镜像为法规遵从性 SQL Server 存储，请选择**启用 SQL Server 存储镜像**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="db207-141">如果您选择启用镜像的法规遵从性 SQL Server 存储，存储和实例从列表中选择**备份法规遵从性 SQL Server 存储镜像**。</span><span class="sxs-lookup"><span data-stu-id="db207-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="db207-142">单击“**新建**”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="db207-143">如果您希望备份法规遵从性 SQL Server 存储的自动故障转移，请选中**使用 SQL Server 镜像见证启用自动故障切换**复选框。</span><span class="sxs-lookup"><span data-stu-id="db207-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="db207-144">如果您选择启用镜像见证启用自动故障转移 SQL Server 存储，存储和实例从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="db207-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="db207-145">单击“**新建**”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="db207-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="db207-146">**文件存储**从列表中选择文件存储位置，或单击**新建**以创建新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="db207-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
 <span data-ttu-id="db207-147">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="db207-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="db207-148">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="db207-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="db207-149">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="db207-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db207-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db207-150">See also</span></span>

#### 

[<span data-ttu-id="db207-151">在 Skype 的持久聊天服务器业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="db207-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="db207-152">持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑</span><span class="sxs-lookup"><span data-stu-id="db207-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="db207-153">为业务服务器 2015年配置在 Skype 的持久聊天服务器的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="db207-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

