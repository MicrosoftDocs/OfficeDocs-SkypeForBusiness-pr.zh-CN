---
title: 联合身份验证路由设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。 如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。
ms.openlocfilehash: 37b3dc26b12ba1ddba336f8847e16d47124a5cca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912020"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="f7754-104">联合身份验证路由设置扩展器</span><span class="sxs-lookup"><span data-stu-id="f7754-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="f7754-105">若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。</span><span class="sxs-lookup"><span data-stu-id="f7754-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="f7754-106">如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。</span><span class="sxs-lookup"><span data-stu-id="f7754-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="f7754-107">如果尚未配置边缘服务器或池联盟设置，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="f7754-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="f7754-108">**允许联盟路由分配给所有网站**此设置会影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="f7754-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="f7754-109">确保您要在该站点上配置的设置是适用于所有网站。</span><span class="sxs-lookup"><span data-stu-id="f7754-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="f7754-110">**启用 SIP 联盟**选择此选项可启用 SIP 联盟路由，并作为联盟路由选择一个控制器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="f7754-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="f7754-111">**启用 XMPP 联盟**选择此选项可启用 XMPP 联盟路由，并作为联盟路由选择一个控制器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="f7754-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="f7754-112">XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="f7754-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f7754-113">有关详细信息，请参阅[迁移 XMPP 联盟](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="f7754-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

