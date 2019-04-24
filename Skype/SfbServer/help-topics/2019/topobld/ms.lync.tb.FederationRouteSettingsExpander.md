---
title: 联合身份验证路由设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 49709f5c4a91e25efb14cc4b2c321c99fec89b68
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201897"
---
# <a name="federation-route-settings-expander"></a>联合身份验证路由设置扩展器
 
若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。 如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。

如果尚未配置边缘服务器或池联盟设置，您可以配置以下选项： 
  
- **允许联盟路由分配给所有网站**此设置会影响所有网站。 确保您要在该站点上配置的设置是适用于所有网站。
    
- **启用 SIP 联盟**选择此选项可启用 SIP 联盟路由，并作为联盟路由选择一个控制器或边缘池。
    
- **启用 XMPP 联盟**选择此选项可启用 XMPP 联盟路由，并作为联盟路由选择一个控制器或边缘池。
- 
  > [!NOTE]
  > XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
    

