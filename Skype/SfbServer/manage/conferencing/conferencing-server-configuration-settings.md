---
title: 管理会议服务器配置设置中 Skype 业务服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要： 了解如何管理会议服务器配置设置中 Skype 业务服务器。
ms.openlocfilehash: a12226f9f7d56f9f8a61b6f820a2c0f9744121fc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890379"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="2a209-103">管理会议服务器配置设置中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="2a209-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="2a209-104">**摘要：** 了解如何管理会议服务器配置设置中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="2a209-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="2a209-105">本主题描述如何管理会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="2a209-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="2a209-106">有关如何规划和部署会议的详细信息，请参阅[Plan for Business Server 的 Skype 中的会议](../../plan-your-deployment/conferencing/conferencing.md)和[Skype 业务服务器中的部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="2a209-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="2a209-107">会议配置设置确定诸如最大允许大小会议内容和讲义;最大数量的带宽为应用程序共享会议服务;存储限制和过期时段;内部和外部 Url 下载的受支持的客户端;指向内部和外部 Url，用户可从中获取会议帮助和资源。和用于应用程序共享、 客户端音频、 文件传输和媒体流量的端口。</span><span class="sxs-lookup"><span data-stu-id="2a209-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="2a209-108">这些设置可让你管理实际服务器本身。</span><span class="sxs-lookup"><span data-stu-id="2a209-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="2a209-109">这些设置可以设置使用 Skype 业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="2a209-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="2a209-110">业务服务器安装 Skype 时，系统您提供单个的会议配置设置 （的全局集合）。</span><span class="sxs-lookup"><span data-stu-id="2a209-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="2a209-111">如果需要为站点或服务创建自定义设置，可以使用 **New-CsConferencingConfiguration** cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="2a209-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="2a209-112">请注意，只能在站点范围或服务范围应用新设置；你无法创建新的会议配置设置全局集合，但是可以使用 **Set-CsConferencingConfiguration** 来修改全局集合。</span><span class="sxs-lookup"><span data-stu-id="2a209-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="2a209-113">此外，站点和服务都不能托管多个设置集合。</span><span class="sxs-lookup"><span data-stu-id="2a209-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="2a209-114">如果你尝试为 Redmond 站点创建新设置，而 Redmond 站点已托管一个会议配置设置集合，则命令将会失败。</span><span class="sxs-lookup"><span data-stu-id="2a209-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2a209-115">使用 Skype 业务 Server Management Shell 管理会议配置设置</span><span class="sxs-lookup"><span data-stu-id="2a209-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2a209-116">若要使用 Skype 业务 Server Management Shell 管理会议配置设置，请使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2a209-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="2a209-117">**会议配置设置**</span><span class="sxs-lookup"><span data-stu-id="2a209-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="2a209-118">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="2a209-118">**Cmdlet**</span></span>|<span data-ttu-id="2a209-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a209-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2a209-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a209-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="2a209-121">返回有关组织的会议配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="2a209-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="2a209-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a209-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="2a209-123">创建新的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="2a209-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="2a209-124">Remove-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a209-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="2a209-125">删除指定的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="2a209-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="2a209-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a209-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="2a209-127">修改现有的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="2a209-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="2a209-p104">下面的命令为 Redmond 站点 (site:Redmond) 创建新的会议配置设置集合。在此示例中，包括一个额外的参数 (Organization)，该参数用于将 Organization 属性的值设置为 Litwareinc：</span><span class="sxs-lookup"><span data-stu-id="2a209-p104">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond). In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="2a209-130">请注意，每个站点只能有一个这样的集合，因此，如果 Redmond 站点已经有一个会议配置设置集合，此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="2a209-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="2a209-131">下一个示例定义了一个新的会议配置设置集合，这些设置最初存储在内存中，然后在晚些时候应用到 Redmond 站点。</span><span class="sxs-lookup"><span data-stu-id="2a209-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="2a209-132">第一条命令使用 **New-CsConferencingConfiguration** cmdlet 创建一个新的保存在内存中的设置集合，并存储在变量 $x 中。</span><span class="sxs-lookup"><span data-stu-id="2a209-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="2a209-133">InMemory 参数指定应在内存中创建集合，而不立即将该集合应用于 Redmond 站点。</span><span class="sxs-lookup"><span data-stu-id="2a209-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="2a209-134">创建集合后，第二个命令将 Organization 属性的值设置为 Litwareinc。</span><span class="sxs-lookup"><span data-stu-id="2a209-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="2a209-135">最后，第三个命令使用 **Set-CsConferencingConfiguration** cmdlet 将新设置实际应用于 Redmond 站点：</span><span class="sxs-lookup"><span data-stu-id="2a209-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="2a209-136">如果不调用 **Set-CsConferencingConfiguration**，新的设置就不会生效。</span><span class="sxs-lookup"><span data-stu-id="2a209-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="2a209-137">相反，只要你结束 Windows PowerShell 会话或删除变量 $x，它们就会立即消失。</span><span class="sxs-lookup"><span data-stu-id="2a209-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

