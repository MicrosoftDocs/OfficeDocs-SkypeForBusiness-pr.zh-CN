---
title: 添加前端监控存储页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: '你可以通过配置以下属性来定义监视 SQL Server 存储:'
ms.openlocfilehash: 3749a780e63ced4c8fb06499709198885b2bbb1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297766"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="16ce1-103">添加前端监控存储页面</span><span class="sxs-lookup"><span data-stu-id="16ce1-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="16ce1-104">你可以通过配置以下属性来**定义监视 SQL Server 存储**:</span><span class="sxs-lookup"><span data-stu-id="16ce1-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="16ce1-105">**监视 SQL server 应用商店**: 从列表中选择 sql Server 完全限定的域名 (和实例)。</span><span class="sxs-lookup"><span data-stu-id="16ce1-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="16ce1-106">单击 "**新建**" 以创建新的 SQL Server FQDN 定义, 还可以选择监视服务器存储的实例名称。</span><span class="sxs-lookup"><span data-stu-id="16ce1-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="16ce1-107">如果要为监视服务器添加数据库镜像, 请选中 "**启用 SQL Server 应用商店镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="16ce1-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="16ce1-108">从列表中选择一个现有的**监视 SQL Server 应用商店镜像**。</span><span class="sxs-lookup"><span data-stu-id="16ce1-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="16ce1-109">单击 "**新建**" 以创建新的 SQL Server FQDN 定义, 还可以选择镜像存储的实例名称。</span><span class="sxs-lookup"><span data-stu-id="16ce1-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="16ce1-110">如果选择 "**启用 Sql server 应用商店镜像**", 则可以选择 "**使用 sql server 镜像见证启用自动故障转移**", 从列表中选择 SQL Server 镜像存储。</span><span class="sxs-lookup"><span data-stu-id="16ce1-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="16ce1-111">单击 "**新建**" 以创建新的 SQL Server FQDN 定义, 还可以选择用于镜像见证存储的实例名称。</span><span class="sxs-lookup"><span data-stu-id="16ce1-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="16ce1-112">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="16ce1-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="16ce1-113">输入此对话框的选项后, 单击 "**下一步**" 以继续配置。</span><span class="sxs-lookup"><span data-stu-id="16ce1-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="16ce1-114">单击 "**取消**" 放弃所有更改并结束向导。</span><span class="sxs-lookup"><span data-stu-id="16ce1-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="16ce1-115">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="16ce1-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16ce1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16ce1-116">See also</span></span>

[<span data-ttu-id="16ce1-117">将监视存储与 Skype for Business 服务器中的前端池相关联</span><span class="sxs-lookup"><span data-stu-id="16ce1-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
