---
title: Lync Server 站点设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 若要编辑现有网站的属性，请执行下列操作：
ms.openlocfilehash: aedb248bf229af754d2ef8eb9c5e3837c69c808d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104448"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="6790f-103">Lync Server 站点设置扩展器</span><span class="sxs-lookup"><span data-stu-id="6790f-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="6790f-104">若要编辑现有网站的属性，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6790f-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="6790f-105">站点属性</span><span class="sxs-lookup"><span data-stu-id="6790f-105">Site properties</span></span>

<span data-ttu-id="6790f-106">在网站属性中，可以更改或修改网站名称 (必需) 、说明 (可选) 、城市 (可选) 、省/市/自治区 (可选) 以及国家/地区代码 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="6790f-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="6790f-107">有关站点属性的详细信息，请参阅 [将分支站点添加到拓扑](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)。</span><span class="sxs-lookup"><span data-stu-id="6790f-107">For details about site properties, see [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="6790f-108">联合身份验证路由属性</span><span class="sxs-lookup"><span data-stu-id="6790f-108">Federation Route properties</span></span>

<span data-ttu-id="6790f-109">若要设置站点联盟路由分配，必须先在边缘服务器或边缘服务器池上启用联盟。</span><span class="sxs-lookup"><span data-stu-id="6790f-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="6790f-110">如果未在边缘服务器或池中启用联盟，则网站的联盟路由分配设置将不能进行修改。</span><span class="sxs-lookup"><span data-stu-id="6790f-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="6790f-111">如果已配置边缘服务器或池的联盟设置，请选择" **在** 站点级别启用"。</span><span class="sxs-lookup"><span data-stu-id="6790f-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="6790f-112">然后从下拉列表中选择边缘或控制器以设置为联盟路由。</span><span class="sxs-lookup"><span data-stu-id="6790f-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="6790f-113">此设置将影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="6790f-113">This setting will affect all sites.</span></span> <span data-ttu-id="6790f-114">确保您在此站点配置的设置适合所有网站。</span><span class="sxs-lookup"><span data-stu-id="6790f-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="6790f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6790f-115">See also</span></span>

<span data-ttu-id="6790f-116">有关详细信息，请参阅 [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)。</span><span class="sxs-lookup"><span data-stu-id="6790f-116">For details, see [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span></span>