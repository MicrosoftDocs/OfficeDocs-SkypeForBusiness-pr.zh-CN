---
title: Lync Server 站点设置扩展器
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
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 若要编辑现有网站的属性，请执行以下操作：
ms.openlocfilehash: 69555a04be4125e213ba2eca7afd7255100c0444
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217563"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="71166-103">Lync Server 站点设置扩展器</span><span class="sxs-lookup"><span data-stu-id="71166-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="71166-104">若要编辑现有网站的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="71166-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="71166-105">站点属性</span><span class="sxs-lookup"><span data-stu-id="71166-105">Site properties</span></span>

<span data-ttu-id="71166-106">在 "网站属性" 中，您可以更改或修改 " (必需的网站名称") 、"说明" (可选) 、City (可选) 、州/省 (可选) 以及国家/地区代码 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="71166-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="71166-107">有关网站属性的详细信息，请参阅 [将分支站点添加到您的拓扑](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。</span><span class="sxs-lookup"><span data-stu-id="71166-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="71166-108">联合路由属性</span><span class="sxs-lookup"><span data-stu-id="71166-108">Federation Route properties</span></span>

<span data-ttu-id="71166-109">若要设置站点联合路由分配，必须首先在边缘服务器或边缘服务器池上启用了联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="71166-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="71166-110">如果在边缘服务器或池上未启用联合，则网站的联合路由分配设置将不可修改。</span><span class="sxs-lookup"><span data-stu-id="71166-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="71166-111">如果已配置边缘服务器或池上的联合身份验证设置，请选择 "在网站级别 **启用** "。</span><span class="sxs-lookup"><span data-stu-id="71166-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="71166-112">然后从下拉列表中选择一个边缘或一个控制器，以将其设置为联合路由。</span><span class="sxs-lookup"><span data-stu-id="71166-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="71166-113">此设置将影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="71166-113">This setting will affect all sites.</span></span> <span data-ttu-id="71166-114">确保您在此网站上配置的设置适用于所有网站。</span><span class="sxs-lookup"><span data-stu-id="71166-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="71166-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71166-115">See also</span></span>

<span data-ttu-id="71166-116">有关详细信息，请参阅 [适用于外部用户访问的拓扑](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。</span><span class="sxs-lookup"><span data-stu-id="71166-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


