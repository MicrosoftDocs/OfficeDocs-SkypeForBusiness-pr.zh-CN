---
title: 添加控制器监控
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
description: 你可以通过配置以下属性来定义监视 SQL Server 存储：
ms.openlocfilehash: 0895e5b2e9410d3632c767672f8b54f2732771f5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685325"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="ca619-103">添加控制器监控</span><span class="sxs-lookup"><span data-stu-id="ca619-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="ca619-104">你可以通过配置以下属性来**定义监视 SQL Server 存储**：</span><span class="sxs-lookup"><span data-stu-id="ca619-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="ca619-105">**监视 SQL server 应用商店**：从列表中选择 sql server 完全限定的域名（FQDN）（也称为 sql server 实例）。</span><span class="sxs-lookup"><span data-stu-id="ca619-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="ca619-106">单击 "**新建**" 以创建新的 SQL Server FQDN 定义，还可以选择 "监视服务器" 存储的实例名称。</span><span class="sxs-lookup"><span data-stu-id="ca619-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="ca619-107">如果要为监视服务器添加数据库镜像，请选中 "**启用 SQL Server 应用商店镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ca619-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="ca619-108">从列表中选择一个现有的**监视 SQL Server 应用商店镜像**。</span><span class="sxs-lookup"><span data-stu-id="ca619-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="ca619-109">单击 "**新建**" 以创建新的 SQL Server FQDN 定义和镜像存储的实例名称（可选）。</span><span class="sxs-lookup"><span data-stu-id="ca619-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="ca619-110">如果选择 "**启用 Sql server 应用商店镜像**"，则可以选择 "**使用 sql server 镜像见证启用自动故障转移**"，从列表中选择 SQL Server 镜像存储。</span><span class="sxs-lookup"><span data-stu-id="ca619-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="ca619-111">单击 "**新建**" 创建新的 SQL Server FQDN 定义和镜像见证存储的实例名称（可选）。</span><span class="sxs-lookup"><span data-stu-id="ca619-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="ca619-112">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="ca619-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ca619-113">输入此对话框的选项后，单击 "**下一步**" 以继续配置。</span><span class="sxs-lookup"><span data-stu-id="ca619-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="ca619-114">单击 "**取消**" 放弃所有更改并结束向导。</span><span class="sxs-lookup"><span data-stu-id="ca619-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="ca619-115">单击 "**帮助**" 以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="ca619-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

