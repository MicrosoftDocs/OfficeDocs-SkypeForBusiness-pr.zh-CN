---
title: 外部应用程序常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 若要编辑已定义的受信任的应用程序服务器的属性，请按照以下说明操作。
ms.openlocfilehash: 4104b9cf22a3db36afd159c0b7d9812142112ece
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="4325b-103">外部应用程序常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="4325b-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="4325b-104">若要编辑已定义的受信任的应用程序服务器的属性，请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="4325b-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="4325b-105">有两个部分，您可以修改：</span><span class="sxs-lookup"><span data-stu-id="4325b-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="4325b-106">常规设置</span><span class="sxs-lookup"><span data-stu-id="4325b-106">General settings</span></span>
    
> <span data-ttu-id="4325b-107">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="4325b-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="4325b-108">常规设置</span><span class="sxs-lookup"><span data-stu-id="4325b-108">General Settings</span></span>

<span data-ttu-id="4325b-109">您可以修改受信任的应用程序服务器池当前完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="4325b-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="4325b-110">编辑该池的 FQDN 名称。</span><span class="sxs-lookup"><span data-stu-id="4325b-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="4325b-111">域名系统 (DNS) 主机 (A) 记录必须存在新项之前客户端或服务器可以连接到新池的名称。</span><span class="sxs-lookup"><span data-stu-id="4325b-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="4325b-112">如果您需要的配置数据复制到此池，请选择**启用配置数据复制到此池**。</span><span class="sxs-lookup"><span data-stu-id="4325b-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="4325b-113">如果您不想复制的配置数据，请清除复选标记。</span><span class="sxs-lookup"><span data-stu-id="4325b-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="4325b-114">下一个跃点设置</span><span class="sxs-lookup"><span data-stu-id="4325b-114">Next Hop Settings</span></span>

<span data-ttu-id="4325b-115">您可以通过从下拉列表中选择已定义的企业版前端池或标准版前端服务器指定受信任的应用程序服务器池的下一个跃点服务器。</span><span class="sxs-lookup"><span data-stu-id="4325b-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="4325b-116">总监或总监池不是受信任的应用程序服务器下一跃点是有效的选项并不会出现在列表中。</span><span class="sxs-lookup"><span data-stu-id="4325b-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  
## 

<span data-ttu-id="4325b-117">单击**确定**以接受并保存您的更改。</span><span class="sxs-lookup"><span data-stu-id="4325b-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="4325b-118">单击“**取消**”将放弃所做的更改并退出属性页面。</span><span class="sxs-lookup"><span data-stu-id="4325b-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

