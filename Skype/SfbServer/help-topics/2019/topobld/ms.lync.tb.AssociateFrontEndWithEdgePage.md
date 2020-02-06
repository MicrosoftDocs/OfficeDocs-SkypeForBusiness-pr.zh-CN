---
title: 将前端与边缘关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: 每个前端池只能拥有一个关联的边缘服务器或边缘池。为站点启用外部用户访问时，可提供对远程用户的支持。还可以启用对联盟用户的支持，包括对特定公共即时消息 (IM) 连接提供商（如 Windows Live）用户的支持，以及对匿名用户的支持。
ms.openlocfilehash: 8c59423562ebc511e8947d9448010b1f097df96d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793990"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="59f41-105">将前端与边缘关联</span><span class="sxs-lookup"><span data-stu-id="59f41-105">Associate Front End With Edge</span></span>

<span data-ttu-id="59f41-p102">每个前端池只能拥有一个关联的边缘服务器或边缘池。为站点启用外部用户访问时，可提供对远程用户的支持。还可以启用对联盟用户的支持，包括对特定公共即时消息 (IM) 连接提供商（如 Windows Live）用户的支持，以及对匿名用户的支持。</span><span class="sxs-lookup"><span data-stu-id="59f41-p102">Each Front End pool can have only one Edge Server or Edge pool associated with it. When you enable external user access for a site, you can provide support for remote users. You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="59f41-p103">站点中的所有池和多个中央站点的池可以使用同一边缘服务器，前提是使用量不超过边缘服务器的容量。有关监控的详细信息（包括伸缩），请参阅规划文档中的[Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)。有关设计支持外部用户访问的拓扑的详细信息，请参阅部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="59f41-p103">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server. For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation. For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


