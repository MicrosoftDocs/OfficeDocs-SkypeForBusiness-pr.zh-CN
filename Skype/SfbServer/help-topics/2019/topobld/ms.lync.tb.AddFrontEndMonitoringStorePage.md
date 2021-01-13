---
title: 添加前端监控存储页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 通过配置以下属性“定义监视 SQL Server 存储”：
ms.openlocfilehash: e867ec998e1380e70125d0ad743f83b06737758e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811662"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="2476f-103">添加前端监控存储页</span><span class="sxs-lookup"><span data-stu-id="2476f-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="2476f-104">通过配置以下属性“定义监视 SQL Server 存储”：</span><span class="sxs-lookup"><span data-stu-id="2476f-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="2476f-105">**监控SQL Server存储**：选择SQL Server完全限定的域名 (（可选）从) 实例。</span><span class="sxs-lookup"><span data-stu-id="2476f-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="2476f-106">单击 **"** 新建"SQL Server FQDN 定义和监控服务器存储的实例名称（可选）。</span><span class="sxs-lookup"><span data-stu-id="2476f-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="2476f-107">如果要 **为监控SQL Server** 数据库镜像，请选中"启用数据库存储镜像"复选框。</span><span class="sxs-lookup"><span data-stu-id="2476f-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="2476f-108">从列表选择一个现有的“监控 SQL Server 存储镜像”。</span><span class="sxs-lookup"><span data-stu-id="2476f-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="2476f-109">单击 **"** 新建"SQL Server FQDN 定义和镜像存储的实例名称（可选）。</span><span class="sxs-lookup"><span data-stu-id="2476f-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="2476f-110">如果选择 **"启用** SQL Server 存储镜像"，可以选择使用 **SQL Server** 镜像见证启用自动故障转移，以从SQL Server选择镜像见证存储。</span><span class="sxs-lookup"><span data-stu-id="2476f-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="2476f-111">单击 **"** 新建"SQL Server FQDN 定义和镜像见证存储的实例名称（可选）。</span><span class="sxs-lookup"><span data-stu-id="2476f-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="2476f-112">单击“上一步”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="2476f-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="2476f-113">完成为此对话框输入选项后单击“下一步”，以继续进行配置。</span><span class="sxs-lookup"><span data-stu-id="2476f-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="2476f-114">单击“取消”将放弃所有更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2476f-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="2476f-115">单击“帮助”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="2476f-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2476f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2476f-116">See also</span></span>

[<span data-ttu-id="2476f-117">将监控存储与 Skype for Business Server 中的前端池关联</span><span class="sxs-lookup"><span data-stu-id="2476f-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
