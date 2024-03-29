---
title: 将前端与边缘关联
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: 每个前端池只能有一个与之关联的边缘服务器或边缘池。 为网站启用外部用户访问时，可以为远程用户提供支持。 您还可以启用对联盟用户的支持，包括对特定公共即时消息 (IM) 连接提供程序 (（如 Windows Live) ）的用户的支持，以及对匿名用户的支持。
ms.openlocfilehash: f894a38fc48b1a2c6610e8d3b886fa028b2559b8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390464"
---
# <a name="associate-front-end-with-edge"></a>将前端与边缘关联

每个前端池只能有一个与之关联的边缘服务器或边缘池。 为网站启用外部用户访问时，可以为远程用户提供支持。 您还可以启用对联盟用户的支持，包括对特定公共即时消息 (IM) 连接提供程序 (（如 Windows Live) ）的用户的支持，以及对匿名用户的支持。

站点中的所有池和多个中央站点的池可以使用同一边缘服务器，前提是使用量不超过边缘服务器的容量。有关监控的详细信息（包括伸缩），请参阅规划文档中的[Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)。有关设计支持外部用户访问的拓扑的详细信息，请参阅部署文档中的[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。