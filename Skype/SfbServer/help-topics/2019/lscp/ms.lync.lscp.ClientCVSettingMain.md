---
title: 客户端版本配置
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: 除了指定您想要在您的环境中支持的客户端版本，还可以为尚不具有定义的版本策略的客户端中指定的默认操作。 这使您可以限制在您的环境，可帮助您控制与支持多个客户端版本相关的成本中使用哪些客户端版本。
ms.openlocfilehash: 4b5f76d17c92d0dd478aa9a1a3fe902ccbf35c48
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="client-version-configuration"></a><span data-ttu-id="9c175-104">客户端版本配置</span><span class="sxs-lookup"><span data-stu-id="9c175-104">Client Version Configuration</span></span>
 
<span data-ttu-id="9c175-105">除了指定您想要在您的环境中支持的客户端版本，还可以为尚不具有定义的版本策略的客户端中指定的默认操作。</span><span class="sxs-lookup"><span data-stu-id="9c175-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="9c175-106">这使您可以限制在您的环境，可帮助您控制与支持多个客户端版本相关的成本中使用哪些客户端版本。</span><span class="sxs-lookup"><span data-stu-id="9c175-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="9c175-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="9c175-107">Tasks you can perform</span></span>

<span data-ttu-id="9c175-108">在**客户端版本配置**页上，可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9c175-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="9c175-109">编辑默认 （**全局**） 客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="9c175-109">Edit the default ( **Global**) client version configuration.</span></span>
    
- <span data-ttu-id="9c175-110">创建针对特定站点的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="9c175-110">Create client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="9c175-111">启用和禁用现有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="9c175-111">Enable and disable existing client version configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9c175-112">由于匿名用户未与站点关联，因此匿名用户受全局级别的策略。</span><span class="sxs-lookup"><span data-stu-id="9c175-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="9c175-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="9c175-113">UI Reference</span></span>

<span data-ttu-id="9c175-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="9c175-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="9c175-115">**新**您可以创建针对特定站点的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="9c175-115">**New** You can create a client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="9c175-116">**编辑**您可以更改的任何客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="9c175-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="9c175-117">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c175-117">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9c175-118">**显示详细信息**此选项可打开一个对话框，您可以在其中更改客户端版本配置的选项。</span><span class="sxs-lookup"><span data-stu-id="9c175-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>
    
  - <span data-ttu-id="9c175-119">**选择全部**此选项可选择列表中所有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="9c175-119">**Select All** This option selects all client version configurations in the list.</span></span>
    
  - <span data-ttu-id="9c175-120">**删除**此选项可删除所有选定的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="9c175-120">**Delete** This option deletes all selected client version configurations.</span></span>
    
- <span data-ttu-id="9c175-121">**刷新**您可以刷新客户端版本配置列表以验证所有客户端版本配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="9c175-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>
    
<span data-ttu-id="9c175-122">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="9c175-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9c175-123">有关使用客户端版本配置的详细信息，请参阅操作文档中的[修改客户端不明确支持或受限默认操作](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9c175-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

