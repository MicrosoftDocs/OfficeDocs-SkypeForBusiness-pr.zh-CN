---
title: 联合身份验证路由设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
description: 若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。 如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。
ms.openlocfilehash: f166f74a1d49af168a8ce2a9a193bb9cc49da753
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194026"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="3a838-104">联合身份验证路由设置扩展器</span><span class="sxs-lookup"><span data-stu-id="3a838-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="3a838-105">若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。</span><span class="sxs-lookup"><span data-stu-id="3a838-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="3a838-106">如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。</span><span class="sxs-lookup"><span data-stu-id="3a838-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>
  

<span data-ttu-id="3a838-107">如果尚未配置边缘服务器或池联盟设置，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="3a838-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="3a838-108">**允许联盟路由分配给所有网站**此设置会影响所有网站。</span><span class="sxs-lookup"><span data-stu-id="3a838-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="3a838-109">确保您要在该站点上配置的设置是适用于所有网站。</span><span class="sxs-lookup"><span data-stu-id="3a838-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="3a838-110">**启用 SIP 联盟**选择此选项可启用 SIP 联盟路由，并作为联盟路由选择一个控制器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="3a838-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="3a838-111">**启用 XMPP 联盟**选择此选项可启用 XMPP 联盟路由，并作为联盟路由选择一个控制器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="3a838-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    

