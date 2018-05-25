---
title: Lync Server 站点设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 若要编辑现有站点的属性，请执行以下操作：
ms.openlocfilehash: 6ae0154da4e53cffb9d0b6bb02a2eda3cb0cbaa8
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="06ead-103">Lync Server 站点设置扩展器</span><span class="sxs-lookup"><span data-stu-id="06ead-103">Lync Server Site Settings Expander</span></span>
 
<span data-ttu-id="06ead-104">若要编辑现有站点的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="06ead-104">To edit the properties of an existing site, do the following:</span></span>
  
## 

### <a name="site-properties"></a><span data-ttu-id="06ead-105">网站属性</span><span class="sxs-lookup"><span data-stu-id="06ead-105">Site properties</span></span>

<span data-ttu-id="06ead-106">在网站属性，您可以更改或修改站点名称 （必需）、 说明 （可选）、 城市 （可选）、 州/省 （可选） 和国家/地区代码 （可选）。</span><span class="sxs-lookup"><span data-stu-id="06ead-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>
  
<span data-ttu-id="06ead-107">有关站点属性的详细信息，请参阅[Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。</span><span class="sxs-lookup"><span data-stu-id="06ead-107">For details about site properties, see [Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>
  
### <a name="federation-route-properties"></a><span data-ttu-id="06ead-108">联盟路由属性</span><span class="sxs-lookup"><span data-stu-id="06ead-108">Federation Route properties</span></span>

<span data-ttu-id="06ead-109">若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。</span><span class="sxs-lookup"><span data-stu-id="06ead-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="06ead-110">如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。</span><span class="sxs-lookup"><span data-stu-id="06ead-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>
  
<span data-ttu-id="06ead-111">如果尚未配置边缘服务器或池联盟设置，请选中**启用**在网站级别。</span><span class="sxs-lookup"><span data-stu-id="06ead-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="06ead-112">从下拉列表作为联盟路由设置，然后选择边缘或控制器。</span><span class="sxs-lookup"><span data-stu-id="06ead-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="06ead-113">此设置会影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="06ead-113">This setting will affect all sites.</span></span> <span data-ttu-id="06ead-114">确保您要在该站点上配置的设置是适用于所有网站。</span><span class="sxs-lookup"><span data-stu-id="06ead-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span> 
  
### 

<span data-ttu-id="06ead-115">有关详细信息，请参阅[外部用户访问的拓扑](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。</span><span class="sxs-lookup"><span data-stu-id="06ead-115">For details, see [Topologies for External User Access](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>
  

