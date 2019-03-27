---
title: 添加前端监控存储页面
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 您定义监视 SQL Server 存储通过配置以下属性：
ms.openlocfilehash: e68383ba75c89460ba599aa083e01db1151fdd2f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893951"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="b9c5c-103">添加前端监控存储页面</span><span class="sxs-lookup"><span data-stu-id="b9c5c-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="b9c5c-104">您通过配置以下属性的**定义监视 SQL Server 存储**：</span><span class="sxs-lookup"><span data-stu-id="b9c5c-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="b9c5c-105">**监控 SQL Server 存储**： 从列表中选择 SQL Server 完全限定的域名 （和可选实例）。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="b9c5c-106">单击**新建**以创建一个新的 SQL Server FQDN 定义，以及 （可选） 的监控服务器存储的实例名称。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="b9c5c-107">如果您想要添加数据库镜像监控服务器，请选择**启用 SQL Server 存储镜像**复选框。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="b9c5c-108">从列表中选择现有**监控 SQL Server 存储镜像**。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="b9c5c-109">单击**新建**以创建一个新的 SQL Server FQDN 定义和镜像存储的实例名称 （可选）。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="b9c5c-110">如果选中**启用 SQL Server 存储镜像**，或者选择**使用 SQL Server 镜像见证启用自动故障转移**以选择 SQL Server 镜像见证存储从列表中。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="b9c5c-111">单击**新建**以创建一个新的 SQL Server FQDN 定义和镜像见证存储的实例名称 （可选）。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="b9c5c-112">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b9c5c-113">完成为此对话框，然后继续进行配置输入选项后，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="b9c5c-114">单击**取消**以放弃所有更改并结束该向导。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="b9c5c-115">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="b9c5c-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9c5c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c5c-116">See also</span></span>

[<span data-ttu-id="b9c5c-117">在 Skype for Business Server 2015 中将监视存储与前端池关联</span><span class="sxs-lookup"><span data-stu-id="b9c5c-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
