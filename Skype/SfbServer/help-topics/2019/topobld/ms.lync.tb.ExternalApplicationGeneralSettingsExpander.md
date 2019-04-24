---
title: 外部应用程序常规设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑已定义的受信任应用程序服务器的属性，请按照以下说明。
ms.openlocfilehash: 66f82f4e6dadf39cbfcce77c46cafc2fedd3d168
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220622"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="5af27-103">外部应用程序常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="5af27-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="5af27-104">若要编辑已定义的受信任应用程序服务器的属性，请按照以下说明。</span><span class="sxs-lookup"><span data-stu-id="5af27-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="5af27-105">有两个部分，您可以修改：</span><span class="sxs-lookup"><span data-stu-id="5af27-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="5af27-106">常规设置</span><span class="sxs-lookup"><span data-stu-id="5af27-106">General settings</span></span>
> 
> <span data-ttu-id="5af27-107">下一跃点设置</span><span class="sxs-lookup"><span data-stu-id="5af27-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="5af27-108">常规设置</span><span class="sxs-lookup"><span data-stu-id="5af27-108">General Settings</span></span>

<span data-ttu-id="5af27-109">您可以修改当前完全限定的域名 (FQDN) 的受信任的应用程序服务器池。</span><span class="sxs-lookup"><span data-stu-id="5af27-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="5af27-110">编辑池的 FQDN 的名称。</span><span class="sxs-lookup"><span data-stu-id="5af27-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="5af27-111">域名系统 (DNS) 主机 (A) 记录必须存在新项之前客户端或服务器可以连接到新池的名称。</span><span class="sxs-lookup"><span data-stu-id="5af27-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="5af27-112">如果您需要的配置数据复制到该池，请选中**启用配置数据复制到此池**。</span><span class="sxs-lookup"><span data-stu-id="5af27-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="5af27-113">如果您不想要复制的配置数据，请清除该复选标记。</span><span class="sxs-lookup"><span data-stu-id="5af27-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="5af27-114">下一个跃点设置</span><span class="sxs-lookup"><span data-stu-id="5af27-114">Next Hop Settings</span></span>

<span data-ttu-id="5af27-115">您可以通过从下拉列表中选择的定义的 Enterprise Edition 前端池或 Standard Edition 前端服务器指定受信任应用程序服务器池的下一个跃点服务器。</span><span class="sxs-lookup"><span data-stu-id="5af27-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="5af27-116">控制器或控制器池不受信任应用程序服务器下一个跃点是有效的选项，将不会出现在列表中。</span><span class="sxs-lookup"><span data-stu-id="5af27-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="5af27-117">单击**确定**接受并保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5af27-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="5af27-118">单击“**取消**”将放弃所做的更改并退出属性页面。</span><span class="sxs-lookup"><span data-stu-id="5af27-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

