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
ms.openlocfilehash: acfd7e312dbde97e847a9b97d9730a6d0b3488da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832912"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 站点设置扩展器

若要编辑现有网站的属性，请执行下列操作：



## <a name="site-properties"></a>站点属性

在网站属性中，可以更改或修改网站名称 (必需) 、说明 (可选) 、城市 (可选) 、省/市/自治区 (可选) 以及国家/地区代码 (可选) 。

有关站点属性的详细信息，请参阅["将分支站点添加到拓扑"。](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)

## <a name="federation-route-properties"></a>联合身份验证路由属性

若要设置站点联盟路由分配，必须先在边缘服务器或边缘服务器池上启用联盟。 如果未在边缘服务器或池上启用联盟，则网站的联盟路由分配设置将不能进行修改。

如果已配置边缘服务器或池的联盟设置， **请选择"在** 站点级别启用"。 然后从下拉列表中选择边缘或控制器以设置为联盟路由。

> [!CAUTION]
> 此设置将影响所有网站。 确保在此站点配置的设置适合所有网站。

## <a name="see-also"></a>另请参阅

有关详细信息，请参阅["外部用户访问的拓扑"。](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)


