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
- NOCSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 若要编辑现有网站的属性，请执行下列操作：
ms.openlocfilehash: 2a771aa3ef7627bf6dcde1004fca0e807bbd5f7b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819644"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="75ce4-103">Lync Server 站点设置扩展器</span><span class="sxs-lookup"><span data-stu-id="75ce4-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="75ce4-104">若要编辑现有网站的属性，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="75ce4-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="75ce4-105">网站属性</span><span class="sxs-lookup"><span data-stu-id="75ce4-105">Site properties</span></span>

<span data-ttu-id="75ce4-106">在 "网站属性" 中，您可以更改或修改 "网站名称（必需）"、"说明" （可选）、"城市" （可选）、"州/省" （可选）和国家/地区代码（可选）。</span><span class="sxs-lookup"><span data-stu-id="75ce4-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="75ce4-107">有关网站属性的详细信息，请参阅[将分支站点添加到你的拓扑](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。</span><span class="sxs-lookup"><span data-stu-id="75ce4-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="75ce4-108">联盟路线属性</span><span class="sxs-lookup"><span data-stu-id="75ce4-108">Federation Route properties</span></span>

<span data-ttu-id="75ce4-109">若要设置站点联合路由分配，必须首先在 Edge 服务器或 Edge 服务器池中启用了联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="75ce4-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="75ce4-110">如果在 Edge 服务器或池上未启用联盟，则该网站的联盟路由分配设置将不可用于修改。</span><span class="sxs-lookup"><span data-stu-id="75ce4-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="75ce4-111">如果已配置 Edge 服务器或池的联盟设置，请在网站级别选择 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="75ce4-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="75ce4-112">然后从下拉列表中选择一个边缘或主管以设置为联盟路线。</span><span class="sxs-lookup"><span data-stu-id="75ce4-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="75ce4-113">此设置将影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="75ce4-113">This setting will affect all sites.</span></span> <span data-ttu-id="75ce4-114">请确保您在此网站上配置的设置适用于所有网站。</span><span class="sxs-lookup"><span data-stu-id="75ce4-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="75ce4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75ce4-115">See also</span></span>

<span data-ttu-id="75ce4-116">有关详细信息，请参阅[外部用户访问的拓扑](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。</span><span class="sxs-lookup"><span data-stu-id="75ce4-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


