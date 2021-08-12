---
title: Lync Server 站点设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑现有网站的属性，请执行下列操作：
ms.openlocfilehash: 24d5982c39fdb3228c73adb80e2a3e3728b62a163d55b68a9508a57cf5abf154
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311700"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 站点设置扩展器

若要编辑现有网站的属性，请执行下列操作：



## <a name="site-properties"></a>站点属性

在网站属性中，可以更改或修改网站名称 (必需) 、说明 (可选) 、城市 (可选) 、省/市/自治区 (可选) 以及国家/地区代码 (可选) 。

有关站点属性的详细信息，请参阅 [将分支站点添加到拓扑](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)。

## <a name="federation-route-properties"></a>联合身份验证路由属性

若要设置站点联盟路由分配，必须先在边缘服务器或边缘服务器池上启用联盟。 如果未在边缘服务器或池中启用联盟，则网站的联盟路由分配设置将不能进行修改。

如果已配置边缘服务器或池的联盟设置，请选择" **在** 站点级别启用"。 然后从下拉列表中选择边缘或控制器以设置为联盟路由。

> [!CAUTION]
> 此设置将影响所有网站。 确保您在此站点配置的设置适合所有网站。

## <a name="see-also"></a>另请参阅

有关详细信息，请参阅 [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)。