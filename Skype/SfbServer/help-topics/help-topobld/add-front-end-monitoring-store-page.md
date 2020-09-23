---
title: 添加前端监控存储页
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 通过配置以下属性“定义监视 SQL Server 存储”：
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218873"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="95760-103">添加前端监控存储页</span><span class="sxs-lookup"><span data-stu-id="95760-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="95760-104">通过配置以下属性“定义监视 SQL Server 存储”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="95760-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="95760-105">**监视 Sql server 存储**：选择 sql server 完全限定的域名 (并从列表中选择一个实例) （可选）。</span><span class="sxs-lookup"><span data-stu-id="95760-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="95760-106">单击 " **新建** " 以创建新的 SQL Server FQDN 定义，还可以选择监视服务器存储的实例名称。</span><span class="sxs-lookup"><span data-stu-id="95760-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="95760-107">如果要为监视服务器添加数据库镜像，请选中 " **启用 SQL Server 存储镜像** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="95760-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="95760-108">从列表选择一个现有的“监控 SQL Server 存储镜像”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="95760-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="95760-109">单击 " **新建** " 创建新的 SQL Server FQDN 定义，还可以选择为镜像存储指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="95760-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="95760-110">如果选择 " **启用 Sql server 存储镜像**"，则可以选择 " **使用 sql server 镜像见证启用自动故障转移** "，从列表中选择 SQL server 镜像存储。</span><span class="sxs-lookup"><span data-stu-id="95760-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="95760-111">单击 " **新建** " 创建新的 SQL Server FQDN 定义，还可以选择为镜像见证存储指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="95760-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="95760-112">单击“上一步”\*\*\*\* 以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="95760-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="95760-113">完成为此对话框输入选项后单击“下一步”\*\*\*\*，以继续进行配置。</span><span class="sxs-lookup"><span data-stu-id="95760-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="95760-114">单击“取消”\*\*\*\* 将放弃所有更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="95760-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="95760-115">单击“帮助”\*\*\*\* 以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="95760-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="95760-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95760-116">See also</span></span>

[<span data-ttu-id="95760-117">将监控存储与 Skype for Business Server 2015 中的前端池关联</span><span class="sxs-lookup"><span data-stu-id="95760-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
