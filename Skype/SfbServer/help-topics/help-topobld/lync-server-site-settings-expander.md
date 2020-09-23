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
# <a name="lync-server-site-settings-expander"></a>Lync Server 站点设置扩展器

若要编辑现有网站的属性，请执行以下操作：



## <a name="site-properties"></a>站点属性

在 "网站属性" 中，您可以更改或修改 " (必需的网站名称") 、"说明" (可选) 、City (可选) 、州/省 (可选) 以及国家/地区代码 (可选) 。

有关网站属性的详细信息，请参阅 [将分支站点添加到您的拓扑](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。

## <a name="federation-route-properties"></a>联合路由属性

若要设置站点联合路由分配，必须首先在边缘服务器或边缘服务器池上启用了联合身份验证。 如果在边缘服务器或池上未启用联合，则网站的联合路由分配设置将不可修改。

如果已配置边缘服务器或池上的联合身份验证设置，请选择 "在网站级别 **启用** "。 然后从下拉列表中选择一个边缘或一个控制器，以将其设置为联合路由。

> [!CAUTION]
> 此设置将影响所有网站。 确保您在此网站上配置的设置适用于所有网站。

## <a name="see-also"></a>另请参阅

有关详细信息，请参阅 [适用于外部用户访问的拓扑](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。


