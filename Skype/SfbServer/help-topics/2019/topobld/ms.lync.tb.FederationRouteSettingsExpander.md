---
title: 联合身份验证路由设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 若要设置站点联合路由分配, 必须首先在 Edge 服务器或 Edge 服务器池中启用了联合身份验证。 如果在 Edge 服务器或池上未启用联盟, 则该网站的联盟路由分配设置将不可用于修改。
ms.openlocfilehash: 6e68bc7cb2f5a9f04e208dc2f27ce7724aa7e793
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292722"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="4f9bc-104">联合身份验证路由设置扩展器</span><span class="sxs-lookup"><span data-stu-id="4f9bc-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="4f9bc-105">若要设置站点联合路由分配, 必须首先在 Edge 服务器或 Edge 服务器池中启用了联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="4f9bc-106">如果在 Edge 服务器或池上未启用联盟, 则该网站的联盟路由分配设置将不可用于修改。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="4f9bc-107">如果已配置 Edge 服务器或池的联盟设置, 则可以配置以下选项:</span><span class="sxs-lookup"><span data-stu-id="4f9bc-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="4f9bc-108">**允许将联盟路由分配给所有网站**此设置将影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="4f9bc-109">请确保您在此网站上配置的设置适用于所有网站。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="4f9bc-110">**启用 SIP 联合**选择此选项以启用 SIP 联盟路由, 然后选择 Director 或 Edge 池作为联盟路由。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="4f9bc-111">**启用 XMPP 联合身份验证**选择此选项以启用 XMPP 联盟路由, 然后选择 Director 或 Edge 池作为联盟路由。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="4f9bc-112">XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4f9bc-113">有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="4f9bc-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

