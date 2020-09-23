---
title: 外部应用程序常规设置扩展器
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 若要编辑已定义的受信任应用程序服务器的属性，请遵循以下说明。
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218133"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="f5923-103">外部应用程序常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="f5923-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="f5923-104">若要编辑已定义的受信任应用程序服务器的属性，请遵循以下说明。</span><span class="sxs-lookup"><span data-stu-id="f5923-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="f5923-105">您可以修改以下两部分：</span><span class="sxs-lookup"><span data-stu-id="f5923-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="f5923-106">常规设置</span><span class="sxs-lookup"><span data-stu-id="f5923-106">General settings</span></span>
> 
> <span data-ttu-id="f5923-107">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="f5923-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="f5923-108">常规设置</span><span class="sxs-lookup"><span data-stu-id="f5923-108">General Settings</span></span>

<span data-ttu-id="f5923-p101">可以修改受信任应用程序服务器池的当前完全限定域名 (FQDN)。编辑池的 FQDN。新条目必须具有域名系统 (DNS) 主机 (A) 记录，客户端或服务器才能连接到新池名称。</span><span class="sxs-lookup"><span data-stu-id="f5923-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="f5923-p102">如果需要该池配置数据的副本，请选中“允许将配置数据复制到此池”\*\*\*\*。如果不希望复制配置数据，请清除复选标记。</span><span class="sxs-lookup"><span data-stu-id="f5923-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="f5923-114">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="f5923-114">Next Hop Settings</span></span>

<span data-ttu-id="f5923-115">通过从下拉列表中选择定义的 Enterprise Edition 前端池或 Standard Edition 前端服务器，可以指定受信任的应用程序服务器池的下一个跃点服务器。</span><span class="sxs-lookup"><span data-stu-id="f5923-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="f5923-116">控制器或控制器池不是受信任应用程序服务器下一跃点的有效选择，不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="f5923-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="f5923-117">单击 **"确定"** 接受并保存更改。</span><span class="sxs-lookup"><span data-stu-id="f5923-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="f5923-118">单击“取消”\*\*\*\* 将放弃所做的更改并退出属性页面。</span><span class="sxs-lookup"><span data-stu-id="f5923-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

