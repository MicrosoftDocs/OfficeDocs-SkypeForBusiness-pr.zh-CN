---
title: 外部应用程序常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑已定义的受信任的应用程序服务器的属性, 请按照以下说明操作。
ms.openlocfilehash: 96118d968a5c9fdf54a78df24019426e562220dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292778"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="cb83d-103">外部应用程序常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="cb83d-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="cb83d-104">若要编辑已定义的受信任的应用程序服务器的属性, 请按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="cb83d-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="cb83d-105">可以修改两个部分:</span><span class="sxs-lookup"><span data-stu-id="cb83d-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="cb83d-106">常规设置</span><span class="sxs-lookup"><span data-stu-id="cb83d-106">General settings</span></span>
> 
> <span data-ttu-id="cb83d-107">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="cb83d-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="cb83d-108">常规设置</span><span class="sxs-lookup"><span data-stu-id="cb83d-108">General Settings</span></span>

<span data-ttu-id="cb83d-109">你可以修改受信任的应用服务器池的当前完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="cb83d-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="cb83d-110">编辑池 FQDN 的名称。</span><span class="sxs-lookup"><span data-stu-id="cb83d-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="cb83d-111">在客户端或服务器可以连接到新的池名称之前, 必须为新条目存在域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="cb83d-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="cb83d-112">如果需要将配置数据复制到此池, 请选择 "**启用将配置数据复制到此池**"。</span><span class="sxs-lookup"><span data-stu-id="cb83d-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="cb83d-113">如果不想复制配置数据, 请清除复选标记。</span><span class="sxs-lookup"><span data-stu-id="cb83d-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="cb83d-114">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="cb83d-114">Next Hop Settings</span></span>

<span data-ttu-id="cb83d-115">你可以通过从下拉列表中选择定义的企业版前端池或标准版前端服务器来指定受信任的应用程序服务器池的下一个跃点服务器。</span><span class="sxs-lookup"><span data-stu-id="cb83d-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="cb83d-116">Director 或控制器池不是受信任的应用程序服务器下一跃点的有效选择, 并且不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="cb83d-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="cb83d-117">单击 **"确定"** 接受并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cb83d-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="cb83d-118">单击“**取消**”将放弃所做的更改并退出属性页面。</span><span class="sxs-lookup"><span data-stu-id="cb83d-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

