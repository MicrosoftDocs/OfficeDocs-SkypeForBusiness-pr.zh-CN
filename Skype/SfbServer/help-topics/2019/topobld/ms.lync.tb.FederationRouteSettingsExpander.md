---
title: 联盟路由设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 要设置站点的联盟路由分配，必须首先在边缘服务器或边缘服务器池中启用联盟。如果未在边缘服务器或池中启用联盟，将无法修改站点的联盟路由分配设置。
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819462"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="49c11-104">联盟路由设置扩展器</span><span class="sxs-lookup"><span data-stu-id="49c11-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="49c11-p102">要设置站点的联盟路由分配，必须首先在边缘服务器或边缘服务器池中启用联盟。如果未在边缘服务器或池中启用联盟，将无法修改站点的联盟路由分配设置。</span><span class="sxs-lookup"><span data-stu-id="49c11-p102">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool. If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="49c11-107">如果在边缘服务器或池配置了联盟设置，则可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="49c11-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="49c11-108">**允许所有站点进行联盟路由分配** 此设置将影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="49c11-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="49c11-109">确保在此站点配置的设置适合所有网站。</span><span class="sxs-lookup"><span data-stu-id="49c11-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="49c11-110">**启用 SIP 联盟** 选择此选项可启用 SIP 联盟路由，然后选择控制器或边缘池作为联盟路由。</span><span class="sxs-lookup"><span data-stu-id="49c11-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="49c11-111">**启用 XMPP 联盟** 选择此选项可启用 XMPP 联盟路由，然后选择控制器或边缘池作为联盟路由。</span><span class="sxs-lookup"><span data-stu-id="49c11-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="49c11-112">XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="49c11-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="49c11-113">有关详细信息 [，请参阅"迁移 XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟"。</span><span class="sxs-lookup"><span data-stu-id="49c11-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

