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
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 可以通过配置或定义以下属性来编辑持久聊天服务器或持久聊天服务器池的常规设置：
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215993"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="17e31-103">持久聊天常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="17e31-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="17e31-104">可以通过配置或定义以下属性来编辑持久聊天服务器或持久聊天服务器池的 **常规** 设置：</span><span class="sxs-lookup"><span data-stu-id="17e31-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="17e31-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="17e31-105">**General**</span></span>
  
- <span data-ttu-id="17e31-106">**FQDN**：编辑此设置以定义持久聊天服务器或持久聊天服务器池的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="17e31-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="17e31-107">**持久聊天池的显示名称**：定义此设置以提供服务器或池的用户友好和用户可读设置。</span><span class="sxs-lookup"><span data-stu-id="17e31-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="17e31-108">此设置将使用户更轻松地根据显示名称关联给定的持久聊天服务器或持久聊天服务器池，而不是更难理解完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="17e31-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="17e31-109">**持久聊天端口**：指定要用于持久聊天的端口。</span><span class="sxs-lookup"><span data-stu-id="17e31-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="17e31-110">可以通过配置或定义以下属性来编辑持久聊天服务器或持久聊天服务器池的 **关联** 设置：</span><span class="sxs-lookup"><span data-stu-id="17e31-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="17e31-111">**群体**</span><span class="sxs-lookup"><span data-stu-id="17e31-111">**Associations**</span></span>
  
- <span data-ttu-id="17e31-112">**Sql server 存储**：从列表中选择 sql server 存储和可选的命名实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="17e31-113">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-114">如果要为主 SQL Server 存储启用镜像，请选中 " **启用 SQL Server 存储镜像** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-115">如果选择启用 SQL Server 存储镜像，请从 " **镜像 SQL server 存储**" 列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="17e31-116">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-117">如果需要主 SQL Server 存储的自动故障转移，则选中 " **使用 SQL Server 镜像见证启用自动故障转移** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-118">如果选择启用 SQL Server 存储镜像见证以启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="17e31-119">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="17e31-120">如果要启用 SQL Server 灾难恢复，请选中 " **使用备份 SQL Server 存储来启用灾难恢复** " 复选框</span><span class="sxs-lookup"><span data-stu-id="17e31-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="17e31-121">如果选择启用灾难恢复，则从“备份 SQL Server 存储”\*\*\*\* 列表选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="17e31-122">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-123">如果要为备份 SQL Server 镜像存储启用镜像，请选中 " **启用 SQL server 存储镜像** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="17e31-124">如果选择启用 "备份 SQL Server 存储镜像"，请从 " **备份 Sql server 存储镜像**" 列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="17e31-125">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-126">如果需要备份 SQL Server 存储的自动故障转移，则选中 " **使用 SQL Server 镜像见证启用自动故障转移** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-127">如果选择启用 SQL Server 存储镜像见证以启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="17e31-128">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="17e31-129">如果要允许使用合规性数据库，则选中“启用合规性”\*\*\*\* 复选框</span><span class="sxs-lookup"><span data-stu-id="17e31-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="17e31-130">如果选择启用合规性，则从“合规性 SQL Server 存储”\*\*\*\* 列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="17e31-131">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-132">如果要为合规性 SQL Server 存储启用镜像，请选中 " **启用 SQL server 存储镜像** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-133">如果选择启用合规性 SQL Server 存储镜像，请从 "列表 **合规性 Sql server 存储镜像**" 中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="17e31-134">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-135">如果要对合规性 SQL Server 存储进行自动故障转移，请选中 " **使用 SQL Server 镜像见证启用自动故障转移** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-136">如果选择启用 SQL Server 存储镜像见证以启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="17e31-137">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="17e31-138">如果选择启用合规性，则从“备份合规性 SQL Server 存储”\*\*\*\* 列表中选择一个存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="17e31-139">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-140">如果要为合规性 SQL Server 存储启用镜像，请选中 " **启用 SQL server 存储镜像** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-141">如果选择启用合规性 SQL Server 存储镜像，请从 list **Backup 合规性 Sql Server 存储镜像**中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="17e31-142">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="17e31-143">如果要对备份合规性 SQL Server 存储进行自动故障转移，请选中 " **使用 SQL Server 镜像见证启用自动故障转移** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="17e31-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="17e31-144">如果选择启用 SQL Server 存储镜像见证以启用自动故障转移，请从列表中选择存储和实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="17e31-145">单击“新建”\*\*\*\* 以定义一个新的 SQL Server 存储和见证存储的可选实例。</span><span class="sxs-lookup"><span data-stu-id="17e31-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="17e31-146">**文件存储** 从列表中选择文件存储位置，或单击 " **新建** " 创建新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="17e31-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="17e31-147">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="17e31-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="17e31-148">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="17e31-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="17e31-149">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="17e31-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17e31-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17e31-150">See also</span></span>

[<span data-ttu-id="17e31-151">在 Skype for Business Server 2015 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="17e31-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="17e31-152">将持久聊天服务器添加到 Skype for business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="17e31-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="17e31-153">在 Skype for business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="17e31-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
