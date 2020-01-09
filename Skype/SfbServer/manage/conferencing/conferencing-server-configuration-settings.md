---
title: 在 Skype for Business Server 中管理会议服务器配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：了解如何在 Skype for Business Server 中管理会议服务器配置设置。
ms.openlocfilehash: be6ccb094cc19a29534d1ca78eb2cae1457d6512
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991897"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="13038-103">在 Skype for Business Server 中管理会议服务器配置设置</span><span class="sxs-lookup"><span data-stu-id="13038-103">Manage conferencing server configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="13038-104">**摘要：** 了解如何在 Skype for Business Server 中管理会议服务器配置设置。</span><span class="sxs-lookup"><span data-stu-id="13038-104">**Summary:** Learn how to manage conferencing server configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="13038-105">本主题描述如何管理会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="13038-105">This topic describes how to manage conferencing configuration settings.</span></span> <span data-ttu-id="13038-106">有关如何规划和部署会议的详细信息，请参阅在 skype for business[服务器中规划会议](../../plan-your-deployment/conferencing/conferencing.md)和[在 Skype for Business 服务器中部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="13038-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="13038-107">会议配置设置决定了会议内容和讲义的最大允许大小;应用程序共享会议服务的最大带宽量;存储限额和到期期;支持的客户端的内部和外部下载的 Url;指向用户可获取会议帮助和资源的内部和外部 Url 的指针;以及用于应用程序共享、客户端音频、文件传输和媒体流量的端口。</span><span class="sxs-lookup"><span data-stu-id="13038-107">Conferencing configuration settings determine such things as the maximum allowed size for meeting content and handouts; maximum amount of bandwidth for the Application Sharing Conferencing service; storage limits and expiration periods; the URLs for the internal and external downloads of the supported client; pointers to internal and external URLs where users can obtain conferencing help and resources; and the ports used for application sharing, client audio, file transfers, and media traffic.</span></span> <span data-ttu-id="13038-108">这些设置可让你管理实际服务器本身。</span><span class="sxs-lookup"><span data-stu-id="13038-108">These settings allow you to manage the actual servers themselves.</span></span> <span data-ttu-id="13038-109">可以使用 Skype for Business Server 命令行管理程序设置这些设置。</span><span class="sxs-lookup"><span data-stu-id="13038-109">These settings can be set by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="13038-110">安装 Skype for Business 服务器时，系统会为你提供单个会议配置设置集合（全局集合）。</span><span class="sxs-lookup"><span data-stu-id="13038-110">When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).</span></span> <span data-ttu-id="13038-111">如果需要为站点或服务创建自定义设置，可以使用 **New-CsConferencingConfiguration** cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="13038-111">If you need to create custom settings for a site or service, you can do so using the **New-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="13038-112">请注意，只能在站点范围或服务范围应用新设置；你无法创建新的会议配置设置全局集合，但是可以使用 **Set-CsConferencingConfiguration** 来修改全局集合。</span><span class="sxs-lookup"><span data-stu-id="13038-112">Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings, but you can modify the global collection by using the **Set-CsConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="13038-113">此外，站点和服务都不能托管多个设置集合。</span><span class="sxs-lookup"><span data-stu-id="13038-113">In addition, no site or service can host more than one collection of settings.</span></span> <span data-ttu-id="13038-114">如果你尝试为 Redmond 站点创建新设置，而 Redmond 站点已托管一个会议配置设置集合，则命令将会失败。</span><span class="sxs-lookup"><span data-stu-id="13038-114">If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.</span></span>
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="13038-115">使用 Skype for Business Server 命令行管理程序管理会议配置设置</span><span class="sxs-lookup"><span data-stu-id="13038-115">Manage conferencing configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="13038-116">若要使用 Skype for Business Server Management Shell 管理会议配置设置，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="13038-116">To manage conferencing configuration settings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="13038-117">**会议配置设置**</span><span class="sxs-lookup"><span data-stu-id="13038-117">**Conferencing configuration settings**</span></span>

|<span data-ttu-id="13038-118">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="13038-118">**Cmdlet**</span></span>|<span data-ttu-id="13038-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="13038-119">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="13038-120">Get-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="13038-120">Get-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="13038-121">返回有关组织的会议配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="13038-121">Returns information about the conferencing configuration settings for your organization.</span></span>  <br/> |
|[<span data-ttu-id="13038-122">New-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="13038-122">New-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="13038-123">创建新的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="13038-123">Creates a new collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="13038-124">Remove-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="13038-124">Remove-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="13038-125">删除指定的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="13038-125">Removes the specified collection of conferencing configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="13038-126">Set-CsConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="13038-126">Set-CsConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="13038-127">修改现有的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="13038-127">Modifies an existing collection of conferencing configuration settings.</span></span>  <br/> |
   
<span data-ttu-id="13038-p104">下面的命令为 Redmond 站点 (site:Redmond) 创建新的会议配置设置集合。在此示例中，包括一个额外的参数 (Organization)，该参数用于将 Organization 属性的值设置为 Litwareinc：</span><span class="sxs-lookup"><span data-stu-id="13038-p104">The following command creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond). In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc:</span></span> 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

<span data-ttu-id="13038-130">请注意，每个站点只能有一个这样的集合，因此，如果 Redmond 站点已经有一个会议配置设置集合，此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="13038-130">Note that you can have only one such collection per site, so this command would fail if the Redmond site already has a collection of conferencing configuration settings.</span></span> 
  
<span data-ttu-id="13038-131">下一个示例定义了一个新的会议配置设置集合，这些设置最初存储在内存中，然后在晚些时候应用到 Redmond 站点。</span><span class="sxs-lookup"><span data-stu-id="13038-131">The next example defines a new collection of conferencing configuration settings, which are stored in memory initially, and then applied to the Redmond site at a later time.</span></span> 
  
<span data-ttu-id="13038-132">第一条命令使用 **New-CsConferencingConfiguration** cmdlet 创建一个新的保存在内存中的设置集合，并存储在变量 $x 中。</span><span class="sxs-lookup"><span data-stu-id="13038-132">The first command uses the **New-CsConferencingConfiguration** cmdlet to create a new, in-memory collection of settings stored in the variable $x.</span></span> <span data-ttu-id="13038-133">InMemory 参数指定应在内存中创建集合，而不立即将该集合应用于 Redmond 站点。</span><span class="sxs-lookup"><span data-stu-id="13038-133">The InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.</span></span>
  
<span data-ttu-id="13038-134">创建集合后，第二个命令将 Organization 属性的值设置为 Litwareinc。</span><span class="sxs-lookup"><span data-stu-id="13038-134">After the collection has been created, the second command sets the value of the Organization property to Litwareinc.</span></span> 
  
<span data-ttu-id="13038-135">最后，第三个命令使用 **Set-CsConferencingConfiguration** cmdlet 将新设置实际应用于 Redmond 站点：</span><span class="sxs-lookup"><span data-stu-id="13038-135">Finally, the third command uses the **Set-CsConferencingConfiguration** cmdlet to actually apply the new settings to the Redmond site:</span></span>
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

<span data-ttu-id="13038-136">如果不调用 **Set-CsConferencingConfiguration**，新的设置就不会生效。</span><span class="sxs-lookup"><span data-stu-id="13038-136">If you do not call the **Set-CsConferencingConfiguration** cmdlet, the new settings will never take effect.</span></span> <span data-ttu-id="13038-137">相反，只要你结束 Windows PowerShell 会话或删除变量 $x，它们就会立即消失。</span><span class="sxs-lookup"><span data-stu-id="13038-137">Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.</span></span>
  

