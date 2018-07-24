---
title: 客户端版本配置
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 除了指定您想要在您的环境中支持的客户端版本，还可以为尚不具有定义的版本策略的客户端中指定的默认操作。 这使您可以限制在您的环境，可帮助您控制与支持多个客户端版本相关的成本中使用哪些客户端版本。
ms.openlocfilehash: 066079914d180faeb54dc682de4f6b628202c6cb
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977368"
---
# <a name="client-version-configuration"></a><span data-ttu-id="fb6b8-104">客户端版本配置</span><span class="sxs-lookup"><span data-stu-id="fb6b8-104">Client Version Configuration</span></span>
 
<span data-ttu-id="fb6b8-105">除了指定您想要在您的环境中支持的客户端版本，还可以为尚不具有定义的版本策略的客户端中指定的默认操作。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="fb6b8-106">这使您可以限制在您的环境，可帮助您控制与支持多个客户端版本相关的成本中使用哪些客户端版本。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="fb6b8-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="fb6b8-107">Tasks you can perform</span></span>

<span data-ttu-id="fb6b8-108">在**客户端版本配置**页上，可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fb6b8-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="fb6b8-109">编辑默认 （**全局**） 客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-109">Edit the default ( **Global**) client version configuration.</span></span>
    
- <span data-ttu-id="fb6b8-110">创建针对特定站点的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-110">Create client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="fb6b8-111">启用和禁用现有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-111">Enable and disable existing client version configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fb6b8-112">由于匿名用户未与站点关联，因此匿名用户受全局级别的策略。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="fb6b8-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="fb6b8-113">UI Reference</span></span>

<span data-ttu-id="fb6b8-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="fb6b8-115">**新**您可以创建针对特定站点的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-115">**New** You can create a client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="fb6b8-116">**编辑**您可以更改的任何客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="fb6b8-117">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fb6b8-117">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="fb6b8-118">**显示详细信息**此选项可打开一个对话框，您可以在其中更改客户端版本配置的选项。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>
    
  - <span data-ttu-id="fb6b8-119">**选择全部**此选项可选择列表中所有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-119">**Select All** This option selects all client version configurations in the list.</span></span>
    
  - <span data-ttu-id="fb6b8-120">**删除**此选项可删除所有选定的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-120">**Delete** This option deletes all selected client version configurations.</span></span>
    
- <span data-ttu-id="fb6b8-121">**刷新**您可以刷新客户端版本配置列表以验证所有客户端版本配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>
    
<span data-ttu-id="fb6b8-122">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[客户端互操作性](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-122">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="fb6b8-123">有关使用客户端版本配置的详细信息，请参阅操作文档中的[修改客户端不明确支持或受限默认操作](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb6b8-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

