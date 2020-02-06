---
title: 存档策略新建或编辑现有
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
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 对于托管在 Skype for business 服务器上的用户，使用存档策略控制部署内部和外部通信的存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: e37d4365af0c817d49d4314987ee41392a0d80cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823195"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="4b289-104">存档策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="4b289-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="4b289-105">对于托管在 Skype for business 服务器上的用户，使用存档策略控制部署内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="4b289-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="4b289-106">存档策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="4b289-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="4b289-107">**全局策略**默认情况下，全局策略在所有 Skype for Business 服务器部署中创建。</span><span class="sxs-lookup"><span data-stu-id="4b289-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="4b289-108">您可以编辑全局策略，但无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="4b289-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="4b289-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="4b289-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="4b289-110">**网站策略（可选）** 你可以指定一个或多个网站存档策略，每个策略都可以配置为为特定网站启用和禁用内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="4b289-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="4b289-111">站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="4b289-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="4b289-112">可以编辑或删除站点策略。</span><span class="sxs-lookup"><span data-stu-id="4b289-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="4b289-113">**用户策略（可选）** 你可以指定一个或多个用户存档策略，每个策略都可以配置为针对特定用户启用和禁用内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="4b289-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="4b289-114">用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。</span><span class="sxs-lookup"><span data-stu-id="4b289-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="4b289-115">可以编辑或删除用户策略。</span><span class="sxs-lookup"><span data-stu-id="4b289-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4b289-116">如果你使用 Exchange 集成将存档数据存储在 Microsoft Exchange 中，则 Exchange 2013 策略将控制托管在 Exchange 2013 上的用户的存档。</span><span class="sxs-lookup"><span data-stu-id="4b289-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="4b289-117">若要为这些用户启用存档，用户的邮箱必须放置在原地保留。</span><span class="sxs-lookup"><span data-stu-id="4b289-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="4b289-118">若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="4b289-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="4b289-119">**名称**每个存档策略都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="4b289-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="4b289-120">该名称由你要添加或编辑的策略类型确定：</span><span class="sxs-lookup"><span data-stu-id="4b289-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="4b289-121">**全局策略**默认名称为全局名称。</span><span class="sxs-lookup"><span data-stu-id="4b289-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="4b289-122">可以将该名称更改成一个更具描述性的名称。</span><span class="sxs-lookup"><span data-stu-id="4b289-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="4b289-123">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="4b289-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="4b289-124">**网站策略**此对话框中列出的网站包括部署中的所有可用网站。</span><span class="sxs-lookup"><span data-stu-id="4b289-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="4b289-125">单击某个站点即可将其选中。</span><span class="sxs-lookup"><span data-stu-id="4b289-125">Click a single site to select it.</span></span> <span data-ttu-id="4b289-126">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="4b289-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="4b289-127">**用户策略**指定一个合适的名称，例如特定用户的姓名或组织中的用户组或团队的名称。</span><span class="sxs-lookup"><span data-stu-id="4b289-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="4b289-128">例如，法律部门。</span><span class="sxs-lookup"><span data-stu-id="4b289-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="4b289-129">**说明**这是可选操作。</span><span class="sxs-lookup"><span data-stu-id="4b289-129">**Description** This is optional.</span></span> <span data-ttu-id="4b289-130">使用它提供其他详细信息，如策略的范围或使用。</span><span class="sxs-lookup"><span data-stu-id="4b289-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="4b289-131">例如，与其他网站的法律部门协调。</span><span class="sxs-lookup"><span data-stu-id="4b289-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="4b289-132">**存档内部通信**选中此复选框以启用内部网络上的通信存档。</span><span class="sxs-lookup"><span data-stu-id="4b289-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="4b289-133">默认情况下，不会在任何策略中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b289-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="4b289-134">**存档外部通信**选中此复选框以启用包括外部用户（如远程用户）（包括匿名和 PIC 设置用户）和联盟合作伙伴的通信的存档。</span><span class="sxs-lookup"><span data-stu-id="4b289-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="4b289-135">默认情况下，不会在任何策略中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b289-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="4b289-136">有关存档功能和功能（包括 Exchange 集成）的详细信息，请参阅[在 skype for Business server 2015 中规划存档](../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business server 2015 存档](../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business server 2015 中的存档](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="4b289-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

