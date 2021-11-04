---
title: 联盟路由设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 要设置站点的联盟路由分配，必须首先在边缘服务器或边缘服务器池中启用联盟。如果未在边缘服务器或池中启用联盟，将无法修改站点的联盟路由分配设置。
ms.openlocfilehash: 565ec7fc5888f6b2a2dbe0c6c63772cbe0863f91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739748"
---
# <a name="federation-route-settings-expander"></a>联盟路由设置扩展器
 
要设置站点的联盟路由分配，必须首先在边缘服务器或边缘服务器池中启用联盟。如果未在边缘服务器或池中启用联盟，将无法修改站点的联盟路由分配设置。

如果在边缘服务器或池配置了联盟设置，则可以配置以下选项： 
  
- **允许将联盟路由分配到所有站点** 此设置将影响所有网站。 确保您在此站点配置的设置适合所有网站。
    
- **启用 SIP 联盟** 选择此选项可启用 SIP 联盟路由，然后选择控制器或边缘池作为联盟路由。
    
- **启用 XMPP 联盟** 选择此选项可启用 XMPP 联盟路由，然后选择控制器或边缘池作为联盟路由。
- 
  > [!NOTE]
  > XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。
    

