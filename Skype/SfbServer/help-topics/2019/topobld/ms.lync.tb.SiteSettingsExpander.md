---
title: Lync Server 站点设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: '若要编辑现有网站的属性, 请执行下列操作:'
ms.openlocfilehash: 1f15ed4230d7a72b67b8df804748f9b732278293
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303079"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 站点设置扩展器

若要编辑现有网站的属性, 请执行下列操作:



## <a name="site-properties"></a>网站属性

在 "网站属性" 中, 您可以更改或修改 "网站名称 (必需)"、"说明" (可选)、"城市" (可选)、"州/省" (可选) 和国家/地区代码 (可选)。

有关网站属性的详细信息, 请参阅[将分支站点添加到你的拓扑](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。

## <a name="federation-route-properties"></a>联盟路线属性

若要设置站点联合路由分配, 必须首先在 Edge 服务器或 Edge 服务器池中启用了联合身份验证。 如果在 Edge 服务器或池上未启用联盟, 则该网站的联盟路由分配设置将不可用于修改。

如果已配置 Edge 服务器或池的联盟设置, 请在网站级别选择 "**启用**"。 然后从下拉列表中选择一个边缘或主管以设置为联盟路线。

> [!CAUTION]
> 此设置将影响所有网站。 请确保您在此网站上配置的设置适用于所有网站。

## <a name="see-also"></a>另请参阅

有关详细信息, 请参阅[外部用户访问的拓扑](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。


