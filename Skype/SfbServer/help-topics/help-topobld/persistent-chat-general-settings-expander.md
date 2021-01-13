---
title: 持久聊天常规设置扩展器
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
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 通过配置或定义以下属性编辑持久聊天服务器或持久聊天服务器池的常规设置：
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823848"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="dc810-103">持久聊天常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="dc810-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="dc810-104">通过 **配置或** 定义以下属性编辑持久聊天服务器或持久聊天服务器池的常规设置：</span><span class="sxs-lookup"><span data-stu-id="dc810-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="dc810-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="dc810-105">**General**</span></span>
  
- <span data-ttu-id="dc810-106">**FQDN：** 编辑此设置以定义持久聊天服务器或持久聊天服务器池的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="dc810-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="dc810-107">**持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。</span><span class="sxs-lookup"><span data-stu-id="dc810-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="dc810-108">此设置将便于用户基于 显示名称 关联给定的持久聊天服务器或持久聊天服务器池，而不是更难以理解的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="dc810-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="dc810-109">**持久聊天端口**：指定要用于持久聊天的端口。</span><span class="sxs-lookup"><span data-stu-id="dc810-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="dc810-110">通过 **配置或** 定义以下属性编辑持久聊天服务器或持久聊天服务器池的关联设置：</span><span class="sxs-lookup"><span data-stu-id="dc810-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="dc810-111">**关联**</span><span class="sxs-lookup"><span data-stu-id="dc810-111">**Associations**</span></span>
  
- <span data-ttu-id="dc810-112">**SQL Server存储**：从SQL Server选择可选存储实例和可选命名实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="dc810-113">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-114">如果要 **为主SQL Server** 启用镜像，请选中"启用存储镜像SQL Server复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-115">如果选择启用存储镜像SQL Server，请从镜像和存储列表中选择SQL Server **实例**。</span><span class="sxs-lookup"><span data-stu-id="dc810-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="dc810-116">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-117">如果希望 **主SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移"SQL Server复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-118">如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc810-119">单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc810-120">如果要 **启用SQL Server** 灾难恢复，请选中"使用备份存储以启用灾难恢复SQL Server复选框</span><span class="sxs-lookup"><span data-stu-id="dc810-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="dc810-121">如果选择启用灾难恢复，则从“备份 SQL Server 存储”列表选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="dc810-122">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-123">如果要 **为SQL Server** 镜像存储启用镜像，请选中"启用SQL Server存储镜像"复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="dc810-124">如果选择启用备份和SQL Server镜像，请从备份和存储镜像列表中选择SQL Server **实例**。</span><span class="sxs-lookup"><span data-stu-id="dc810-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="dc810-125">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-126">如果希望 **备份SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移"SQL Server复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-127">如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc810-128">单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc810-129">如果要允许使用合规性数据库，则选中“启用合规性”复选框</span><span class="sxs-lookup"><span data-stu-id="dc810-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="dc810-130">如果选择启用合规性，则从“合规性 SQL Server 存储”列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="dc810-131">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-132">如果要 **为SQL Server** 存储启用镜像，请选中"启用SQL Server镜像"复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-133">如果选择启用应用商店镜像的合规性SQL Server，请从应用商店镜像的合规性SQL Server **和实例**。</span><span class="sxs-lookup"><span data-stu-id="dc810-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="dc810-134">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-135">如果希望 **合规性SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移"SQL Server复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-136">如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc810-137">单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc810-138">如果选择启用合规性，则从“备份合规性 SQL Server 存储”列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="dc810-139">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-140">如果要 **为SQL Server** 存储启用镜像，请选中"启用SQL Server镜像"复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-141">如果选择启用应用商店镜像的SQL Server，请从存储镜像的"备份合规性"SQL Server **选择存储和实例**。</span><span class="sxs-lookup"><span data-stu-id="dc810-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="dc810-142">单击“新建”以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="dc810-143">如果希望 **备份合规性SQL Server** 自动故障转移，请选中"使用镜像见证启用自动故障转移"SQL Server复选框。</span><span class="sxs-lookup"><span data-stu-id="dc810-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="dc810-144">如果选择启用存储镜像SQL Server启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="dc810-145">单击“新建”以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="dc810-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="dc810-146">**文件存储** 从列表中选择文件存储位置， **或单击"** 新建"以创建新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="dc810-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="dc810-147">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="dc810-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="dc810-148">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="dc810-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="dc810-149">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="dc810-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc810-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc810-150">See also</span></span>

[<span data-ttu-id="dc810-151">在 Skype for Business Server 2015 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="dc810-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="dc810-152">将持久聊天服务器添加到 Skype for Business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="dc810-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="dc810-153">在 Skype for Business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="dc810-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
