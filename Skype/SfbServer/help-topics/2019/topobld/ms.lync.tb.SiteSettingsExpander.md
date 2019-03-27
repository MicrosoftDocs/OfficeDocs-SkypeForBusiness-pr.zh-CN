---
title: Lync Server 站点设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑现有站点的属性，请执行以下操作：
ms.openlocfilehash: fdbcd5ddb62de7d4d4040e0b790e3475e20372c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887045"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 站点设置扩展器

若要编辑现有站点的属性，请执行以下操作：



## <a name="site-properties"></a>网站属性

在网站属性，您可以更改或修改站点名称 （必需）、 说明 （可选）、 城市 （可选）、 州/省 （可选） 和国家/地区代码 （可选）。

有关站点属性的详细信息，请参阅[Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。

## <a name="federation-route-properties"></a>联盟路由属性

若要设置站点联盟路由分配，首先必须在边缘服务器或边缘服务器池启用联盟。 如果边缘服务器或池上未启用联盟，则站点联盟路由分配设置将不可用进行修改。

如果尚未配置边缘服务器或池联盟设置，请选中**启用**在网站级别。 从下拉列表作为联盟路由设置，然后选择边缘或控制器。

> [!CAUTION]
> 此设置会影响所有网站。 确保您要在该站点上配置的设置是适用于所有网站。

## <a name="see-also"></a>另请参阅

有关详细信息，请参阅[外部用户访问的拓扑](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。


