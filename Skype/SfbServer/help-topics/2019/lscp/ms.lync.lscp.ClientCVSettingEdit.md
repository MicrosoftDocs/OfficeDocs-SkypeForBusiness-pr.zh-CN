---
title: 客户端版本配置创建新的或编辑现有的
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: 客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置与 Skype 的业务服务器安装，并用于启用或禁用整个服务器部署的客户端版本控制。 当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。 如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。
ms.openlocfilehash: 19c7cda4924148c6129e3fc3847c2770c51708d9
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="00d8a-106">客户端版本配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="00d8a-106">Client Version Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="00d8a-107">客户端版本配置设置用于打开或关闭客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="00d8a-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="00d8a-108">全局客户端版本配置与 Skype 的业务服务器安装，并用于启用或禁用整个服务器部署的客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="00d8a-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="00d8a-109">当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。</span><span class="sxs-lookup"><span data-stu-id="00d8a-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="00d8a-110">如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="00d8a-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span> 
  
<span data-ttu-id="00d8a-p103">也可以创建站点特定的客户端版本配置，这样您可以按网站来启用或禁用客户端版本控制。站点特定的配置优先于全局配置。</span><span class="sxs-lookup"><span data-stu-id="00d8a-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="00d8a-113">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="00d8a-113">Tasks you can perform</span></span>

<span data-ttu-id="00d8a-114">您可以在“**新建客户端版本配置**”或“**编辑客户端版本配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="00d8a-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="00d8a-115">添加或修改客户端版本配置的名称。</span><span class="sxs-lookup"><span data-stu-id="00d8a-115">Add or modify the name of the client version configuration.</span></span>
    
- <span data-ttu-id="00d8a-116">启用或禁用全局或某特定站点的客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="00d8a-116">Enable or disable client version control globally or for the specific site.</span></span>
    
- <span data-ttu-id="00d8a-117">添加或修改客户端版本配置的默认操作。</span><span class="sxs-lookup"><span data-stu-id="00d8a-117">Add or modify the default action for the client version configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="00d8a-118">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="00d8a-118">UI Reference</span></span>

<span data-ttu-id="00d8a-119">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="00d8a-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="00d8a-120">**范围**标识客户端版本配置的范围 （全局或站点）。</span><span class="sxs-lookup"><span data-stu-id="00d8a-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>
    
- <span data-ttu-id="00d8a-121">**名称**您可以添加或修改客户端版本配置的名称。</span><span class="sxs-lookup"><span data-stu-id="00d8a-121">**Name** You can add or modify the name of the client version configuration.</span></span>
    
- <span data-ttu-id="00d8a-122">**启用版本控制**您可以启用或禁用全局或站点，具体取决于配置的范围的客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="00d8a-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>
    
- <span data-ttu-id="00d8a-123">**默认操作**您可以选择当用户尝试登录使用客户端应用程序没有任何特定客户端版本策略将应用默认操作。</span><span class="sxs-lookup"><span data-stu-id="00d8a-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="00d8a-124">您具有以下选项：</span><span class="sxs-lookup"><span data-stu-id="00d8a-124">You have the following options:</span></span>
    
  - <span data-ttu-id="00d8a-125">**允许**允许客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器。</span><span class="sxs-lookup"><span data-stu-id="00d8a-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>
    
  - <span data-ttu-id="00d8a-126">**阻止**阻止客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器。</span><span class="sxs-lookup"><span data-stu-id="00d8a-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>
    
  - <span data-ttu-id="00d8a-127">**使用 URL 阻止**阻止客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器，并包括包含的 URL，可以下载更新的客户端一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="00d8a-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>
    
  - <span data-ttu-id="00d8a-128">**使用 URL 允许**允许客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器，并包括包含 URL 的错误消息，可以下载更新的客户端。</span><span class="sxs-lookup"><span data-stu-id="00d8a-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>
    
  - <span data-ttu-id="00d8a-129">**URL**如果选择了**使用 URL 阻止**或**使用 URL 允许**，则可以指定要包含在错误消息的客户端下载 URL。</span><span class="sxs-lookup"><span data-stu-id="00d8a-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>
    
<span data-ttu-id="00d8a-130">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="00d8a-130">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="00d8a-131">有关使用客户端版本配置的详细信息，请参阅操作文档中的[修改客户端不明确支持或受限默认操作](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="00d8a-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

